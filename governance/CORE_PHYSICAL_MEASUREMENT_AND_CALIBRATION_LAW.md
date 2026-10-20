# 🔬 CORE — PHYSICAL MEASUREMENT & CALIBRATION LAW (CANONICAL)

- **File:** `CORE_PHYSICAL_MEASUREMENT_AND_CALIBRATION_LAW.md`
- **Authority Level:** Binding Scientific Integrity Law
- **Status:** ✅ BINDING | ✅ NON-OPTIONAL (on ratification)
- **Enforcement Chain:**
  1. Stop Layer
  2. Constitution
  3. Experiment Integrity & Reproducibility Law
  4. Sensor I/O Safety Law
  5. this law
  6. CORE measurement services
  7. UI

## 1. Purpose

CORE produces computational measurements (sealed engine runs). This law governs the second kind of artifact CORE
handles: **physical measurements made with real instruments and compared against a frozen prediction**. It exists
so that a physical result inside CORE is as hard to fake as a computational one.

## 2. Ledger (enforced, one-way, no skipping)

Each step below must be completed before the next:

1. **PREDICTION_FROZEN** — the prediction is fixed, together with:
   - the observables;
   - the extraction method and its parameters;
   - the prediction value and its uncertainty, source and basis;
   - the comparison rule;
   - the environment envelope;
   - the capture plan.
2. **INSTRUMENTS_DECLARED** — every channel is declared with:
   - class, make, model and serial;
   - quantity and unit;
   - position, which must be within tolerance of the predicted sensor position.
3. **CALIBRATIONS_BOUND** — every channel is bound to an ACCEPTED, unexpired calibration record of the same serial.
   Geometry-tool and environment-sensor checks are bound too. A loop-back check is bound whenever CORE plays an
   excitation.
4. **ENVIRONMENT_RECORDED** — the readings must be inside the envelope. Otherwise the measurement is **held**, and
   the prediction is never adjusted.
5. **INTENT_FROZEN** — one identity binds everything above, together with the operator's sensor-use attestation.
6. **CAPTURED → VERIFIED → COMPARED** — the result is PASS / FAIL / INCONCLUSIVE, in a sealed receipt that is
   recomputed independently.

## 3. Custody

- The original bytes of every capture are kept and hashed (SHA-256).
- Raw data is never filtered, resampled, re-windowed or edited.
- Extraction happens only through the frozen method.
- Each take is captured once. A re-measurement is a new campaign.

## 4. Calibration records

- Calibrations are measured in situ with acceptance limits fixed in code, or taken from a certificate and labelled
  as such.
- Each record is sealed, carries a validity window, and is bound to one instrument serial.
- A record that is expired, unaccepted, edited, or bound to a different serial cannot be used.

## 5. Evidence separation

- Only instrument data may enter a physical measurement.
- Simulated data is the prediction side only. A "simulated measurement" is not a measurement.
- Synthetic test signals exist only for software self-tests, are labelled as such, and are never evidence.

## 6. Verdict semantics

- **PASS:** the frozen prediction survived one attempt at falsification under the declared conditions. It is not
  proof.
- **FAIL:** preserved as evidence.
- **INCONCLUSIVE:** the data could not support a verdict. Causes include calibration, environment, clipping, gaps,
  and an extraction that refuses. An INCONCLUSIVE result is never collapsed into PASS or FAIL.

## 7. Pre-registration amendments

- A method may change only before any physical capture exists for that benchmark.
- The change must be made as a sealed amendment that binds the frozen packet identity.
- Earlier versions keep their semantics.

## 8. Git is law

This law has authority only as committed in the governance repository.

## 9. Typed calibrations (owner decision, 2026-10-20)

A PHYSICAL measurement or physical benchmark run accepts ONLY sealed calibration records produced by the calibration
lab (measured in situ, or certificate-backed and labelled as such). Typed calibration declarations are refused for
physical runs; they remain permitted for clearly labelled simulated rehearsals, which are never evidence.

## 10. Hardware calibration hardening (amendment A7, ratified 2026-10-20)

Stricter-only additions. They never correct a measurement; they decide whether it may become evidence.

1. **Microphone channel match (T0.6).** Two microphones whose relative timing defines an observable are qualified
   together: one sealed take with the pair side by side (AB), one with the two swapped (BA), same inputs, gains and
   sample rate, within 2 h. Chain mismatch (d_AB + d_BA)/2 must be ≤ 1 µs; placement (d_AB − d_BA)/2 ≤ 20 µs.
   A physical Benchmark A run must bind an ACCEPTED record for exactly its two microphones on exactly its two inputs.
2. **Gain binding.** A sensitivity calibration holds only at the gain marking recorded in it. A channel or apparatus
   that declares a different gain, or none, cannot bind it.
3. **Post-session bracket.** Every channel calibrated with an acoustic calibrator is checked again after the last
   capture of the session (within 4 h; same serial and gain; |drift| ≤ 0.5 dB). A missing or failed check makes
   every observable using that channel INCONCLUSIVE, never PASS or FAIL.
4. **Benchmark A envelope.** The Benchmark A environment envelope is 18.0–20.5 °C and 30–60 % RH (pre-registration
   amendment v1.2). New physical runs use v1.2; v1 and v1.1 keep their semantics (§7).
