# Policy data

**What it is.** The `policies` tab is the full policy book at the closing date, one row per policy, with its product, entry-year cohort, age band, entry date, status, sum assured, annual premium and closing liability. Aggregates in the other tabs were built from this data.

**When to use it.** The cell-level tabs usually explain a movement. Drill into policy data when:
- you need to know *who* is behind a number (how many policies, what mix, what average size),
- you want to check a cause, such as whether excess lapses really sit in the cohort the spec points to,
- you need to confirm new business: policies with an entry date inside the period are the period's new business.

**What the fields mean.**
- `status` is the status at the closing date: `in_force`, `lapsed` or `claimed`. Lapsed and claimed policies carry zero closing liability.
- `liability` is the closing-date liability. Summed per cell it equals `movement.closing_liability`.
- `cohort` is the entry-year band; `entry_date` is the exact date.

**Never read rows.** Policy data is only ever accessed through `query_policies`, which returns counts, totals and averages per group. This keeps every number deterministic and logged.

**Reconciliation.** Policy liabilities per cell should equal the cell's closing liability in `movement` and in `liabilities`. A difference would be a data issue, not an experience finding.

**When to pull this card.** Before using `query_policies`, or when the question is about counts, mix or individual-policy size.

**Related cards.** `new_business_and_mix`, `experience_variance`.
