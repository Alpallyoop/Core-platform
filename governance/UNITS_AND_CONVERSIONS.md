# 📏 CORE — UNITS & CONVERSIONS (CANONICAL V1)

Authority Level: Binding Platform Spec
Effective Date: First Public CORE Deployment
Status: ✅ LOCKED | ✅ BINDING | ✅ NON-OPTIONAL

## 1) Canonical Units (Mandatory)
All engines MUST emit unit-tagged quantities using these canonical units:

### Atmospheric
- Wind speed: m/s
- Rain rate: mm/hr
- Snow rate: mm/hr SWE (Snow Water Equivalent)

### Distance & Geometry
- Distance: meters (m)
- Scaling factor: distance_scale_factor ∈ {0.25, 0.50, 0.75, 1.00}

### Time
- Seconds (s)

### Temperature
- Kelvin (K) canonical

### Frequency
- Hertz (Hz)

### Pressure
- Pascal (Pa)

### Energy / Power
- Joule (J)
- Watt (W)

## 2) Display Conversions (Allowed, Not Canonical)
Engines MAY include display conversions in an explicit display block, but canonical MUST remain present:
- Wind: mph, kph display allowed (canonical remains m/s)
- Distance: feet/miles display allowed (canonical remains meters)

## 3) Unit Tagging Rule (Mandatory)
Every numeric output MUST be accompanied by:
- value
- unit
- (optional) reference_frame

Example:
{
  "wind_speed": { "value": 12.4, "unit": "m/s" }
}

## 4) Dual Tagging (Amendment U1, ratified 2026-10-20)
Declared / field units (e.g. ft, uGal, degC, km, h) MAY be kept in saved outputs, but never instead of the canonical unit.
Every numeric output (scalar or array) is therefore carried as:

{
  "gravity_change": { "value": 12.0, "unit": "uGal", "canonical": { "value": 1.2e-07, "unit": "m/s^2" } },
  "air_temperature": { "value": 21.0, "unit": "degC", "canonical": { "value": 294.15, "unit": "K" } }
}

- canonical = SI coherent unit; temperature in kelvin; plane angle in radian; logarithmic units (dB) carry no SI conversion
  and are marked "convertible": false;
- when the canonical value equals the value (scale 1), "canonical": { "unit": ..., "equals_value": true } is permitted;
- where an engine's raw output cannot be changed (frozen lanes), CORE attaches the dual-tagged view as a sealed,
  hashed CORE artifact next to the verbatim engine output, and the verifier recomputes it;
- a numeric output whose unit cannot be resolved is a sealing failure (UNITS_UNDECLARED), never silently accepted.
