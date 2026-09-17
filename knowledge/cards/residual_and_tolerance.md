# Residual and tolerance

**What the residual is.** Residual = closing liability − opening liability − the sum of all named buckets. It is never stored; it is derived from the data. It represents the part of the movement that the analysis does not attribute to anything.

**Why it exists.** Real valuation systems have timing differences, data corrections, model refinements and rounding. A small residual is normal. A large one means something happened that the analysis has not captured.

**Tolerance.** A residual within 0.5% of the opening liability is within tolerance. It is still reported, with its amount and share of opening, but it needs no further work.

**Above tolerance.** Compare the absolute residual with 0.5% of opening liability. If it exceeds tolerance, flag it for further investigation and present it as unresolved for review. The supplied tools cannot break down the residual or independently reconcile it to the balance-sheet source. Identify the additional cell-level reconciliation evidence needed; do not request a residual breakdown from `get_movement`.

**The rule that matters most.** Never attribute a residual to a cause without evidence. A document asserting timing or rounding does not by itself establish a cause; it needs corroborating reconciliation evidence. "The residual is probably due to timing" is not a finding. "Residual of R15,000, 0.36% of opening, within tolerance, concentrated in Funeral, no cause identified" is a finding.

**Reconciliation line.** The explained movement (sum of buckets) plus the residual must equal the total movement. The commentary must state this line.

**When to pull this card.** At the reconciliation stage of every investigation.

**Related cards.** `liability_movement`, `basis_change`.
