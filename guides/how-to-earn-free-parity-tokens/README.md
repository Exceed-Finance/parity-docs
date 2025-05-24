# How to Earn Free Parity Tokens

{% hint style="info" %}
PT Staking refers to Parity Token Staking. Stake your PUSD to earn **free Parity Tokens**.&#x20;
{% endhint %}

## Start PT Staking

The only way to acquire **Parity Tokens** is by staking PUSD through the Parity protocol at [app.parityusd.fi](http://app.parityusd.fi). Below is a guide to help you navigate the interface and explain how the staking process works:

<figure><img src="../../.gitbook/assets/SS 3.png" alt=""><figcaption></figcaption></figure>

1. **Connect Wallet**\
   Before connecting, you will be prompted to accept Terms of Service if you haven't already done so.
2. **Stake Amount**\
   Here, you input the amount of PUSD you wish to stake to be rewarded in free Parity Tokens.
3. **FDV Levels**\
   This section displays the current Fully Diluted Valuation (FDV) at which Parity Tokens will be awarded. The starting FDV is $50M, and it increases in $10M increments, reaching $100M.
4. **Token Distribution**\
   At each FDV level, only **75 million Parity Tokens** will be distributed as rewards. Once the available tokens at a given FDV level are fully allocated, the FDV moves to the next level. This scaling ensures that rewards are tied to the protocol's TVL growth.
5. **Staking Options**\
   Here, you can toggle between two staking options: **PT Staking** to earn free Parity Tokens or **USD Staking** to earn rewards in USDC. Simply choose your preferred option before proceeding.
6. **Tab Switching**\
   This toggle allows you to switch between the **Stake** tab and the **Mint-Redeem** tab. If you're done staking, you can move back to minting or redeeming PUSD.

## Staking is Active

Once you begin PT-staking your PUSD, a detailed summary window will appear on the right side of the main interface, displaying key information about your staking activity:

<figure><img src="../../.gitbook/assets/SS 4 (2).png" alt=""><figcaption></figcaption></figure>

1. **Amount Staked**\
   This number shows how much PUSD you are currently staking.
2. **Parity Tokens Earned**\
   This figure displays the amount of Parity Tokens you’ve accumulated so far. For a detailed explanation of how Parity Tokens are calculated, see the "How Awards are Calculated" section.
3. **Baseline Yield**\
   This value represents the current yield of the protocol, which is a crucial factor in calculating your Parity Token rewards. It is conveniently displayed to help you track your staking performance.
4. **Current FDV Level**\
   Here, you can quickly check the active FDV level that determines the valuation at which Parity Tokens are awarded.
5. **Staking Duration**\
   This shows how many days you’ve been continuously PT-staking.
6. **Unstake Amount**\
   When you wish to unstake your PUSD, enter the amount here. You can withdraw any portion or the entire amount of your staked PUSD.
7. **Unstake Button**\
   Clicking this button will trigger the unstaking process. Once confirmed in your wallet, the transaction is completed instantly. Your principal is returned in full, with no fees, lock-ups, or cooldown periods. Additionally, you keep all Parity Token rewards, even if you staked for a short amount of time.

## How Rewards are Calculated

Parity Token Rewards are accumulating according to the following formula:

> #### Amount of free Parity Tokens user receives = (Amount PUSD staked x Duration x Baseline yield)     / Price per Parity Token.

#### Example

A user stakes $100k for 6 months. During this entire period, the Baseline yield, which is the yield the Protocol is making on its reserves and is conveniently displayed at the top of the tab in “3” (see the previous section), has been 20%.

Amount of Tokens user receives = $100k x 0.5 (6/12 months) x 20% / Price per Token.

Parity Tokens have a fixed supply of 15bn tokens (see Parity Token tab for more). The Price per Parity Token for a given FDV can be easily determined as FDV / Total Token Supply.

If you had been staking whilst the FDV was still at $50m, the effective token price at which you will be rewarded with Parity Tokens is: $50m / 15bn token supply = $0.00333 price per token.

To complete our example, the amount of Parity Tokens you will have been continuously accumulating over this 6 months staking period, will add up to:

$100k x 0.5 x 20% / $0.00333 = 3m Parity Tokens

This means the user will have earned $10,000 worth of rewards, effectively at an FDV of $50m.&#x20;

## Price Per Token

The following table presents price per Parity Token for various FDV levels:

| FDV at This Price Level | Token Price at This Level |
| ----------------------- | ------------------------- |
| 50 $m                   | 0.0033 $                  |
| 60 $m                   | 0.0040 $                  |
| 70 $m                   | 0.0047 $                  |
| 80 $m                   | 0.0053 $                  |
| 90 $m                   | 0.0060 $                  |
| 100 $m                  | 0.0067 $                  |

For context, comparable protocols like **Ethena** and **Jupiter** currently have token prices of $0.34 and $0.78, respectively—**100-200x** higher than Parity Token's price at current levels.

{% hint style="info" %}
**Vesting:** Post TGE, there will be a one-year cliff, followed by a 3-year daily linear vesting schedule.
{% endhint %}
