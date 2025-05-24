# Delta Neutrality risk

## Introduction

To ensure 1:1 redemption of PUSD against USDC, Parity Dollar reserves must remain stable in dollar terms and free from volatility. This requires the reserves to be delta-neutral, meaning that they are unaffected by fluctuations in cryptocurrency prices. Achieving this is the core objective of the protocol's design.

Under the hedged JLP strategy, Parity's initial and exclusive reserve management approach, changes in crypto prices can affect the reserves through two channels: **market risk** (revaluation of assets) and **Traders' P\&L risk** (profit and loss from traders' positions). Understanding how these risks operate and how Parity hedges them requires a deep dive into the workings of the JLP (Jupiter Liquidity Provider) pool.

We reproduce the diagram from a previous section to demonstrate the basic workings of the JLP pool.

<figure><img src="../../.gitbook/assets/SS 8 (2).png" alt=""><figcaption></figcaption></figure>

And the JLP pool consists of 5 blue chip cryptos with the following target weights:

<figure><img src="../../.gitbook/assets/SS 15 (2).png" alt=""><figcaption></figcaption></figure>

## **Market Risk and Traders’ P\&L Risk in JLP**

Let's dive into the workings of the JLP pool. A key distinction is whether traders are going **long** or **short**.

Let’s say the trader goes long. The trader provides collateral of 1 SOL but wants to go long 10 SOL with 10x leverage. In this case the trader borrows 10 SOL from the JLP Pool. Assume the price of SOL is $100 at the time of opening the trade. If the price of SOL rises to $150, the trader is up $50 per SOL; total profit 10 SOL x $50 = $500. The trader decides to close the position and takes profit. The pool pays the trader $500 of his profit, based on the new price of SOL of $150; this would be $500 / $150 = 3.33 SOL. So the trader gets back his 1 Sol of Collateral and $500 worth of Profit or 3.33 SOL minus the trading and interest fees. The JLP pool on the other hand, has lost 3.33SOL to pay the trader. However, the 6.67Sol which the pool still owns from the trade out of the 10SOL initially reserves, are now worth: 6.67 SOL \* $150 = \~$1000, which is worth the same as the 10 SOL the pool had at the time when the trade was opened when SOL was $100. 10 x $100 = also $1000. The only difference for the pool are the fees that it made. The conclusion here is the JLP pool is hedged by design in $ terms from traders' winnings and losses when traders go long. Exactly the reverse happens when traders go long but the market goes down.

You can check [How JLP Works: Jupiter Station](https://station.jup.ag/guides/jlp/How-JLP-Works) for more details.

<figure><img src="../../.gitbook/assets/JLP SS 1.png" alt=""><figcaption></figcaption></figure>

**Utilization and Hedging**: A successful delta-neutral strategy depends on tracking the portion of the JLP pool reserved for traders' positions, known as the **utilization ratio**. The utilized part is hedged by design (through the mechanics of the pool), while the unused portion must be actively hedged to protect against market volatility. For SOL, ETH, wBTC – the utilised percentages are the portion, which is hedged by design and (1 – utilisation ratio) is what requires hedging to eliminate market risk. The utilisation ratio is also displayed on Jupiter’s own JLP dashboard. See below:

<figure><img src="../../.gitbook/assets/SS 17.png" alt=""><figcaption></figcaption></figure>

**Traders' P\&L risk arises from short positions:** in a second scenario, assume the trader goes short SOL. To go short the trader deposits collateral of $100 USDC (= 1 SOL) and goes short 10 SOL when the price of SOL is $100. Assume the price of SOL declines to $50. The trader has turned a profit of $50 x 10 = $500. The trader will be paid $500 in stablecoins from the JLP pool along with his $100 worth of initial collateral. From the JLP pool’s perspective, the pool will be down $500 in stablecoins minus the trading and interest fees. The conclusion here is that on the short side, the JLP Pool is not hedged by design, and when traders go short – JLP pool wins in $ terms when traders are wrong and loses in $ terms when traders are right. The following picture from Jupiter demonstrates this point:

<figure><img src="../../.gitbook/assets/JLP SS 2.png" alt=""><figcaption></figcaption></figure>

The **stablecoin portion** of the JLP pool (\~35%) is used as margin and settlement for short trades, and while it doesn't carry market risk, it carries P\&L risk for the LPs. Parity hedges the risk associated with traders' gains.

The following table summarises the hedging strategy required to stay delta neutral:

|   JLP Pool composition  |   Weight in JLP Pool   |   Risk to JLP holders   |   Amount to Hedge     |
| ----------------------- | ---------------------- | ----------------------- | --------------------- |
| Crypto                  | 65%                    | Market Risk             | (1-Utilisation Ratio) |
| Stablecoins             | 35%                    | Traders' P\&L Risk      | Utilisation Ratio     |

&#x20;The following graphic depicts the above table.

<figure><img src="../../.gitbook/assets/SS 16 (1).png" alt=""><figcaption></figcaption></figure>

## Edge Cases & Stress Testing Delta-Neutrality

Parity has built tailor-made infrastructure with elements of both DeFi and CeFi in order to monitor the necessary components for the protocol to stay Delta Neutral in real time and to hedge out these exposures.

### Potential Edge Cases and Their Repercussions

Currently, Parity updates its hedging positions every 5 minutes, while monitoring data is processed in real time. The worst-case scenario for delta neutrality would involve a sudden and significant swing in the utilization rates of the JLP pool. For example, imagine we’re in the depths of a bear market, where most traders are short and long positions are minimal. An unexpected event (such as a tweet) triggers a rapid price surge, causing long utilization rates to spike from 10% to 90% within 2 minutes, while short utilization rates simultaneously drop from 90% to 10%.

According to data from Binance, a 99.9% probability event (a 3.3 sigma event) would translate to a 3.5% price movement over a 5-minute period. We view the combination of 1) large position shifts, and 2) just in time for a large price swing, as highly improbable—not only because Jupiter Perps DEX users are physical traders rather than algorithmic crypto hedge funds, but also because it’s extremely unlikely that such a large portion of traders would collectively reverse their positions and do so just as an exceptionally large market shift is about to happen.

Even in this highly unlikely scenario, we estimate that Parity could lose 1.5-2% of its reserves. In the future, the protocol may consider increasing the frequency of hedging updates to reduce this risk further, though this would come with additional costs. For now, we believe the current setup provides sufficient protection under typical and even volatile market conditions.

### Solana Staking & Funding Fee Arbitrage

As Parity introduces its second reserve management strategy, **Solana Funding Fee Arbitrage**, maintaining delta-neutrality becomes simpler. This strategy involves a direct hedging operation that occurs simultaneously with changes in Solana holdings, further reducing risks compared to the JLP strategy.
