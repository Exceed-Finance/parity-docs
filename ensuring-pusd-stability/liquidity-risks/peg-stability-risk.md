# Peg Stability Risk

## Ensuring PUSD's $-peg&#x20;

**Ensuring the Peg**: The 1:1 peg of Parity Dollar (PUSD) against USDC is maintained by the ability to redeem PUSD for USDC at any time. As long as Parity can facilitate these 1:1 redemptions, market makers and arbitrageurs will enforce the peg by exploiting price differences in secondary markets.

To ensure this redemption is always possible, Parity's reserves must remain stable in dollar terms and highly liquid. As discussed in the delta-neutrality and liquidity risk sections, Parity employs strategies to guarantee both stability and liquidity, ensuring PUSD remains fully backed and redeemable.

***

**Temporary Redemption Fees**: In extreme situations, where the cost of liquidating positions exceeds 1%, Parity may temporarily introduce a redemption fee to preserve the peg. For example, if a 0.5% redemption fee is introduced and PUSD is trading at 99.6¢ versus $1 USDC, arbitrageurs would no longer profit from buying PUSD at that price because they would only receive 99.5¢ after fees. This mechanism prevents further downward pressure on the peg during high-stress scenarios, but it may temporarily weaken the peg while the fee is in place. However, this is a short-term measure designed to protect the protocol during rare events.

***

**Managing High Utilization**: In another unlikely scenario, where the JLP pool utilization is extremely high, making it difficult to perform primary redemptions, only secondary markets may be available to liquidate holdings. This is highly unlikely, as extreme market conditions generally lead to either high long or short positions, allowing at least partial redemptions from the JLP pool. Additionally, very high utilization rates attract new capital quickly, as high APR fees incentivize liquidity providers, while traders may scale back activity as liquidity becomes scarce.

In the rare event that no primary liquidity is available, Parity may temporarily suspend redemptions or introduce a higher redemption fee to reflect the cost of liquidating positions through secondary markets. These measures may negatively but temporarily affect the peg until normal conditions are restored.

***

**USDC Reserve Buffer**: To provide further peg stability, Parity maintains approximately 5% of its reserves in USDC, which can be used for immediate redemptions without the need to liquidate any positions. This buffer ensures that Parity can honor redemptions even in challenging market conditions. If the 5% USDC buffer is depleted, it is quickly replenished by liquidating reserve positions, ensuring the peg is continuously supported.
