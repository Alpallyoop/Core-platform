# ⚡ CORE ENGINE — ELECTROMAGNETIC GOVERNANCE (CANONICAL)

File: `verticals/electromagnetic/CORE_ELECTROMAGNETIC_ENGINE_GOVERNANCE.md`  
Engine Key: ELECTROMAGNETIC  
Engine Kind: TRUTH_ENGINE  
Authority Level: Engine Governance (Binding)  
Status: ✅ BINDING | ✅ NON-OPTIONAL  
Effective Date: First Public CORE Deployment  

---

## 1. Engine Role (Canonical)

ELECTROMAGNETIC is a deterministic electromagnetic **measurement** engine.

Its sole purpose is to produce sealed computational measurements for bounded,
low-order electromagnetic systems with analytic or closed-form behavior.

ELECTROMAGNETIC:
- produces primary measurement truth
- enforces analytic invariants at runtime
- emits replayable numeric artifacts

ELECTROMAGNETIC explicitly:
- does not interpret meaning
- does not classify outcomes
- does not predict real-world consequences
- does not act as a field solver

It is a governed measurement instrument, not a semantic, decision, or control system.

---

## 2. Governance Inheritance (Absolute)

ELECTROMAGNETIC is permanently bound by:

- `CORE_CONSTITUTIONAL_STOP_LAYER.md`
- `CORE_PLATFORM_CONSTITUTION.md`
- `CORE_ENGINE_REGISTRY_AND_VERTICAL_INHERITANCE_LAW.md`
- `CORE_GOVERNANCE_INDEX_CHAIN_OF_AUTHORITY.md`
- `CORE_EXPERIMENT_INTEGRITY_AND_REPRODUCIBILITY_LAW.md`
- `CORE_ENGINE_REGISTRY_CONTRACT.md`

If any conflict exists → CORE law prevails immediately and without exception.

---

## 3. Scope Boundary (Critical)

ELECTROMAGNETIC is restricted to analytic and low-order electromagnetic measurement primitives.

It must not implement:
- field solvers
- PDE-based evolution
- boundary-conditioned field propagation
- material-coupled EM field behavior

Those responsibilities are reserved exclusively for the MAGNETAR engine.

This separation is enforced by registry law and may not be bypassed.

---

## 4. Execution Lanes (Declared)

### Lane: `rc_discharge_v1`

**Purpose**  
Deterministic measurement of RC discharge behavior using closed-form physics.

**Declared Inputs**
- `R_ohm` (float, > 0)
- `C_f` (float, > 0)
- `V0_v` (float)
- `dt_s` (float, > 0)
- `T_s` (float, ≥ 0)
- optional tolerance parameters (numeric)

**Determinism Controls**
- fixed time step (`dt_s`)
- closed-form exponential decay
- no stochastic terms
- no runtime environment dependence

**Outputs**
- time-ordered voltage series `V(t)`
- derived parameter `τ = R · C`
- invariant evaluation report

### Lane: `analytic_magnetostatics_v1` (amendment A3, ratified 2026-10-20)

**Purpose**  
Closed-form magnetostatic measurement primitives: centred-dipole geomagnetic field (declared coefficient set),
total-field and vertical anomalies of uniformly magnetised sphere / horizontal cylinder bodies, electromagnetic skin depth.

**Determinism Controls**  
closed-form expressions only; no field solver, no PDE evolution, no boundary-conditioned propagation (those remain MAGNETAR's).

**Invariants**  
divergence-free and curl-free checks of the analytic field, dipole-limit and far-field decay ratios.

### Lane: `coupling_estimates_v1` (amendment A3, ratified 2026-10-20)

**Purpose**  
Order-of-magnitude analytic estimates of electromechanical / electrokinetic coupling (piezoelectric voltage from stress
in quartz-bearing rock with conduction relaxation; streaming potential from pore-pressure gradients). Outputs are
low / typical / high bands from declared parameter ranges, never point predictions.

### Lane: `gpr_primitives_v1` (amendment A4, ratified 2026-10-20)

**Purpose**  
Ground-penetrating-radar travel time, velocity and reflection-coefficient primitives from declared relative permittivity
and conductivity (closed form; no wave solver).

---

## 5. Invariants (Binding)

ELECTROMAGNETIC enforces analytic invariants on every run.

Declared invariants include:
- endpoint decay consistency
- exponential ratio consistency across sample pairs
- NaN / Inf exclusion
- parameter domain validity (`R > 0`, `C > 0`, `dt > 0`)

Invariant evaluation:
- executes every run
- is included in the output artifact
- is sealed with the run
- may not be suppressed, rewritten, or deleted

Invariant failure does not invalidate a run.
It is preserved as part of the measurement truth.

---

## 6. Output Contract

Each run emits exactly one `RUN_OUTPUT.json` containing:

- engine identity and version
- declared inputs
- generated numeric series
- derived parameters
- invariant report (`schema`, results, diagnostics)

Output artifacts:
- are canonicalized
- are hashed using SHA-256
- are sealed by CORE
- are immutable after sealing

---

## 7. Sealing & Replay Requirements

ELECTROMAGNETIC:
- does not self-seal
- emits seal-compatible artifacts only
- must tolerate byte-for-byte replay

Given identical:
- engine version
- declared inputs
- determinism parameters
- speed factor (where applicable)

→ output must be identical after canonical normalization.

Replay mismatch constitutes an integrity violation.

---

## 8. Prohibitions (Hard)

ELECTROMAGNETIC must never:

- access network resources
- fetch external data at runtime
- communicate directly with other engines
- infer intent, identity, or behavior
- classify objects or outcomes
- embed user, billing, or permission context
- mutate or reinterpret sealed artifacts
- emit side-channel or auxiliary outputs

Violation invalidates the engine.

---

## 9. Change Control

Any change affecting:
- governing equations
- invariants
- determinism guarantees
- output schema

requires:
- engine version bump
- governance review
- registry consistency
- auditable Git commit

Silent changes are forbidden.

---

## 10. Declaration

ELECTROMAGNETIC is a governed, deterministic electromagnetic measurement instrument.

It produces sealed, replayable numeric measurements suitable for audit and differential comparison.

Meaning, classification, and action are applied exclusively by CORE lenses, never by this engine.
