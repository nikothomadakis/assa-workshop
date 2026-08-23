# Liability movement investigation framework

Version 1.0. This document is the methodology. The agent follows it stage by stage. Editing this document changes how the agent investigates.

## Rules that apply throughout

- Every number you use comes from a tool. You never calculate, estimate, add, subtract or convert numbers yourself. If you need a number, call a tool that returns it.
- Record a finding after every stage with `record_finding`, before moving to the next stage. Findings are your memory; do not rely on the conversation.
- One call answers one question. If the next question needs a different tab, make the next call.
- Pull a reference card with `load_reference` when a concept is unclear. Do not guess at meanings.
- Use the `period` you were given for every call.
- Signs are impacts on the liability, not favourability. Do not call a negative variance "adverse" or a positive one "favourable".
- A finding can be "no cause identified". Never invent a cause.

## Materiality

A bucket is **material** if its absolute value exceeds 10% of the absolute total movement, or 1% of the opening liability. The tool output for the movement summary gives you both shares.

**Basis change is always investigated** if the assumptions register shows any change effective in the period, whether or not the bucket is material.

**Residual tolerance** is 0.5% of the opening liability.

## Stage 0 — Establish the headline

Call `get_movement_summary` for the product in the question (or the whole book if none). Record finding: opening, closing, total movement and its percentage of opening, each bucket's amount, the derived residual, and whether the balance-sheet reconciliation check passed.

## Stage 1 — Rank the buckets

From the Stage 0 output, list every bucket other than `expected_change` with its amount and its share of movement and of opening. Mark which are material. Record finding: the ranking and the material set. If nothing is material and there is no basis change in the register, go to Stage 4.

## Stage 2 — Locate each material bucket

For each material bucket, call `get_movement_by_segment` grouped by `cohort`, and again grouped by `age_band` if the cohort view is diffuse. A bucket concentrated in one or two cells is a signal; a bucket spread evenly across cells is a different kind of finding (a book-wide effect). Record one finding per material bucket stating where it sits and what share the driving cells carry.

## Stage 3 — Explain each material bucket

Use the source the bucket points to. Record one finding per explanation, stating the cause if the evidence supports it, or "no cause identified" if it does not.

**Experience variances** (`claims_variance`, `lapse_variance`, `expense_variance`):
1. `get_experience` for the driving cells and the relevant driver → expected, actual, ratio.
2. `get_product_spec` for the product → look for a recent change whose timing and affected policies match the driving cells.
3. If the spec does not explain it, `query_policies` on the driving cells to check counts and mix. If still unexplained, say so.

**Basis change**:
1. `get_assumption_changes` for the period and product → what changed.
2. `get_basis_change_impact` for the period and product → how much each change mattered.
3. Report **every** change with its impact and share, including small or offsetting ones. Check that the total in the detail matches the bucket. If the register shows a change with no impact, or an impact with no register entry, that is a finding.

**New business**:
1. `query_policies` filtered to entry dates in the period, grouped by `age_band` → count, total liability, average liability per new policy.
2. `query_policies` for the in-force book grouped by `age_band` → compare mix and average liability.
3. `get_product_spec` for a commercial cause (campaign, channel, pricing).

## Stage 4 — Reconcile

From the Stage 0 output: explained movement = sum of buckets; residual = total − explained. State the residual's amount and share of opening and whether it is within tolerance. If above tolerance, call `get_movement_by_segment` for the residual grouped by cohort to see if it concentrates, then stop. Record the reconciliation finding. Never attribute the residual to a cause without evidence.

## Stage 5 — Hand off

Confirm every stage has at least one recorded finding. Reply with a one-paragraph summary for the log: what you investigated, how many findings you recorded, and the finding IDs. Do not write the commentary; a separate step writes it from the findings.
