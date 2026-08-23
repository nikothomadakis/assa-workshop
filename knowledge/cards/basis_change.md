# Basis change

**What it is.** A basis change is the effect on the liability of changing the assumptions used to value it. The same policies, valued on new assumptions, produce a different number; that difference is the basis change.

**It always has a paper trail.** Assumption changes are approved and recorded in the assumptions register with an old value, a new value, an effective date and a rationale. A basis change in the movement analysis without a matching register entry effective in the period is itself a finding.

**Effective dates are the join.** Only assumption changes whose `effective_date` falls inside the period (after the opening date, up to and including the closing date) contribute to this period's `basis_change`. A change effective before the period is already in the opening liability; a change effective after the period, including proposals that are not yet approved, is not in this period at all.

**One total, several steps.** `movement.basis_change` is the total per cell. `basis_change_detail` splits it by assumption, applied as numbered steps in a fixed order. Individual step impacts depend on the order in which the changes were run; the total does not. Do not over-interpret small differences between steps, and do not assume the largest step is the only one: two changes can offset, leaving a small total that hides two material movements.

**Typical directions.** Raising expense inflation increases the liability (more future expenses to provide for). A mortality improvement on a protection product reduces the liability (fewer expected claims). Lowering a discount rate increases the liability.

**How to investigate.** Get the register entries effective in the period; get the impact per assumption; report each one with its amount and share of the total, and say whether the total is consistent with the register.

**When to pull this card.** Whenever the register shows a change in the period, or when `basis_change` is material, or when a basis-change total looks too small to be true.

**Related cards.** `liability_movement`, `residual_and_tolerance`.
