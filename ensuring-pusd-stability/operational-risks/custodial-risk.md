# Custodial Risk

**Non-Custodial Model**

The Parity Protocol is a fully non-custodial platform, meaning that we do not hold or manage users’ funds. Users maintain complete control over their assets, including PUSD and sPUSD. These tokens are stored directly in users’ wallets, and users are responsible for managing and securing their own holdings, ensuring they retain ownership at all times.

**Reserves Management**

When it comes to the reserves backing Parity Dollar (PUSD), Parity takes additional measures to ensure maximum security. In the early stages of the protocol, with the hedged JLP strategy as the primary reserve strategy, 80% of Parity’s reserves are securely stored in a Fireblocks cold wallet, an institutional-grade custody solution. This cold storage provides robust protection against:

* **Liquidation risk**
* **Hacks**
* **Smart contract vulnerabilities**
* **Internal control failures**

For transparency, Parity Protocol will publicly share its wallet address, allowing users to view its holdings and reserves in real-time.

**Off-Exchange Settlement for CEX Exposure**

For the remaining 20% of reserves that are deployed on centralized exchanges (CEXs) for hedging, Parity is actively transitioning to an off-exchange settlement solution. This means that soon, no funds will be held directly on centralized exchanges, significantly reducing custodial risk. Instead, all funds will be stored with high-quality third-party custodians such as:

* **Fireblocks**
* **Ceffu (Binance’s institutional custody solution)**

This off-exchange model ensures that even when Parity interacts with CEXs, its assets are kept securely in third-party custody, protecting them from the operational and custodial risks typically associated with exchanges.

**Flow of Funds and Security Architecture**

All interactions between Parity's smart contracts and the DeFi ecosystem flow securely through Fireblocks’ MPC multisig wallet architecture. This ensures that any funds moving between Parity’s smart contracts, Solana DeFi platforms (such as JLP), and CEX platforms are protected within the Fireblocks security system.

Additionally, funds can only be moved to whitelisted wallet addresses, including Parity’s own custodial wallets for interactions with Binance, Bybit, and their associated off-exchange settlement wallets. This ensures that funds are always transferred securely, without exposure to unauthorized transfers or breaches.
