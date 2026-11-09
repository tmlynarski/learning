# Sweep & Latch: door closers, arms and adjustment

A single-file, offline primer on how a hydraulic door closer works, built around the LCN 4040XP Series surface closer and its cutsheet. Open `index.html` in any current browser. It has no dependencies or network calls. Your place and theme are kept in the browser's localStorage, and the page still works if storage is blocked.

## Sections

1. **Inside the closer.** A clickable cutaway of the body (spring and tube, Green Dial, piston, rack, pinion, bearings, check valve, B/M/L/D valves, fluid, seals, cover, arm) that moves as you drag the door or let it go, with a hydraulic circuit that shows which passage the fluid is taking and a plan view of the door.
2. **Swing zones & valves.** Turn the backcheck, delay, main and latch valves (with the 4040XP's colour indicators and positive stop), the spring size, mount, door width and weight, temperature and fluid. A closing curve with the ADA 90°-to-12° timing and latch speed, and an opening curve that shows backcheck cushioning a walk-through, a brisk shove or a kick before the wall or the arm's limit. Animated plan view.
3. **Spring power & force.** The Green Dial, opening and closing force at the handle against door angle for each mount, the ADA 5 lbf and NFPA 101 limits, fire doors, a sizing rule of thumb, and air pressure that holds a door open or shut.
4. **Mounts & geometry.** Regular arm (pull side), top jamb (push side) and parallel arm (push side) solved as linkages in plan, with pinion rotation, leverage and closing force against angle, elevation sketches and a mount comparison.
5. **The arms.** All thirteen 4040XP arms (REGARM, LONG, XLONG, H, HLONG, EDA, HEDA, EDAW62G, HEDA62G, CUSH, HCUSH, SCUSH, SHCUSH) drawn and described, with filters and an arm selector that flags hold-open on fire doors.
6. **Fitting the opening.** A head-and-door section and a checker for the 18, 18G, 18TJ and 18PA plates, the 62PA, 62A and CUSH shoes and supports, the 61 blade stop spacer and the 419 flush frame adapter.
7. **Specifying it.** Finishes, covers, fasteners and cylinder options, and a hardware-schedule line builder that adds the metal cover and SRI when the cutsheet requires them.
8. **Codes & ratings.** ADA closing speed, opening force and headroom; NFPA 101 egress forces; NFPA 80 fire doors and hold-open; UL 10C; BHMA A156.4 grades; pressure-relief valves; environment.
9. **Other closers & handing.** Track arm, concealed, floor, spring hinge, electronic hold-open and power operators compared; LH, RH, LHR, RHR, and which 4040XP parts are handed.
10. **Adjust & troubleshoot.** The adjustment sequence and a symptom-to-cause table.
11. **Glossary.** About 55 searchable terms, each linked to its section.
12. **Check yourself.** 18 questions with explanations.

## Limits

These are educational models, simplified on purpose:
- Part numbers, arms, accessories, degrees of operation, finishes and ratings come from LCN's 4040XP cutsheet (Allegion 013110, Rev. 05/2022). The forces, speeds and arm geometry are this page's own model, not LCN data.
- The arm linkage is solved from plan dimensions taken from the cutsheet where it gives them and filled in where it doesn't. Spring rate, preload by size, pinion radius and mechanical efficiency are tuned so that size 1 on a 36 in. door opens at just under 5 lbf, matching the cutsheet's claim.
- Closing speed uses an orifice law (flow ∝ valve opening × √pressure) with quasi-static motion; backcheck uses the same law with the door's inertia. Valve "turns" are a relative scale. Temperature effects are illustrative.
- The sizing table is a common rule of thumb; the chart in LCN's installation instructions governs. Code references are summaries; the adopted edition and the authority having jurisdiction govern.

A self-test runs on load and logs to the console whether the model, the fitting and spec rules, and every cross-reference check out.
