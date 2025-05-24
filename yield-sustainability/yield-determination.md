# Yield Determination

## How is The Protocol’s Yield Determined and Can It Change?

The Parity Protocol generates a **Baseline Yield**, which reflects the returns from its Parity Dollar (PUSD) reserves. This Baseline Yield drives the rewards users receive from both USD Staking and Parity Token Staking. For USD Staking, the formula is Baseline Yield x Multiplier, while for Parity Token Staking, the rewards are calculated as:

Parity Tokens received = (Amount staked x Duration x **Baseline Yield**) / Price per Parity Token.

The Baseline Yield is reviewed on a weekly basis and may change over time, but it’s designed to remain relatively stable to improve user experience. To achieve this, Parity employs smoothing and rounding techniques:

* **Smoothing**: Aims to keep the yield steady across short periods. For example, if the protocol earns 22% in week 1 and 18% in week 2, the Baseline Yield may be set at 20% for both weeks.
* **Rounding**: Focuses on simplicity, adjusting the yield to multiples of **5%** (e.g., **15%**, **20%**, **25%**) rather than using precise decimal figures like “18.73%.”

In its initial phase, Parity exclusively uses the **Hedged JLP strategy** to generate returns. The fees and resulting APY from the JLP pool are transparently reported by [Jupiter](https://jup.ag/perps-earn) and [Gauntlet](https://app.gauntlet.xyz/protocols/jupiter), providing users with clear insight into the protocol’s performance and reserve management strategy.

<figure><img src="../.gitbook/assets/SS 14.png" alt=""><figcaption></figcaption></figure>
