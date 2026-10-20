# CORE — Amendment A7 (ratified 2026-10-20): hardware calibration hardening

Ratified by: the owner, Alec Maiatico, 2026-10-20 ("set these up now", approving P1–P4 of
`docs/proposals/2026-10-20_HARDWARE_CALIBRATION_HARDENING.md` in the core-platform repository).
Enforcement: binding from this commit ("Git is law"). Nothing in the Stop Layer or the Constitution changes.
Every item is **stricter only**: no threshold, geometry, frozen prediction or frozen estimator is changed.

| Id | Changes | Summary |
|---|---|---|
| A7-P1 | CORE_PHYSICAL_MEASUREMENT_AND_CALIBRATION_LAW §10.1; SIGNAL lane `measurement_phase_slope_delay_v1` | Microphone channel match (T0.6): two sealed takes (AB, then the pair swapped: BA); chain mismatch = (d_AB + d_BA)/2 must be ≤ 1 µs and placement (d_AB − d_BA)/2 ≤ 20 µs. Required by physical Benchmark A runs as a qualification gate, never as a correction. |
| A7-P2 | §10.2 | A microphone sensitivity calibration is valid only at the gain marking it was made at; binding refuses a different or undeclared gain. |
| A7-P3 | §10.3 | Each acoustic-calibrator channel is bracketed by a post-session calibrator check: after the last capture, within 4 h, same serial and gain, drift ≤ 0.5 dB. Otherwise every observable using that channel is INCONCLUSIVE. |
| A7-P4 | §10.4; Benchmark A pre-registration amendment v1.2 | Benchmark A environment envelope narrowed to 18.0–20.5 °C (RH 30–60 % unchanged). New physical Benchmark A runs must use v1.2; v1 and v1.1 keep their semantics for replay and rehearsal. |

Reason: the frozen sound-speed prediction (343.2368 m/s, 1 % threshold) matches real air near 19 °C; inside the
former 18–25 °C envelope air alone is up to 1.18 % off (Cramer 1993). The 1 % budget is 5.8 µs of mic-to-mic delay.
Gain and calibration drift were recorded but not enforced.
