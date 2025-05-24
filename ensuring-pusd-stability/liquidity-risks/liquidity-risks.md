# Liquidity Risks

## Definition

Liquidity risks refer to a “bank run” type scenario, where Parity must quickly liquidate its positions to redeem PUSD held by users 1:1 against USDC. The primary concern here is how quickly and at what cost Parity can liquidate its positions to meet redemptions.

**Hedged JLP Strategy**: Parity employs the hedged JLP strategy to manage its reserves. In the event of a severe market downturn, while secondary trading activity in JLP may be low, the strength of JLP lies in its composition—it is a composite asset consisting of five blue-chip, liquid cryptocurrencies. Similar to how an S\&P 500 ETF can be disassembled into its underlying components, Parity can disassemble JLP into its constituent cryptocurrencies (e.g., BTC, ETH, SOL, USDC, USDT) to enable efficient liquidation. This ensures that despite low secondary market activity, Parity’s underlying assets remain highly liquid and accessible.

<figure><img src="../../.gitbook/assets/SS 15 (2).png" alt=""><figcaption></figcaption></figure>

**Fair Value and Redeeming JLP**: Jupiter charges between 0-150 basis points (bps) depending on which of the underlying assets you are redeeming JLP into. The pool maintains target weights for each of the five assets, and the cost of minting/redeeming JLP depends on how these actions affect the pool's balance. If minting/redeeming helps bring the pool closer to its target weights, it can be done at little to no cost versus fair value (referred to as the “Virtual Price,” similar to the NAV of an investment fund). Given that pool composition is a zero-sum game (i.e. the 5 individual parts must sum to 100%), some assets in the JLP pool are always below and some assets are above their target weights. By tracking the relative abundance of assets – Parity can utilise to its advantage to liquidate its JLP holdings at relatively low cost. By tracking asset weight imbalances in the pool, Parity can optimize liquidation costs, ensuring redemptions occur at a low cost.

<figure><img src="../../.gitbook/assets/SS 21.png" alt=""><figcaption></figcaption></figure>

**Cost of Liquidation**: We estimate that, even under market stress, the cost of unwinding JLP positions into USDC (including disassembling JLP units, bridging BTC/ETH, and trading costs) will not exceed 1%. In these cases, Parity's insurance fund will cover the cost, allowing Parity to redeem PUSD at 1:1 against USDC. If liquidation costs exceed 1%, Parity may temporarily impose redemption fees to cover the penalty for liquidating positions, ensuring stability.

**Hedging Position Liquidity**: Regarding the liquidation of hedging positions, Parity takes the opposite side of the general market flow in downturns, allowing these positions to be unwound with relative ease. Parity conducts most of its hedging on Binance and Bybit, which combined account for around 80% of perpetual futures open interest and trading volumes, further mitigating liquidity concerns.

## Edge Cases

One rare edge case to consider is when Parity is redeeming JLP into its underlying units, and the pool liquidity is reserved for opened traders' positions. In such a scenario, it may not be possible to redeem JLP holdings immediately at the source. However, the self-correcting mechanism of the JLP pool comes into play here. When utilization rates are very high, high fee APRs in the JLP pool attract fresh capital, which increases liquidity and creates more opportunities for redemptions. Simultaneously, the cost for traders to maintain positions increases, potentially leading traders to unwind positions to avoid high fees.
