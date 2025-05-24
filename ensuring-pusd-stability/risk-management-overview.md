# Risk Management overview

At Parity Finance, we implement a range of key measures to ensure the stability and security of our protocol, safeguarding assets and maintaining the stability of the Parity Dollar (PUSD). Below are the core measures we have in place to mitigate risks and protect the Parity ecosystem:

**Stablecoin Holdings**: Approximately **48%** of Parity Dollar’s reserves are effectively held in leading stablecoins (USDC and Tether). 20 percentage points of this comes from direct holdings used for CEX collateral and hedging operations, while the remaining portion is indirectly held through JLP, where stablecoins have a 35% weight. This substantial allocation of stablecoins enhances the stability, delta-neutrality, and liquidity of the protocol, providing a strong foundation against market volatility.

**Cold Storage Security**: **80%** of Parity Dollar’s reserves are securely stored in **Fireblocks cold wallets**. These funds are offline and inaccessible to online threats, including hacks or smart contract vulnerabilities, ensuring maximum safety.

**Dynamic Hedging Strategy**: To maintain **delta-neutrality**, Parity actively monitors and adjusts its hedging positions. This helps mitigate the impact of price swings in major cryptocurrencies, such as **SOL**, **BTC**, and **ETH**, ensuring stability for the Parity Dollar.

**Efficient Liquidity Management**: In the event of market stress, Parity can disassemble its **JLP** holdings into underlying liquid assets like **BTC**, **SOL**, and **USDC**, ensuring efficient liquidation. Even in adverse market conditions, liquidation costs are estimated to be under **1%**, preserving the 1:1 redemption rate for PUSD.

**Peg Stability Assurance**: Parity maintains a **1:1 peg** with USDC, supported by a portion of reserves which always remain in the smart contract and provide immediate redemption liquidity. This ensures that redemptions can be honored promptly and that PUSD $-peg is intact.

**Third-Party Audits**: **Parity Finance** has undergone multiple audits, most recently by **Quantstamp**, a leading blockchain security auditor. This ensures the protocol's smart contracts are secure, well-structured, and adhere to best practices.

**Off-Exchange Settlement**: To further minimize **custodial risks**, Parity is moving towards **off-exchange settlement** solutions with partners like **Fireblocks** and **Ceffu**. This ensures that even when interacting with centralized exchanges, funds are kept in secure, third-party custodial systems.

**Segregation of PUSD reserves:** Reserves are held in a Special Purpose Vehicle (SPV) with a separate balance sheet and accounts. SPV directors oversee operations, upholding their fiduciary duty to safeguard Parity Dollar reserves.

**No Leverage**: Parity does not use leverage, significantly reducing **liquidation risk**. By avoiding borrowed capital, we ensure that Parity’s reserves are not overexposed to market volatility, further protecting the protocol during extreme conditions.

**Reserve fund:** Parity maintains a **Reserve Fund**, which is expected to scale to \~5% of all outstanding PUSD. This fund serves as an additional buffer, ensuring that any short-term negative returns are absorbed without affecting the stability of the Parity Dollar or its peg.

**Franklin Templeton Fallback Protection**: In the rare event where crypto markets face an extreme downturn, Parity has a solid fallback plan. The protocol has an agreement to unwind positions into **Franklin Templeton's tokenized Tbills Fund - Benji.**&#x20;



