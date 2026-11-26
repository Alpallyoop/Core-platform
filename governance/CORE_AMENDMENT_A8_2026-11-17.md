# CORE — Amendment A8 (ratified 2026-11-17): Benchmark A v1.3, tube radius and analysis band

Ratified by: the owner, 2026-11-17 (decision B1: "v1.3 is required, with the canonical edits applied", approving
`docs/proposals/2026-11-17_BENCHMARK_A_DISCRIMINATION.md` in the core-platform repository).
Enforcement: binding from this commit ("Git is law"). Nothing in the Stop Layer or the Constitution changes.
Every item is **stricter only**: no threshold, geometry, frozen prediction or frozen estimator is changed. The ±1 %
threshold is unchanged. Decided before any physical capture.

| Id | Changes | Summary |
|---|---|---|
| A8-R1 | CORE_PHYSICAL_MEASUREMENT_AND_CALIBRATION_LAW §10.5; Benchmark A pre-registration amendment v1.3 | The tube's internal diameter is declared with its uncertainty; the radius minus its uncertainty must be at least 25 mm (refusals DIAMETER_UNCERTAINTY_REQUIRED, TUBE_RADIUS_BELOW_V1_3_MINIMUM). |
| A8-R2 | §10.5 | An analysis band is declared before capture: it starts at or above max(343.24 Hz, c/2L) and ends below 0.8 × the first cross-mode cut-on 1.8412 c/(2π r_max) (refusals ANALYSIS_BAND_REQUIRED, ANALYSIS_BAND_BELOW_FUNDAMENTAL, ANALYSIS_BAND_ABOVE_PLANE_WAVE). |
| A8-R3 | §10.5 | The measured energy-median frequency of the gated microphone-1 window must lie inside the declared band; otherwise the sound-speed observable is INCONCLUSIVE (BAND_NOT_MET), never PASS or FAIL. |
| A8-V | §10.4 | New physical Benchmark A runs use v1.3 ("v1.2 or later" in §10.4). v1.2 records stay verifiable as v1.2; v1, v1.1 and v1.2 keep their semantics for replay and rehearsal. |

Reason (SCREENING, `core/vv/bench_a_screening.py`): inside the v1.2 envelope, tube-wall boundary layers slow the
plane wave by about 0.10–1.02 % over 10–50 mm radius and 250 Hz–1 kHz (Kirchhoff 1868; Tijdeman 1975), so a perfect
instrument could fail the frozen band for a reason that is not the instrument. Under v1.3 the worst admitted
perfect-instrument case stays inside the band (tests/vv/test_bench_a_v1_3.py).
Sealed amendment: `physical_evidence/v1_3/BENCH_A_V1_3_AMENDMENT.json` (carries the v1.2 amendment identity).
