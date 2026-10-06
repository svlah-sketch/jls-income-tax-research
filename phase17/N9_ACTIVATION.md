# Activation of N9: holiday-home tax and personal income tax decisions

6 October 2026. This dated activation applies the optional N9 section of the protocol deposited in commit 850fdd384cb19345944b483fff81511eb85616e6. The original deposit and phase16 results remain unchanged. The author requested completion of feasible remaining analyses. No N9 outcome regression, FWL outcome bound or exposure/outcome association has been calculated before this activation.

The broader study is exploratory. N2 and budget-weight results are already known. Those results do not alter N9's previously specified variables, samples, tests or reporting rules.

## Exact implementation

The primary population is the positive-2023-surtax population excluding Zagreb and units with a zero holiday-home tax in both years. Its complete-data size is 269. The exact-change regression includes 240 units; the remaining 29 contribute interval outcomes to identification bounds. The separate all-positive-surtax sensitivity contains 301 units, 272 with exact changes. There are 19 counties in each design. The 32 zero-in-both-year units are also reported separately.

For each annual PIT band, g=max(1-t2024/min(t_R,c2024),0), t_R=t0(1+r/0.74). g is a fraction, so a 10-percentage-point increase in the relative shortfall corresponds to 0.1 times the regression coefficient. It is not a ten-point change in the statutory PIT rate. Each band has a separate model.

The outcome is the annual change in holiday-home tax in EUR per square metre. For interval entries it belongs to [L2024-U2023,U2024-L2023]. Exact means zero interval width to tolerance 1e-12. No midpoint is used.

Regressors, in order, are g, log2_population, income_index_10, unemployment_1pp, grants_10pp, holiday_10pp, old_surtax_pp, class24_small_city, class24_large_city, equalization23_10pp, and a full set of county indicators without another intercept. Default status is not an additional regressor: it is a simultaneous 2024 decision and not one of the original pre-reform covariates specified in N9. All eight matrices have rank 29 of 29. There is no outcome-dependent control or population selection.

The two primary exact-change slopes form Holm2. The two all-positive-surtax exact-change sensitivity slopes form a separate Holm2. CR2/Satterthwaite and restricted wild cluster-t use the frozen routines, 9,999 Rademacher draws, the common15 model-label hash seed and tie tolerance 1e-10. The conservative input is max(CR2 p,wild p). The wild label is the full model identifier plus '_gap_zero'. Report all coefficients, pointwise 95% intervals, Holm p-values and conservative Bonferroni2 95% intervals for the targets. No new directional test is added.

Interval outcome bounds use the FWL weight v=residual(g)/sum(residual(g)^2). Minimise and maximise sum(v*y) by selecting each outcome endpoint according to the sign of v, and verify the result with an independent linear program. They are sharp bounds over the product of the reported unit intervals for the given design, not confidence intervals, and receive no p-value. No interval-inference method is introduced. Exact-only regressions target their smaller population and are not silently generalized to the range-reporting units.

Working design precision, county leverage and inclusion audits have been saved before any outcome fit. The residual SD grid is {0.25,0.5,1,2} EUR/m2 with pointwise alpha .05 and Bonferroni planning alpha .025. This is not achieved CR2/wild/Holm power. Nonestimable slots would stay in the family with bookkeeping p=1.

## Prespecified descriptive fiscal magnitudes

Use census 2021 holiday-dwelling surface area from sheet '1.', column 'For vacation', in the surface-area row immediately following each already verified unit count row. Match the unit and county labels and check all 556 rows against the count linkage and the national area total. A dash is the source's zero symbol; no other missing value is recoded to zero.

For the primary 269 and all-301 populations report sums of area times the signed change intervals, and separately sums of area times max(change,0), with endpoints preserved. These are approximations based on census use, not legal taxable area or observed collections.

For a like-signed gross comparison use the frozen phase15 employee+pensioner, primary-final-tax-offset, w in [0.8,1] unit scenarios. Sum positive_shortfall_min/max over exactly the same units. The illustrative ratio is [gross holiday potential lower/PIT shortfall upper, gross holiday potential upper/PIT shortfall lower], only if the denominator lower bound is positive. This is an outer scenario range across different measurement concepts, not identified substitution or compensation collected. Report numerators, denominators and populations, including the fact that holiday area is from 2021 and PIT structure from 2023. It is descriptive and creates no extra hypothesis family.

Positive slopes are consistent with substitution, negative slopes with common tax preferences. Wide intervals permit neither conclusion. Simultaneous choices, endogenous PIT exposure, interval reporting, national ceiling changes and proxy tax bases preclude causal attribution. Holiday use identifies neither nonresident nor diaspora ownership.

## Frozen inputs

- `phase15/inputs/Porezna_kuce_za_odmor_2023_2024.xlsx`: `79ecd68982d9d418ede04f1a52f41324addfeae200064f408b8bcb50a442ac86`
- `phase7/recovered_phase1/raw/dzs_housing_2021_jls.xlsx`: `38e30ef2a383ecd10aa3dda8795ea907beb6483cc953c9cceef1a49f29afade5`
- `phase4/results/policy_database_enriched.csv`: `8b308a04d42208e3569e33531f1e39a45cf546ccf86f7884daf53455bb742a5e`
- `phase11/phase11b/results/decision_pair_unit_audit.csv`: `3dd1e1dea60194c380fc3b7d914ffdd42d3bf55c31ddf938bc7deecb43b2b1a3`
- `phase15/results/offset_money_unit_scenarios.csv`: `39da4f02334e46dfd5cde2e66ad2dd02d41f0faab6eaa57bbf65cbf6a801ef48`
- `phase16/common16.py`: `370f9ae8b8c7d70d178f6bc5acb2d25fb9b21d4cbc5e1ac5dbfd9d0dbd3d3ebe`
- `phase15/common15.py`: `152ce6819858cf178c4639dbb10cb25b7df88461461a16892d67d6c958d2d2a5`
- `phase13/common.py`: `1d7c7efbe29f089f2ca24b5cd2cf79d8282c36b973d00a0e754439bf1459e2b4`

Design-only lock saved (UTC): 2026-10-06T13:34:52.089462+00:00.
