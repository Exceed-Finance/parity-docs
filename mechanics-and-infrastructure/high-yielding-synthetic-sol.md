# High-Yielding Synthetic SOL

**pikSOL** and **pitSOL** are Parity’s synthetic SOL products, **designed to deliver enhanced yield** while maintaining SOL exposure and capital efficiency.

## How Yield is Generated

Yield on synthetic SOL is powered by three coordinated mechanisms:

#### 1. JLP Trading Commissions

Parity allocates capital into the JLP pool, which powers Solana’s leading Perps DEX, earning a share of trading fees and funding from perpetuals traders.

#### 2. Perpetual Funding Rates

When funding rates are negative, Parity may open long SOL positions on decentralized (Drift) or centralized (Binance) perpetual exchanges, collecting funding fees for its long SOL exposure.

#### 3. Validator Rewards (Dynamic Switching)

When blockchain-native staking rewards (validator yield) exceed market-based returns, Parity dynamically reallocates capital to traditional staking — ensuring users earn at least as much as they would via traditional staking providers. This switching mechanism guarantees baseline staking performance with upside when market conditions are favorable.

## Maintaining SOL Exposure and Peg

To ensure that synthetic SOL 1:1 tracks the performance of native SOL:

* The protocol uses a combination of JLP pool exposure, SOL-denominated derivatives, and validator staking
* This allows Parity to mirror SOL’s price behavior 1:1 while capturing yield from multiple sources

The peg is maintained through:

* Redeemability of synthetic SOL at par value for SOL at any time
* Real-time asset-liability matching
* A transparent dashboard displaying real collateral composition

**pikSOL and pitSOL are always backed by yield-generating collateral**, with built-in protections to prioritize peg stability and risk-adjusted yield.
