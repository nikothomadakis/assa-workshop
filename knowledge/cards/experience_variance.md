# Experience variance

**What it is.** Experience variance is the difference between what actually happened and what the assumptions said would happen, for one driver: claims, lapses or expenses. It exists in two forms in this system:

- as **counts** in the `experience` tab (expected vs actual claims, expected vs actual lapses, expected vs actual expenses in rand), and
- as a **liability impact** in the `movement` tab (`claims_variance`, `lapse_variance`, `expense_variance`).

The count tells you what happened; the rand amount tells you what it did to the liability.

**The actual-to-expected ratio.** Actual ÷ expected. A ratio of 1.0 means experience matched assumptions. A ratio of 2.0 means twice as many events as assumed. Ratios on very small expected counts (below about 5) are noisy and should be interpreted with care.

**Sign is not favourability.** The buckets are signed as impacts on the liability. In most products, more claims or lapses than expected *release* reserves, so the liability impact is negative. Whether that is good or bad for the insurer depends on the product and on what was paid out:
- Excess surrenders on a Savings product remove account values: the liability falls by roughly what was paid, so the net effect is close to neutral.
- Excess death claims on a Protection product release a small reserve but pay a large sum assured: the liability falls slightly, but the insurer has lost money.
- Expense variances barely touch the liability at all; their real effect is on profit, which is outside this analysis.

So a negative variance is not "adverse" and a positive one is not "favourable". Say what happened and what it did to the liability; leave favourability to the product context.

**How to explain a variance.** Locate it (which cells), measure it (the count ratio), then look for a cause outside the numbers: the product spec's recent changes, a campaign, a premium change, an operational event.

**When to pull this card.** When a `claims_variance`, `lapse_variance` or `expense_variance` bucket is material, or before interpreting a ratio.

**Related cards.** `liability_movement`, `product_specs`, `policy_data`.
