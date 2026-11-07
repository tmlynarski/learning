# Sun & Current: a Florida home solar and battery wiring plate

A single-file, offline teaching plate showing how a typical Florida residential solar system is wired, with or without battery storage:
- an 8.0 kW DC rooftop array (20 × 400 W modules in two rows)
- a 7.6 kW string inverter with module-level rapid-shutdown devices, **or** 20 microinverters with an AC combiner
- optionally, a 13.5 kWh battery (DC-coupled to a hybrid inverter, or AC-coupled with microinverters) and a whole-home backup gateway
- the PV AC disconnect, rapid-shutdown initiator, net meter and 200 A main, the 200 A load panel, grounding electrodes and the utility transformer
- seven house circuits: AC condenser, air handler, water heater, pool pump, EV charger, kitchen and lighting

Open `index.html` in any current browser. There are no dependencies or network calls.

## How to use it

- **Setup (top bar).** Choose the inverter type and whether there's a battery; with a battery, choose *self-powered* or *backup only*. The plate redraws with the right equipment and wiring for each of the four combinations.
- **Conditions.** Scrub the time of day, change the sky, cut the grid, or initiate rapid shutdown. **▶ Play the day** runs the clock and integrates the battery charge and the meter registers.
- **Scenarios (keys 1–9).** Sunny noon, morning ramp, afternoon AC peak, after sunset, night EV charging, hurricane outage at midday and at night, an islanded system with a full battery (curtailment), and rapid shutdown. Each has a step-by-step sequence that rewrites itself for the current setup.
- **Every line is one conductor** in its standard colour: L1 black, L2 red, neutral white, ground green, PV + red / − black, the GEC bare copper, signals dashed purple. Moving white dashes show the direction energy is flowing; faded wires are de-energized.
- **Hover** anything for its name, a one-line description, its live state and (for wires) its conductors. **Click** for the Inspector: what it does, an "inside the box" diagram, the wires in and out, Florida notes and code references. Wires show typical sizes and live volts, amps and kW.
- **Side tabs.** Sequence, Wires (the full wire schedule and colour code), Day (a 24-hour chart of solar, home, battery and grid with daily totals), Loads (force any circuit on or off), and Code & Florida (an interactive 120% rule calculator, Florida-specific rules and the key NEC sections).
- **Keyboard.** 1–9 scenarios, P play, G grid, R rapid shutdown, Space pauses the wire animation, Esc clears the selection.

## The model

A simple instantaneous power balance, not a simulation of a real product:
- Solar follows a Florida-summer sun curve (7:00 am to 7:36 pm) with a 16% loss for heat and soiling, the inverter's efficiency, and clipping at the inverter's AC rating.
- Loads follow typical summer schedules (AC duty peaks mid-afternoon, the pool pump runs 9–5, the EV charges 10:30 pm to 1:30 am).
- With the grid up, a self-powered battery charges from surplus solar and discharges down to a 20% reserve; a backup-only battery charges from solar and holds. The grid makes up the difference.
- With the grid down and no battery, everything stops (anti-islanding). With a battery, the gateway islands the house, sheds the EV charger, pool pump and water heater (and the AC if the load exceeds about 7 kW plus solar), and curtails solar when the battery is full: a DC-coupled inverter throttles, an AC-coupled battery raises the frequency.

## What it is not

It is diagrammatic, not to scale, and not for construction. Wire, breaker and equipment sizes are typical for this example, not a design. Code references are to the 2020 NEC, which Florida's 8th-edition (2023) building code uses; net-metering details follow Florida PSC Rule 25-6.065 for investor-owned utilities. Confirm current rules and tariffs with the AHJ and the utility.

A self-test runs on load and logs to the console whether every cross-reference between wires, equipment and scenarios resolves in all four configurations.
