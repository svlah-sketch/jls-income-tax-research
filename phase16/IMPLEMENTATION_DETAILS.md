# Phase 16: prospective numerical implementation details

The governing protocol is the unchanged public commit
`850fdd384cb19345944b483fff81511eb85616e6`, published 6 October 2026 at
12:31:36 UTC. All seven deposited files were verified by unauthenticated
retrieval and SHA-256 comparison before any new-family estimation.

This note fixes numerical details before first estimation. It adds no outcomes,
populations, controls, primary tests or optional N9 analysis.

- Model labels are `N2_employee_H_M`, `N2_employee_H_D`,
  `N2_employee_H_P`, their `N2_pension_...` counterparts, and
  `budget_A_low`, `budget_A_high`, `budget_B_low`, `budget_B_high`.
- Bootstrap seeds follow `common15.py`: 20261004 plus the unsigned little-endian
  integer in the first three bytes of SHA-256 of the model/test label. Suffixes
  identify coefficients, nulls and TOST boundaries. Draw counts and seeds are
  archived. Every equality comparison includes the fixed absolute-t tie
  tolerance 1e-10. Signed TOST tails use the corresponding signed tolerance.
- N2 TOST uses an upper-tail test at 0.85 and a lower-tail test at 1.15.
  The larger of these two p-values is taken within each method, followed by
  the larger CR2/wild value, and then Holm over the three tests. Signed wild
  tails are counted directly; a two-sided p-value is not blindly halved.
- Nonzero logit nulls use a fixed offset `gamma_star * log(b)` while all
  other coefficients are refitted. Existing C and S restricted score-bootstrap
  variants are retained; the larger bootstrap p-value and the CR2 p-value
  enter the prespecified conservative comparison. These are approximate
  working-linearization procedures, not exact small-sample logit inference.
- N2 working residual SDs remain {0.02, 0.03, 0.04, 0.05, 0.10}. Precision
  is shown at alpha 0.05 and the Bonferroni planning threshold 0.05/3.
  TOST planning power assumes the true slope is exactly one and integrates
  the central-normal coefficient error over a chi-square working variance
  estimate with the design CR2 degrees of freedom.
- Budget precision uses the previously saved finite-fit probabilities from
  phase 12, not probabilities fitted with the new log budget share. It shows
  residual SD multipliers {0.5, 1, 1.5, 2} around that working Bernoulli target,
  with alpha 0.05 and 0.05/4. Multiplier one is the principal working scenario.
  The separated A-higher population has no regular-model MDE or coefficient.
- All design and sample files are hashed in a local prospective design lock
  before the first new-family fit. Each first-fit event is logged, and earlier
  phases remain immutable. Primary family decisions and thresholds are not
  altered in response to precision or observed coefficients.

The old exploratory results and reviewer-provided facts remain prior knowledge.
This prospective record does not retrospectively preregister the entire study
and does not establish causality.
