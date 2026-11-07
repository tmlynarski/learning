# Heat & Water: a boiler, air-handler and water-heater schematic

A single-file, offline teaching plate showing how an existing basement plant works together:
- an oil-fired cast-iron boiler (BLR-1)
- a hydro-air handler (AHU-1) with its outdoor condensing unit (CU-1)
- an indirect water heater (WH-1)

It shows every connection between the units, every valve and its type, the incoming water service, and everything that has to be exhausted or discharged.

Open `index.html` in any current browser. There are no dependencies or network calls.

## Source

The equipment data comes from an existing-equipment schedule built from nameplate data. The schedule records equipment, not piping. So the plate separates four kinds of information, and **Colour tags by → Where the information comes from** shows which is which:

| Tag style | Meaning |
|---|---|
| Solid border, schedule mark (e.g. `ZV-1`) | In the schedule |
| Amber (when coloured) | In the schedule, but marked TBD / tentative / "confirm on site" |
| *Dashed italic, terra* | Required by code or manufacturer, or the schedule says to add it, but not listed |
| *Dashed italic, grey* | Typical for an installation like this, not listed; an assumption |

## How to use it

- **Scenarios (keys 1–9).** Standby, Heating call, Hot-water call (priority), Hot-water draw, Cooling call, Make-up / fill, Warm-up & expansion, Purging air, and a Relief fault demonstration. Each one animates the flows that move, sets every valve to its state, and starts or stops the burner, circulator, blower, compressor and sump pump.
- **Valve states.** White = open, no flow. Black = closed. Pipe colour = open and flowing. Red = relief lifted. Hatched = unknown.
- **Hover anything** (mouse or trackpad). A tooltip shows the part's name and schedule mark, its valve type and current state, a one-line description of what it's for, and where the information comes from. Pipes show what they carry, whether they're flowing in this scenario, and where they run from and to. On touch screens, tap instead.
- **Click anything.** Pipes, valves, devices and equipment open in the Inspector, which shows the valve type and how it works, the schedule data, the proposed disposition, the schedule notes, and the runs it connects to.
- **Side tabs.**
  - Sequence: step-by-step sequence of operation, highlighting the parts involved.
  - Valves: the full valve schedule, plus a gallery of the valve types.
  - Connections: every run, from → to, with what's on it.
  - Water in · Exhaust out.
  - Field checks: what to verify on site.
- **Layers.** Typical/required parts, control wiring (typical logic, not traced), all tags. **Colour tags by → Proposed disposition** shows what remains, is replaced, is relocated, needs verification, or is added.
- **Keyboard.** 1–9 pick a scenario, Space pauses the animation, Esc clears the selection.

## What it is not

It is diagrammatic, not to scale, and not for construction:
- Pipe routes, tee locations and valve order are drawn to teach, not as-built.
- No pipe sizes are recorded apart from the 5/8 in. meter.
- The control wiring is the typical logic for a zone-valve hydro-air system; the schedule doesn't trace it.

Pressures and temperatures quoted in the text (12 psi fill, 30 psi relief, 150 psi / 210°F T&P, and so on) are standard residential values, not field measurements. The schedule's propane cylinder (LPT-1) isn't drawn, because nothing connects it to these units.

## Code organization

Everything is in `index.html`:
1. Vocabulary: piping systems, provenance, dispositions, valve-type explanations
2. Pipes: every run, points in flow direction
3. Components: schedule data and teaching text
4. Scenarios: flows, valve states, unit states, steps
5. SVG helpers and valve symbols
6. Plate construction
7. State and interaction
8. Panels

A self-test runs on load and logs to the console whether every cross-reference between pipes, components, scenarios and wiring resolves.
