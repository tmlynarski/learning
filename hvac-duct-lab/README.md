# Air in Motion: an interactive HVAC ductwork laboratory

A single-file, offline teaching application. It is an animated engineering plate of a four-room supply system: an air handler in section, a reducing rectangular trunk, four branches, dampers, fittings, registers, and an optional return path. Every number on screen comes from a real network solution of the system.

Open `index.html` in any current browser (Chrome, Edge, Safari, Firefox). There are no dependencies, fonts, CDNs or network calls. Your configuration is saved in the browser's localStorage.

## How to use it

- **Click anything in the drawing.** Ducts, takeoff collars, damper blades, elbows, reducers, boots, registers, rooms, junction nodes, the filter, coil, blower and plenum all open in the Inspector. It shows what the component does, its calculated properties and equations, and controls for its editable parameters. Unrelated parts of the drawing dim.
- **Mode A, fixed airflow.** You impose the airflow and the model reports the pressure needed to move it. Branch flows can be held at the room targets (ideal balance; the critical path sets the plenum pressure and the other branches show the surplus their dampers must absorb) or split by branch resistance. A warning appears when the requirement exceeds what the illustrated blower can develop.
- **Mode B, fan-driven.** A fixed-speed blower curve meets the system resistance curve, and airflow is the result. Closing a damper, shrinking a duct or loading the filter reduces the total and redistributes the branch flows. An illustrative constant-airflow (ECM-style) control is included, with a modeled speed limit.
- **Instruments** (below the plate): instrument cluster, velocity gauge, room delivery bars, fan and system curves with the operating point, pressure budget by component, the pressure grade line (total vs static, with static regain marked), velocity vs area at constant flow, and friction rate vs velocity.
- **Side tabs:** eight guided Lessons (predict, set up, change, explain, with a "Show the mathematics" panel), Fittings laboratory with cutaways and the sharp-vs-smooth elbow comparison, Register laboratory, Sizing methods (velocity, equal friction, static regain, available static pressure, total effective length, critical path), Design & Construction, Assumptions, and Tests.
- **Toolbar:** presets A–F plus the Lesson 8 starting system, Undo/Redo, Reset, layer toggles (return air, dimensions, data tags), JSON export/import, and Print (a landscape, print-friendly study).
- **Keyboard:** Space pauses or resumes the particles, Ctrl/⌘-Z undoes, Ctrl/⌘-Shift-Z redoes, Esc clears the selection.

## The model

**Air and units.** Standard air is fixed: ρ = 0.075 lb/ft³ and ν = 1.64 × 10⁻⁴ ft²/s. Velocity pressure is Pv = ρV²/2, which for standard air is (V/4005)² in. w.g. with V in FPM. All pressures are in in. w.g., referenced to room air = 0 (gauge).

**Geometry.** Rectangular area A = w·h/144; round A = π(D/12)²/4. Q = A·V throughout.

**Straight duct.** Darcy–Weisbach, ΔP = f·(L/D)·Pv. The friction factor uses the Swamee–Jain approximation of Colebrook, with ε = 0.0003 ft for galvanized and 0.003 ft for flex. Laminar flow uses 64/Re, with a linear bridge between Re 2,300 and 4,000. A fixed-f option is available in the Assumptions tab.

**Rectangular duct.** Uses the hydraulic diameter Dh = 4A/P with the actual mean velocity. This is approximate because of corner secondary flows, increasingly so above about 4:1. The Huebscher equal-friction diameter is shown for reference. Results are close to, but not the same as, published friction charts.

**Fittings.** Each fitting uses ΔP = K·Pv with one constant K, referenced to a stated velocity. All K values are illustrative and editable per installed fitting. They are not ASHRAE, SMACNA or manufacturer values, and real junction losses depend on the flow split.

**Dampers.** K(θ) comes from an illustrative log-interpolated table. A closed damper is a very large K, so only leakage passes.

**Filter and coil.** ΔP = ΔP₁₀₀₀·(Q/1000)ⁿ, with n = 1.5 for the filter and 1.8 for the coil (illustrative exponents).

**Fan.** Both curves are hypothetical:
- Curve A is a blower-assembly curve that excludes the filter and coil.
- Curve B is an ESP-table-style curve that includes a wet coil and a clean filter. Only resistance above those rated values is added, so nothing is counted twice.
- Speed changes follow the fan laws, P(Q, n) = n²·P₀(Q/n).
- Manufacturer-style data can be imported as JSON from the Air handler inspector, in this form: `{"name":"…","basis":"…","includes":{"filter":false,"coil":true,"coilRef":0.25},"points":[[0,0.9],[400,0.85],…]}`

**Network solver.**
- Unknowns are the four room flows and the plenum pressure. Each room path's losses must equal the plenum pressure, and the system is closed either by the fan curve (Mode B) or by the imposed total (Mode A).
- It is solved by damped Newton–Raphson with a finite-difference Jacobian.
- Trunk flows are sums of the downstream room flows, so continuity holds exactly at every junction.
- Reverse flows are rejected. If the solver fails, the last valid state stays on screen with an error message; no values are made up.

**Visualization.** On-screen particle speed is 115 px/s × (V/1000 FPM)^0.75. At each takeoff, particles are routed in proportion to the solved flow split. This is a visualization of calculated flow, not real-time air speed. The drawing is schematic and not to scale; branch lengths are given by the dimension strings.

## What is simplified or not modeled

The following are not modeled:
- duct leakage and heat gain or loss
- fan system effect
- altitude and temperature corrections
- flow-ratio-dependent junction coefficients
- door undercuts and transfer paths
- acoustics
- register throw (shown qualitatively only)

Velocity "caution thresholds" are adjustable teaching aids, not codes, standards or manufacturer limits. No costs are shown because there is no cost database.

This is an educational tool, not a design procedure. A real design needs room loads (e.g. ACCA Manual J), equipment selection with real blower tables (Manual S), duct design by an established method (Manual D, ASHRAE), tested fitting data, construction to SMACNA and code requirements, manufacturer data for terminal devices, and field testing, adjusting and balancing.

## Validation

The Tests tab runs automatically on load and can be re-run at any time. It covers:
- the ten required checks (velocities, monotonic behavior, continuity at every junction across six system states, damper response, fan/system intersection, display consistency, invalid-input handling)
- seven extra checks (velocity pressure, fan laws, ECM limit, critical path, static regain, explicit solver failure, sanitizing imported files)

All 17 pass.

**Note on required test 3.** A 10-inch round duct has an area of 0.545 ft², so at 1,000 CFM it runs at about **1,833 FPM**, not 1,467 FPM. The 1,467 FPM figure corresponds to 800 CFM in the same duct (or to about an 11.2-inch duct at 1,000 CFM). The test checks both and the app uses the physically correct value.

## Code organization

Everything is in `index.html`, in labeled sections:
1. Default system data
2. Geometry and unit conversions
3. Airflow and pressure engine
4. Network solver
5. SVG illustration
6. Animation
7. Application state and input handling
8. Charts
9. Educational content
10. Validation tests

The engine (sections 1–4) is pure functions with no DOM access, and the drawing never feeds back into the calculations.
