# Solana staking & funding fee arbitrage

## Reserve Management Strategy 2: SOL Staking & Funding Fee Arbitrage

Parity’s second reserve management strategy is SOL staking & funding fee arbitrage. The strategy involves holding staked SOL and simultaneously shorting an equivalent amount of SOL via perpetual derivatives. This forms a fully hedged position, which is unaffected by the swings in SOL’s price. Whether the price of SOL goes up or down, the winnings and losses on the two legs of the trade offset each other one for one. This allows Parity to maintain the stability of its reserves in $ terms.

<figure><img src="../.gitbook/assets/SS 10.png" alt=""><figcaption></figcaption></figure>

By holding **staked SOL** while shorting SOL via perpetual derivatives, Parity generates returns of around **20% in a neutral market environment**. The strategy breaks down into two components:

* **Staking Returns (\~8%)**: Parity holds staked SOL tokens, which grow at around 8% APY. The underlying staking returns are derived from SOL token inflation, transaction fees, and MEV (Maximal Extractable Value). New SOL tokens are minted and distributed to stakers as rewards, while transaction fees and MEV contribute additional income.
* **Funding Fees (\~12%)**: Collected by shorting SOL in the perpetual futures markets. As perpetual futures do not expire, funding fees are used to keep the futures price aligned with the spot price. Because long traders are more common than short traders, funding rates are typically positive (in around 9 out of 10 cases), with short position holders like Parity receiving payments from long position holders.

<figure><img src="../.gitbook/assets/SS 11.png" alt=""><figcaption></figcaption></figure>

## Staking Returns

The 8% staking returns on Solana primarily come from token inflation, where new SOL tokens are minted and distributed as rewards to stakers. This inflation incentivizes SOL holders to lock up their tokens and help secure the network by participating in its proof-of-stake consensus mechanism. By staking their SOL, holders delegate their tokens to validators who are responsible for verifying transactions and maintaining the blockchain. In return, stakers receive periodic rewards, helping to ensure the decentralization and security of the network.

Beyond token inflation, staking rewards also include transaction fees generated on the Solana network. Every time a transaction occurs, a small fee is paid by the user, and a portion of these fees goes to validators and stakers. This source of income increases as network activity rises, adding to the overall staking returns.

Another important factor contributing to staking rewards is MEV (Maximal Extractable Value). MEV represents the extra profit validators can earn by optimizing the way transactions are ordered in a block. Validators can prioritize certain transactions (such as high-fee transactions) in a way that maximizes their own earnings. This practice contributes additional rewards to stakers, enhancing the overall return on their staked SOL.

See [Learn how the Solana blockchain works | Solana](https://solana.com/docs) as a further reading resource.

## Funding Fees

And 12% funding fees on an average day come from perpetual futures markets, which are derivatives unique to the crypto space. Unlike traditional futures contracts, perpetual futures (also known as "perps") do not have an expiry date. Their price is designed to track the spot price of the underlying asset, but without natural settlement, there needs to be a mechanism to keep the futures price close to the spot price. This is where funding fees come in.

Funding fees are periodic payments exchanged between long and short positions in the perpetual futures market. The funding rate is determined by the difference between the futures price and the spot price. If the futures price is higher than the spot price, long traders pay funding to short traders, and if the futures price is lower, shorts pay longs. Because in the majority of cases (around 9 out of 10) there are more traders long on SOL futures than short, funding fees tend to be positive.

On average, the median funding rate hovers around 11%, with average returns of 12-14% on the short leg of the trade. It’s only about 10% of the time that the funding rate turns negative, requiring short traders to pay the long side. Thus, by shorting SOL perpetuals, Parity captures these regular, positive funding payments to enhance the overall returns of the strategy.

Solana funding fee arbitrage will in the near future become a more profitable and a much larger opportunity as Centralised Exchanges such as Binance, Bybit, Bitget, and others have all recently announced their version of SOL LSTs (Liquid Staked Tokens), along with the goal of making these tokens eligible collateral for margin trading activities on these exchanges.

<figure><img src="../.gitbook/assets/SS 12.png" alt=""><figcaption></figcaption></figure>
