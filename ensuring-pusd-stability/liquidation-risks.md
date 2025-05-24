# Liquidation Risks

## Definition

To maintain $ stability and liquidity of Parity Dollar reserves, Parity must hedge its crypto holdings to remain delta neutral at all times. These hedging operations require large amounts of liquidity and significant Open Interest in derivatives, which are only available on centralised exchanges, such as Binance and Bybit.

However, Binance and Bybit do not accept JLP (Jupiter Liquidity Pool) tokens as collateral, and it is unlikely they will in the future. As a result, Parity splits its reserves: the majority is invested in JLP, while a smaller portion—around 20%—is allocated to CEXs as collateral for hedging positions. This split balances capital efficiency with liquidation risk: the more funds held on CEXs, the lower the risk of liquidation, but at the expense of reduced capital efficiency. Parity manages this trade-off by ensuring that CEX collateral can withstand a 40% instant price upswing in SOL, BTC, and ETH.

Liquidation risk refers to the possibility that Parity’s collateral on CEXs could be forcibly sold if the collateral becomes insufficient due to rapid market movements, potentially leading to losses and disruption of delta neutrality. Despite Parity operating without leverage, liquidation remains a possibility due to the necessary split of reserves described above.

The below diagram shows reserves distribution for Parity:

<figure><img src="../.gitbook/assets/SS 19.png" alt=""><figcaption></figcaption></figure>

## Managing Collateral Ratios

As discussed in the delta-neutrality section, the size of hedging positions for Parity depend on the utilization rates of crypto and stablecoins in the JLP pool. Under typical market conditions, the 80/20 reserve split is sufficient to withstand a 40% upward price movement over a short period. In more bearish scenarios, where short utilization is high and long utilization is low, Parity may adjust to a 75/25 split, and in extreme cases (e.g., a 4:1 short-to-long ratio), a 70/30 split may be required. Parity continuously monitors market conditions and adjusts its reserve allocations to maintain stability.

In deeply bearish markets, where short-to-long ratios are high, many traders may struggle to absorb a 40% price spike, which could reduce Parity’s hedging needs and improve the resilience Parity's collateral. Additionally, since Parity holds short positions, market downturns typically strengthen its collateral position with CEXs, minimizing the risk of liquidation. The primary risk arises during sudden, sharp market upswings when many traders are positioned for downward movements.

## Worst-Case Scenario

In the unlikely event that Parity’s collateral on CEXs is liquidated due to sudden market movements, the impact is limited to the 20% of reserves held as collateral on these exchanges. In such a scenario, Parity would incur liquidation fees on this portion of reserves, typically amounting to a few percentage points. While this would disrupt delta neutrality temporarily, it would only affect a relatively small part of Parity’s overall reserves.&#x20;
