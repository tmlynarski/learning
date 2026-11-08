# Watts & Wire: how a building's electrical system works

A single-file, offline primer on architectural electrical systems. It starts at volts and amps and ends in the electrical room. Open `index.html` in any current browser. It has no dependencies or network calls. Your place, theme, inputs, panel schedule and quiz answers are kept in the browser's localStorage, and the page still works if storage is blocked.

## Sections

1. **Volts, amps & watts.** A live circuit (source, ammeter, load, voltmeter) with a water-analogy view and a DC/AC switch. Pick real loads and voltages and watch current and power change; the page warns when a 120 V appliance would see 240 V. Also a clickable formula wheel, a "solve any two" calculator, SI prefixes and a table of typical magnitudes.
2. **kW vs kWh.** A power gauge, an energy register and a strip chart. Energy is the area under the power curve. Also a monthly energy and cost calculator, and a demand-charge comparison of two buildings that use the same kWh with different peaks, with peak shaving.
3. **AC & phases.** A rotating phasor diagram (the transformer winding *is* the voltage diagram) projected onto an oscilloscope, for 120/240 V split-phase, 208Y/120, 480Y/277 and 240/120 V high-leg delta. Measure between any two terminals, and show that three-phase power is steady while single-phase pulses. Also RMS vs peak, nominal vs utilization voltage, and where each system is used, with its wire colours.
4. **kVA, PF & amps.** The power triangle with a power-factor slider, and an amp calculator (W, kW, VA, kVA or hp on any system) that suggests a breaker and copper conductor. A drawing to scale shows the copper the same load needs at 120, 240, 208 and 480 V. Also NEC motor full-load currents.
5. **Wire & breakers.** A kitchen countertop circuit: plug in appliances, watch a thermal-magnetic breaker trip on overload or short circuit, and see why 14 AWG on a 20 A breaker is dangerous. Also conductor sizes drawn to scale with ampacities, a voltage-drop calculator, and cable and raceway types.
6. **Grounding & shock.** A transformer, service panel, branch circuit, metal appliance and a person. Toggle the fault, the green wire, a GFCI and a local ground rod to see fault current, case voltage and body current, and why a ground rod doesn't trip a breaker. Also body-current effects, protective devices and the vocabulary of grounding and bonding.
7. **The building one-line.** One-line diagrams of a Florida house (with a standby generator and load shedding), a restaurant (with battery emergency lights) and a mid-rise office (with a fire pump, step-down transformer, generator and two ATSs). Each item is clickable for what it is, what it asks of the building, and the code behind it. A utility outage plays out the generator start and the transfer timing.
8. **Panels & load calcs.** An editable 42-circuit 208Y/120 V panel schedule: add and remove circuits, auto-balance the phases, and see the connected load, the NEC demand load and the feeder size. Also a dwelling service calculation (NEC 220.82 optional method) and early-design load densities.
9. **Rooms & drawings.** NEC 110.26 working space in plan and section for panelboards and switchboards, by voltage and condition, with exits, panic hardware and dedicated space. Also a small apartment power and lighting plan with standard symbols, circuits and home runs, mounting heights, and rules of thumb for sizing electrical rooms.
10. **Formulas & numbers.** A printable sheet of everything above.
11. **Glossary.** About 90 searchable terms, each linked to its section.
12. **Check yourself.** 16 questions with explanations.

## Limits

These are educational models, simplified on purpose:
- Loads are modelled as resistors in Section I; breaker trip times and cable heating in Section V are illustrative and sped up.
- The grounding values in Section VI (0.25 Ω loop, 1,500 Ω body, 25 Ω rod) are typical round numbers.
- Ampacities are copper, NEC Table 310.16 at 30 °C with no more than three current-carrying conductors and no derating.
- Load calculations follow the structure of NEC Article 220 in simplified form; planning densities are rough ranges.

Code references are to the 2020 and 2023 NEC (NFPA 70), with NFPA 20, 37, 101 and 110 where noted. Rules change between editions and with local amendments. Real projects are designed by a licensed engineer and approved by the authority having jurisdiction.

A self-test runs on load and logs to the console whether the core calculations and every cross-reference resolve.
