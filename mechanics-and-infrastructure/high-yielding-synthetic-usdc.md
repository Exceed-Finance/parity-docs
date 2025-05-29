# High-Yielding Synthetic USDC

**pikUSDC** and **pitUSDC** are Parity’s synthetic USDC products, **offering USD-pegged exposure** with **significantly higher yield** than traditional stablecoins — powered by crypto-native yield sources.

## How Yield is Generated

Yield on synthetic USDC is derived from three core mechanisms:

#### JLP Trading Commissions

Parity allocates capital into the JLP pool, which powers Solana’s leading Perps DEX, earning a share of trading fees and funding from perpetual traders.

#### Slana Basis Trade

Parity runs a delta-neutral strategy by staking SOL while shorting SOL perps. This earns:

* \~8% from staking SOL (inflation, fees, MEV)
* \~12% from funding fees on short perp positions\
  Together, this strategy offers stable, relatively high yield USD returns.

#### Crypto Risk Free Rate Switching

When market conditions reduce returns below the prevailing USD crypto risk free rate (the baseline stablecoin yield available on blue-chip borrow-lend protocols), Parity automatically reallocates to those benchmark strategies. This includes either:

* Switching to leading DeFi lending protocols (e.g. Kamino, DRIFT)
* Or converting reserves into Franklin Templeton’s Benji Token, via Parity’s integration agreement

This dynamic floor ensures that Parity never underperforms what users could get from low-risk DeFi yield options.

## Maintaining the $1 Peg

Parity ensures synthetic USDC stays pegged to $1 through:

* Full redeemability at par
* Real-time rebalancing to maintain delta-neutrality of reserves

Reserves are always transparent and auditable via the protocol’s dashboard. **Every pikUSDC and pitUSDC token is backed by real, productive collateral** designed to maintain both liquidity and peg integrity under a wide range of market conditions.
