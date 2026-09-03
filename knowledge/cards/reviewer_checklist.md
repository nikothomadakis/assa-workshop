# Reviewer checklist

Used by the person deciding whether to approve the findings presented in the review form. Approving is a
professional act: you are the control, and after you click Approve the findings are recorded as approved
under your decision. Work the list before you decide.

A checklist nobody is required to work is not a control. If you cannot answer an item, that is a reason
to send the work back, not a reason to approve and hope.

## The seven checks

1. **Every number names its tool.** Each figure is presented with the tool that produced it and the
   arguments passed. A figure with no tool beside it has no provenance — send it back.
2. **Derived numbers show their working.** Where the Calculator was used, the inputs, the operation and
   the source tool of each input are shown. `57%` is not evidence; `1,968,679 / 3,436,957 = 57%, both
   from get_movement` is.
3. **Every material bucket is handled.** Each bucket meeting the materiality rule has either a stated
   cause with a source, or an explicit statement that no cause was identified. Silence on a material
   bucket is the most common real failure.
4. **Basis change is disaggregated.** Every register entry for the product is reported with its own
   impact, including small and offsetting ones, and the sum of the impacts is reconciled to the
   `basis_change` bucket. A single net figure is not enough: a small total can conceal two larger changes
   pulling in opposite directions.
5. **Each cause is attributable, not plausible.** For every cause, ask *which document says this, and do
   its timing and affected policies match the cells that were measured?* A cause that merely sounds
   reasonable — "likely a distribution or premium event" — is an inference presented as a finding.
   Send it back.
6. **The residual is reported as a residual.** Stated with its amount and share of opening, marked within
   or above tolerance, and **not** attributed to a cause unless a source states one. "Due to timing" and
   "rounding" are the two phrases to hunt for; neither is a cause without evidence.
7. **The reconciliation holds and is stated.** Opening + explained movement + residual = closing, written
   out, with the numbers.

## Two questions the checks do not cover

Ask them anyway, because nothing in the system enforces them:

- **Was the analysis actually re-derived?** The execution log lists every tool call. A run that presents
  conclusions without the calls behind them recalled them from somewhere else.
- **Was the premise sound?** Every tool call can be legitimate and the investigation still be answering a
  question that a document planted. If a cause traces to prose, read the prose.

## Deciding

- **Send back** if any of the seven fails. Say which item failed and what you want done — the agent gets
  your feedback verbatim and re-presents everything, so specific feedback ("quantify the lapse A/E for
  the driving cohort and cite the spec line") gets specific work.
- **Approve** only when all seven pass. Your approval is the record that they did.

**Related cards.** `residual_and_tolerance`, `basis_change`, `liability_movement`.
