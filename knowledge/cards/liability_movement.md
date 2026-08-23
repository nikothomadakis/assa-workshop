# Liability movement analysis

**What it is.** A liability movement analysis (also called an analysis of change or a roll-forward) explains how a liability got from its opening value at one valuation date to its closing value at the next. The total change is split into named buckets, each of which has a cause you can point to.

**The buckets used in this system.** Every bucket is a signed amount: its contribution to (closing − opening).

| Bucket | What it captures |
|---|---|
| `expected_change` | What the opening assumptions predicted would happen: discount unwind, expected claims, expected lapses, expected expenses and premiums received. This is the baseline and is not investigated further. |
| `claims_variance` | Actual claims differing from expected, converted to a liability impact. |
| `lapse_variance` | Actual lapses or surrenders differing from expected, converted to a liability impact. |
| `expense_variance` | Actual maintenance expenses differing from expected. Usually small in liability terms. |
| `basis_change` | The effect of changing assumptions during the period. Always has a paper trail in the assumptions register. |
| `new_business` | Liability added by policies written during the period. |
| `residual` | Whatever is left: closing − opening − all buckets. Never stored; always derived. |

**Why it matters.** The analysis is how an actuary checks that the liability moved for reasons they understand. A bucket that is large and unexplained is a problem; a residual that is large is a bigger one.

**How it is organised here.** The book is split into cells: product × entry-year cohort × age band. Every bucket is available per cell, so a movement can be located ("which cohort drove it?") before it is explained ("why?").

**Materiality.** A bucket is material if it exceeds 10% of the total movement or 1% of the opening liability. Basis change is examined whenever the assumptions register shows a change effective in the period, regardless of size, because it is a governance item.

**When to pull this card.** At the start of any movement question, or when unsure what a bucket means.

**Related cards.** `experience_variance`, `basis_change`, `new_business_and_mix`, `residual_and_tolerance`.
