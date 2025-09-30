# Liquid Staking Program Addresses

### Programs

**Liquid Staking Program Address:** `par1tyqusak2f2DXg9RHv78SVHNWXkJLSbtJZQSuWjV`

### Pairs

The Liquid Staking Program uses a "Pair" model to ensure that every LST issued is backed by an underlying token. Each pair maintains:

* An associated token account for the base token (receives deposits)
* An LST mint with configurable decimals matching the base token
* Dynamic exchange rates that compound yield over time based on APR and time intervals
* Configurable fees (stake, swap, withdrawal) up to 25% (2500 bps)
* Deposit caps and minimum deposit requirements

{% tabs %}
{% tab title="pikSOL" %}
| Type                 | Address                                        |
| -------------------- | ---------------------------------------------- |
| **Pair Address**     | `J6szVgxaWyCrvKJHfjrV6CzbFUcvfgu7KqQ7gJ1DtWii` |
| **LST Mint Address** | `8tbk3FoJwsgNtK3osT3XQ5iJnkuocrzAgPVkdkpZMsBi` |
{% endtab %}

{% tab title="pikUSDC" %}
| Type                 | Address                                        |
| -------------------- | ---------------------------------------------- |
| **Pair Address**     | `EwqMpnBHKEd537E37kcsNU9Qi82uukjVAXsC8K5Kswt7` |
| **LST Mint Address** | `8B9vL4c9w5HiyFXdPT8Z8hgFvSeZ14Y5DxjCZyRSTf4z` |
{% endtab %}
{% endtabs %}

### Withdrawal Windows

Withdrawal windows batch withdrawal requests for processing. Each window has:

* **Time boundaries:** `start_time`, `end_time`, `earliest_withdrawal_time`, `expiration_time`
* **Capacity limits:** `max_withdrawal_amount` (in base tokens)
* **Tracking fields:** `requested_withdrawal_amount`, `total_lst_burned`, `withdrawn_amount`
* **Funding status:** `is_funded` flag indicates if the window has been funded with base tokens

#### Finding a Withdrawal Window

```tsx
// Find a withdrawal window by unix timestamp
const unixTimestamp = Math.floor(Date.now() / 1000); // or getUnixTime(yourDate)

const [withdrawalWindowAddress] = findWithdrawalWindowPda(
    umi,
    pairAddress,
    unixTimestamp
);

// Fetch the window data
const windowSerializer = getWithdrawalWindowAccountDataSerializer();
const windowAccount = await umi.rpc.getAccount(withdrawalWindowAddress);
const [window] = windowSerializer.deserialize(windowAccount.data);

// Or fetch all windows using the GPA builder
const windowGpaBuilder = getWithdrawalWindowGpaBuilder();
const allWindows = await windowGpaBuilder.get();

```

#### Window Lifecycle

1. **Creation:** Window authority creates a window with time parameters and max withdrawal amount
2. **Request Period:** Users can request withdrawals between `start_time` and `end_time`
3. **Funding:** After `end_time`, deposit authority funds the window with `requested_withdrawal_amount` base tokens
4. **Execution Period:** Users can execute withdrawals between `earliest_withdrawal_time` and `expiration_time`
5. **Closure:** Window authority closes the window after all withdrawals are executed

### Account Derivation Seeds

Here are the PDA seeds used to derive each account type in the program:

#### Core Accounts

**Access Control**

```rust
seeds: [b"access_control"]

```

**Pair**

```rust
seeds: [
    b"pair",
    base_token_mint.key(),
    lst_mint.key()
]

```

**LST Mint**

```rust
seeds: [
    b"lst_mint",
    symbol.as_bytes()  // e.g., "pikSOL"
]

```

#### Withdrawal Accounts

**Withdrawal Window**

```rust
seeds: [
    b"withdrawal_window",
    pair.key(),
    start_time.to_le_bytes()  // i64 as little-endian bytes
]

```

**Withdrawal Request**

```rust
seeds: [
    b"withdrawal_request",
    withdrawal_window.key(),
    staker.key()
]

```

#### Finding Withdrawal Window Addresses Manually

To manually derive a withdrawal window address, you need:

1. **The pair address** - e.g., `J6szVgxaWyCrvKJHfjrV6CzbFUcvfgu7KqQ7gJ1DtWii` for pikSOL
2. **The window's start time** - Unix timestamp as an i64
3. **The program ID** - `par1tyqusak2f2DXg9RHv78SVHNWXkJLSbtJZQSuWjV`

**Manual Derivation Example:**

```tsx
import { PublicKey } from '@solana/web3.js';

// Convert unix timestamp to little-endian bytes
function timestampToBytes(unixTimestamp: number): Buffer {
    const buffer = Buffer.alloc(8);
    buffer.writeBigInt64LE(BigInt(unixTimestamp));
    return buffer;
}

// Manual PDA derivation
const programId = new PublicKey('par1tyqusak2f2DXg9RHv78SVHNWXkJLSbtJZQSuWjV');
const pairAddress = new PublicKey('J6szVgxaWyCrvKJHfjrV6CzbFUcvfgu7KqQ7gJ1DtWii');
const startTime = 1704067200; // Example: Jan 1, 2024

const [withdrawalWindowAddress, bump] = PublicKey.findProgramAddressSync(
    [
        Buffer.from('withdrawal_window'),
        pairAddress.toBuffer(),
        timestampToBytes(startTime)
    ],
    programId
);

console.log('Withdrawal Window Address:', withdrawalWindowAddress.toString());

```

**Key Points:**

* The `start_time` must be converted to **little-endian i64 bytes** (8 bytes)
* Each unique `start_time` creates a different withdrawal window
* Windows are immutable once created - the start time becomes part of the address
* To find an existing window, you must know its exact start time or enumerate all windows using the GPA builder
