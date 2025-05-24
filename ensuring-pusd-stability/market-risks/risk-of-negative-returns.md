# Risk of Negative Returns

## Definition

The **risk of negative returns** refers to the possibility that Parity Dollar’s reserves may yield negative returns under certain conditions. Below, we outline the factors that could lead to negative returns, the potential impact on Parity, and the measures in place to manage this risk.

Under the **hedged JLP strategy**—the primary reserve management approach employed by Parity—fees paid by traders can only be positive. This means that in most cases, Parity collects fees without the risk of incurring negative returns from trader activity. However, negative returns can occur in rare scenarios where hedging costs turn negative, and these costs significantly exceed the fees that Parity collects from providing liquidity on Jupiter.

Recalling the earlier diagram, which breaks down JLP Pool into hedged and non-hedged parts:

<figure><img src="../../.gitbook/assets/SS 16.png" alt=""><figcaption></figcaption></figure>

## The Mechanics

Parity, along with other liquidity providers (LPs), earns its proportionate share of fees on the portion of the JLP pool that is utilized (i.e., actively supporting open trading positions). This pool needs to be hedged to remain delta-neutral, particularly on the parts encircled by the dotted lines in the earlier diagram.

In normal conditions, Parity collects fees from trading activity and also benefits from positive funding rates on the short perpetual contracts used for hedging. In fact, in 9 out of 10 cases, these funding rates are positive.

However, in a hypothetical scenario where utilization of the JLP pool drops to zero on both the long and short sides—meaning Parity receives no fees—and hedging costs turn negative, it is possible to encounter negative returns

## Risk Mitigation Strategies

In the rare event of negative returns, Parity has a strong **safety net** in place. Parity holds an agreement with **Franklin Templeton**, a $1.7 trillion asset manager, allowing the protocol to unwind its positions into **Franklin Templeton’s Benji Token**. The Benji Token represents a tokenized share in Franklin Templeton’s short-term Treasuries fund, ensuring the stability of Parity Dollar’s reserves when crypto markets face extreme stress.

Additionally, Parity maintains a **Reserve Fund**, which is expected to grow to approximately **5% of all outstanding PUSD**. This fund can be temporarily tapped to bridge any negative returns, ensuring that the Parity Dollar’s peg remains intact and that no negative returns are passed onto users.

It is also important to note that a scenario where there is zero activity on the Jupiter Perps DEX is highly unlikely. Even in a deep bear market, while there may be little to no utilization on the long side, the short side of the pool is likely to see considerable activity. This would generate fees for Parity, which would more than likely offset any potential negative hedging costs.

Finally, to illustrate the distribution of funding rates—representing Parity’s hedging returns or, in rare cases, hedging costs—we refer to the earlier chart for a detailed breakdown.

<figure><img src="../../.gitbook/assets/SS 12.png" alt=""><figcaption></figcaption></figure>
