# Withdrawals

## Pending Withdrawals

Once you've unstaked and confirmed the transaction in your wallet, your request will appear in the **Pending Withdrawals** tab. Withdrawals are completed over a **48-hour period** and follow a clear, three-stage process — described below and illustrated in the app interface.

#### Withdrawal Timing

Withdrawals are **batched daily**, with **midnight UTC** as the cutoff.

* Requests submitted **before midnight UTC** will be **claimable at midnight UTC the next day** — i.e., settled in **\~24 hours**
* Requests submitted **after midnight UTC** are included in the next batch — and become **claimable in \~48 hours**

{% hint style="info" %}
**Example:**

* If you unstake at 11:59 PM UTC, your withdrawal will be claimable in 24 hours
* If you unstake at 12:01 AM UTC, it will be claimable in 48 hours
{% endhint %}

Actual unstaking duration ranges from **24 to 48 hours**, depending on when your request enters the batching window.

<figure><img src="../.gitbook/assets/Withdrawals.png" alt=""><figcaption></figcaption></figure>

**1. Stage 1 — Pending (0–24 hours)**\
This is the initial stage of the withdrawal period. During this time, your request is still **cancelable**. If you change your mind and want to continue staking, simply click the **"Cancel"** button. There is no fee for cancelling a withdrawal request. And your unstaking fee will also be returned in full.  &#x20;

**2. Stage 2 — Committed (24–48 hours)**\
Once the first 24 hours have passed, your withdrawal request becomes **locked**. It can no longer be canceled, and your funds are now in the final settlement window.

**3. Stage 3 — Claimable (after 48 hours)**\
When the full 48-hour period is complete, your withdrawal becomes **claimable**. The **"Withdraw"** button will activate, allowing you to transfer your SOL or USDC back to your wallet.
