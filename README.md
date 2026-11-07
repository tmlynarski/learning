# Learning

Self-built study tools and interactive explainers.

**Live site:** https://tmlynarski.github.io/learning/, served by GitHub Pages from the root of `main`. Each project opens at its own folder URL (for example https://tmlynarski.github.io/learning/hydronic-plant-lab/), and that link can be texted or emailed. Sending the `.html` file itself doesn't work: phone and Messages previews don't run JavaScript, so the pages show up blank.

To add a project, put it in its own folder with an `index.html`, link it from the root `index.html` and from the list below, and push to `main`. Pages redeploys in a minute or two. `.nojekyll` makes GitHub serve the files exactly as written.

## Projects

- [hvac-duct-lab](hvac-duct-lab/) — **Air in Motion**, an interactive, animated laboratory for HVAC duct design: duct sizing, velocity, static pressure, fan and system curves, and branch balancing. Open `hvac-duct-lab/index.html` in a browser; it runs offline.
- [hydronic-plant-lab](hydronic-plant-lab/): **Heat & Water**, an interactive piping and venting schematic of an oil boiler, a hydro-air handler and an indirect water heater working together. It shows every connection and valve (with valve types), the incoming water service, and the exhaust and discharges, with animated sequences of operation. Open `hydronic-plant-lab/index.html` in a browser; it runs offline.
- [sheet-metal-lab](sheet-metal-lab/): **Sheet & Seam**, a workshop on how sheet metal ductwork is made: the vocabulary, duct shapes and gauges, animated seams and joints, an atlas of fittings and takeoffs (stock vs. made to size vs. custom), and a pattern shop that lays out flat patterns with 1:1 SVG export. Open `sheet-metal-lab/index.html` in a browser; it runs offline.
- [solar-pv-lab](solar-pv-lab/): **Sun & Current**, a wiring plate of a typical Florida home solar system: an 8 kW rooftop array with a string inverter or microinverters, and an optional 13.5 kWh battery with a backup gateway. Every conductor is drawn in its real colour from the modules to the meter, load panel and loads, with live power flow through the day, hurricane outages, battery curtailment and rapid shutdown, plus the NEC and Florida rules behind it. Open `solar-pv-lab/index.html` in a browser; it runs offline.
