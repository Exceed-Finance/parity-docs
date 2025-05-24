# Hedged JLP Strategy

## Reserve Management Strategy 1: Hedged JLP (Jupiter Liquidity Provider)

Parity Finance is a **Liquidity Provider** on the **Jupiter Perps DEX** (Perps = Perpetual Derivatives; DEX = Decentralized Crypto Exchange). Jupiter Perps DEX is the most popular perps DEX on Solana and consistently ranks among the top three perps DEXes across all blockchains (see [DefiLlama](https://defillama.com/derivatives) for the latest stats). Unlike traditional order-book-based exchanges, Jupiter is a Trader-to-Pool exchange, where a pre-funded liquidity pool enables trading. This pool allows traders to go long or short on blue-chip crypto assets using the liquidity provided by participants like Parity. The diagram below provides a simplified view of how Jupiter Perps DEX operates:

<figure><img src="../.gitbook/assets/SS 8.png" alt=""><figcaption></figcaption></figure>

For more details on how **Jupiter Perps** works, check out their documentation here: [Understanding Jupiter Perps](https://station.jup.ag/guides/perpetual-exchange/overview). For a hands-on look at the trading experience, visit: [Jup.ag/perps](https://jup.ag/perps).

Jupiter Perps DEX’s popularity and high trading volumes make it one of the highest fee-generating DeFi applications. 75% of trading fees go to Liquidity Providers (LPs) like Parity. These fees can be tracked through third-party apps like [Gauntlet’s Risk Dashboard](https://app.gauntlet.xyz/protocols/jupiter) or Jupiter’s own analytics: [JLP Earn](https://jup.ag/perps-earn). Parity’s participation in the JLP pool allows it to collect its share of these fees, enabling Parity to offer 20% APY to Parity Deposit Token holders. The expected returns from the Hedged JLP strategy in a neutral market environment range between 20-40%.

## The $-peg and hedging

As a stablecoin, Parity Dollar (PUSD) can be redeemed for $1 USDC at any time. This requires Parity’s reserves to remain stable and liquid in dollar terms. The JLP pool consists of SOL, BTC, ETH, USDC, and USDT with target weights of 44%, 11%, 10%, 26%, and 9% respectively. Without hedging, this exposure to crypto market movements could negatively impact Parity’s reserves during market downturns. To mitigate this, Parity employs a hedging strategy to protect against price swings in SOL, ETH, and BTC.

Hedging works like insurance against market downturns. By shorting the assets held in the JLP pool through perpetual derivatives, Parity ensures that gains and losses offset each other, keeping the portfolio stable—what is known as a delta-neutral position. For example, holding 100 SOL and simultaneously shorting 100 SOL makes the portfolio fully hedged against price changes in Solana. The positive funding rates typical of crypto markets mean that short positions often receive funding from traders who are long, allowing Parity to earn from taking out this insurance against market volatility rather than pay.

Successfully hedging JLP pool holdings involves three main steps:

1. Separating the JLP pool into portions belonging to LPs and traders, accounting for collateral and traders' unrealized profits and losses.
2. Real-time tracking of traders' positions.
3. Hedging out market risk and traders' potential gains to maintain delta neutrality.

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><strong>Jupiter LPs Payoff Before Hedging =</strong></td><td><ul><li>Trading fees and interest fees paid by traders</li><li>+ SOL/BTC/ETH price increases</li><li>- SOL/BTC/ETH price decreases</li><li>+ Traders' losses</li><li>- Traders' winnings</li></ul></td></tr><tr><td><strong>Jupiter LPs Payoff After Hedging =</strong></td><td><ul><li>Trading fees and interest fees paid by traders</li><li>+ Hedging returns</li></ul></td></tr></tbody></table>

The goal of hedging is to protect Parity’s reserve holdings from market volatility while ensuring consistent earnings from trading fees and hedging premiums.

## Performance Overview

The chart below illustrates the performance of Parity Dollar reserves since April 15th, assuming that all reserves were fully invested in the Jupiter LP pool with complete hedging against market swings and traders’ profits and losses. The performance comparison includes two scenarios: “JLP fees,” which shows returns from collecting fees alone, and “JLP hedged,” which reflects the combined performance of fee collection and hedging returns. The Hedged JLP strategy has delivered approximately 40% annualized returns since April.

<figure><img src="../.gitbook/assets/SS 9.png" alt=""><figcaption></figcaption></figure>

**Hedging Operations**: These operations are managed by **Parity’s hedging engine**, a sophisticated system that tracks the dynamic JLP pool composition, traders' positions, and crypto market prices. By continuously adjusting Parity’s hedging positions, the engine ensures that Parity’s reserves maintain a delta-neutral stance, effectively shielding them from market volatility. For more details on delta neutrality and its importance, see the **Risks Section**.

**Liquidity and Stability**: Parity's JLP positions remain highly liquid, enabling Parity to swiftly adjust its holdings to meet PUSD redemptions without disruption. Since the JLP pool consists of five blue-chip cryptocurrencies—SOL, ETH, wBTC, USDC, and USDT—Parity can efficiently convert JLP holdings back into these underlying assets whenever necessary. This ensures that the liquidity of reserves even during market stress. For a deeper dive into liquidity management, refer to the Liquidity Risks section.

**Strategic Focus**: The **Hedged JLP strategy** is the core reserve management approach that Parity will employ, particularly in the early stages of the protocol’s development.&#x20;

