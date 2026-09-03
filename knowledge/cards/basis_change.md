# Basis change

**What it is.** A basis change is the effect on the liability of changing the assumptions used to value it. The same policies, valued on new assumptions, produce a different number; that difference is the basis change.

**It always has a paper trail.** Assumption changes are approved and recorded in the assumptions register with an old value, a new value and a rationale. A basis change in the movement analysis without a matching register entry is itself a finding, and so is a register entry with no impact.

**The register holds this period only.** Every entry in the register belongs to the quarter under analysis, so there is no date test to apply: each change contributes to this period's `basis_change`. In a system covering several periods you would filter by effective date, and a change effective before the period would already sit in the opening liability.

**One total, several steps.** `movement.basis_change` is the total per cell. `basis_change_detail` splits it by assumption, applied as numbered steps in a fixed order. Individual step impacts depend on the order in which the changes were run; the total does not. Do not over-interpret small differences between steps, and do not assume the largest step is the only one: two changes can offset, leaving a small total that hides two material movements.

**Typical directions.** Raising expense inflation increases the liability (more future expenses to provide for). A mortality improvement on a protection product reduces the liability (fewer expected claims). Lowering a discount rate increases the liability.

**How to investigate.** Call `get_assumptions` for the product to see what changed, remembering that entries marked product `ALL` apply to every product. Then call `get_basis_change_impact` for the product with `assumption_id` blank, so each change's impact is returned separately. Report every change with its amount and share of the total, and check the total against the bucket in the movement summary.

**When to pull this card.** Whenever the register shows a change, or when `basis_change` is material, or when a basis-change total looks too small to be true.

**Related cards.** `liability_movement`, `residual_and_tolerance`.
