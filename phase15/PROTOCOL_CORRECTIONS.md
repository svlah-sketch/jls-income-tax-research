# Phase 15: correction and descriptive reconstruction rules

Date: 2026-10-06. This is a correction plan, not a preregistration. Review files 13 and 14 supplied the headline offset counts, election aliases, and several sensitivity results before this file was written. Their discovery is attributed to the reviewer. Prior phases remain immutable.

## Legally defined accounting coverage

The co-primary fixed-base calculation uses A = employee withholding + pension withholding + other-income tax, and F = capital tax + property-rights tax, after dividing reported 2023 tax-and-surtax by (1+r). The other-income prepayment follows the local lower rate (NN 114/2023-1609, Art.17). The final-tax multiplier is 1.2 (Arts.24,28). This is a reporting-scope approximation, not deduplicated final liability. Business-book tax is excluded because the source explicitly permits overlap with employment. Mixed occasional-work/property income is excluded from primary F and added only in a 1.0–1.2 multiplier envelope, because the tourist-bed flat tax did not necessarily rise by 20%. Treasury-bill exemptions and changed bases are limitations. Repeat on 2022 reporting amounts converted at 7.53450 HRK/EUR; this holds the 2023 surtax reference fixed and is composition sensitivity, not observed 2022 policy revenue.

For annual base A, final base F and multiplier m, old receipts are (a+r)(A+F), new receipts a(kA+mF). Thus k_R = 1+r/a+(F/A)[r/a-(m-1)]. Burden reference k_B = 1+r+(F/A)[r-(m-1)]. Set a=.74. Mixed scope extends the same additive identity category by category. No clipping of a reference to the statutory minimum: an algebraic reference below the legal minimum is labelled separately; it is automatically attainable. Eligibility requires r>0, an applicable band decision, and k_R*t0 <= the legal maximum. Report all eligible and, separately, exclude cases k_R<=1; do not erase their contribution from the primary count.

Suppressed tax cells are intervals [0,R], R = published total minus all disclosed nonnegative tax categories. When several categories are suppressed, their allocations share one residual constraint; enumerate simplex vertices, do not allocate the full residual to every missing category simultaneously. Never impute a missing cell as an observed zero. Report certain and possible classifications when intervals cross a threshold. Threshold tolerance is 1e-9 percentage points; .1 percentage point is a separately labelled sensitivity.

Money: employee+pension annual tax is the headline reporting scope, with the primary final-tax offset F. Report w=1, common w in [.8,1], unit-specific w in [.8,1], and unrestricted unit-specific w in [0,1]. Bounds on w are assumptions about liability shares, never inferred from bracket headcounts. Other-income annual tax and potentially overlapping business tax are separate sensitivities. Money is signed old-minus-new receipt, with positive shortfall and unavoidable ceiling loss separately labelled. A common 1% collection fee leaves rate references unchanged and scales gross amounts by .99, conditional on common application. Reconcile using direct receipt arithmetic and independent rational threshold calculations.

## Election corrections and existing-model corrections

Match aliases only within the same unit, supported by official continuity records: Mače 248, Konjščina 200, Donji Kukuruzari 83. Preserve all other sample and model rules. Rerun the original O2 families and all coefficients; add a clearly post hoc contested-in-both-years sensitivity. Report actual residual-SD planning MDE alongside the original unconditional-SD convention. Election exposure is the initial 2024 schedule; quantify change before 18 May 2025. Do not describe it as election-date exposure.

Keep the original 2025 O5 exposure max(t2024-c2025,0). Correct its documentation and use t2024 in the mechanical-envelope denominator. For 2025 calibrated ratios, match both reduced-form and effective-rate horizons to 2023–2025. Describe the ratio as an algebraic Wald scale with an invalid exclusion restriction, not an identified elasticity. Confine it to the supplement. Stable bootstrap ties use tolerance 1e-10 in |t|; exact Rademacher enumeration is used when fewer than ten nonzero score clusters suffice.

## Descriptive extensions and source audits

Inspect the 31 single-national-band 2024 decisions and four multiple-reference entries in the Official Gazette; code each band's explicit setting, amendment, or statutory default and preserve evidence. Audit the 2025 changes band by band. Codes: P1 unchanged valid earlier local decision; P2 new decision effective 1 January; P3 timely new March decision in a band compelled by Article 14; P4 timely March decision in an already compliant band; P5 out-of-range band replaced in the register by national rate under the 7 March notice with no applicable timely NN decision; P6 unchanged national statutory default. Ambiguous source evidence is UNRESOLVED, never silently a local choice.

Describe 2021 surtax changes only, with the simultaneous .60→.74 retained-share reform and selective 318-unit coverage. Describe a 2x2 lower/higher annual-reference attainment table and off-diagonal units; no shape hypothesis test. Describe 2025 removed room with E=(t24-c25)+, W=(min(tR,c24)-c25)+, X=(t24-max(c25,min(tR,c24)))+, M=W+X. Then 0<=E<=M. Report legal-band rate points and tax-weighted E/M with fractional-linear endpoint optimization over w; distinguish M=0 as undefined. Do not sum separate endpoint ratios.

## New hypothesis families

N2, budget-weighted stakes, and optional N9 require a separate public timestamped protocol before first estimation under review 13. They are not licensed by this corrections file. No new regression from these families will be estimated before that requirement is met. N3, N5, N8 and the active-national-rate logit are not estimated, following review 14. The already disclosed six-city-exclusion stake sensitivity is a post hoc correction, not a new confirmatory family.

## Transparency

Stake gradients and 9/12% bins were known before phase12; preliminary .59/.79 correlations before O5; O2 followed O1's failed gate after a separate author decision. Earlier lock times were reconstructed from session records after original bytes were lost. Holm adjustment does not convert these analyses into confirmation. Keep original failures at p=1 in their original family. Archive code, inputs, source excerpts, outcomes and verification without overwriting previous versions.
