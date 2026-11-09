# Plumb & Square: residential wood framing

A single-file, offline primer on framing a wood house, from the sill to the ridge. Open `index.html` in any current browser. It has no dependencies or network calls. Your place and theme are kept in the browser's localStorage, and the page still works if storage is blocked.

## Sections

1. **The frame.** A clickable section through a two-story platform frame (footing, stem wall, anchor bolt, sill, rim, joists, girder and post, subfloor, plates, studs, header and window, stacked bearing walls, sheathing and WRB, ceiling joists, rafters, ridge, collar tie, eave, roof sheathing, connectors), with the gravity, uplift and lateral load paths animated. Platform vs balloon framing, ten principles of a good frame, and what the IRC covers.
2. **Lumber.** Nominal and actual sizes drawn to scale with I and S; why depth wins; No. 2 design values for four species; a shrinkage calculator for the cross-grain stack at each floor; warp and defects; engineered wood (LVL, PSL, LSL, glulam, I-joists, trusses, OSB, plywood); treated wood and use categories.
3. **Loads & spans.** A beam engine that rebuilds span tables from bending, deflection and shear for floor joists, ceiling joists, rafters and built-up headers (species, spacing, dead load, snow, pitch, deflection limit), with a loaded-beam diagram, utilisation bars and jack-stud count for headers.
4. **Nails & connectors.** Two nails compared to scale with NDS withdrawal values; an abridged nailing schedule (IRC Table R602.3(1)); eight connector types; good nailing and corrosion.
5. **Layout & square.** A diagonal and 3-4-5 squaring checker that reads measured diagonals; a plate layout-mark generator for 12, 16, 19.2 and 24 in.; tools, the order of a frame and tolerances.
6. **Floors.** A clickable floor framing plan (girder, posts, laps, stair opening with doubled header and trimmers and hangers, double joist under a partition, cantilever, bridging, subfloor) and a notch-and-bore checker for sawn joists (IRC R502.8).
7. **Walls.** A wall framer: length, plate height (precut studs), 2x4 or 2x6, spacing, corner types, head height and up to four doors and windows. It places commons on layout, kings, jacks, headers sized by the span engine, cripples, fillers and rough sills, and gives a cut list and framing factor. Corners, cutting studs and plates, building and standing walls, headers and advanced framing.
8. **Bracing & wind.** A racking demo for five bracing methods with drift and hold-down uplift; braced wall lines and methods (IRC R602.10); uplift load path, Florida and high-wind notes, and foundation anchorage.
9. **Roofs & rafters.** A common-rafter calculator (run, rise, line length, ridge deduction, net, tail, overall and stock length, birdsmouth seat, heel and notch depth, HAP, ridge size, framing- and speed-square settings) drawn as an overview with zoomed seat and ridge details; rafter thrust with a raised tie; eight truss types; ridge boards and beams, ties and purlins, overhangs, sheathing and venting.
10. **Hips & valleys.** A hip and valley rafter calculator for equal or unequal pitches: hip/valley pitch and angle, run and length per foot, plan angle, line, net, tail and overall length, ridge deduction, plumb and seat cuts with square settings, cheek bevel and top-edge angle, drop and backing angles, height above plate and seat, and jack-rafter schedules for both roof planes with common differences, deductions and side cuts. A rotatable 3D view (sheathed or bare framing), a framing plan, the hip stick laid out with seat and ridge details, and a framing-square rafter table for 2/12 to 18/12. How-to steps, valleys and their variants, and common mistakes.
11. **Stairs.** A stringer calculator: risers and treads, total run, angle, 2R + T, throat, stringer length and the floor opening needed for 6 ft 8 in. headroom, drawn in section, with the IRC R311.7 rules.
12. **Glossary.** About 115 searchable terms, each linked to its section.
13. **Check yourself.** 16 questions with explanations.

## Limits

These are educational models, simplified on purpose:
- Spans are computed for simple spans with uniform loads (no point loads, continuity, cantilevers, notches or wet service) from NDS No. 2 reference values with size, duration and repetitive-member factors. They land close to the IRC/AWC tables but are not those tables. Header loads assume a roof-and-ceiling or stacked-floor bearing wall with a centre bearing wall.
- Hip and valley geometry assumes walls at right angles, level plates and equal fascia heights (the overhang on roof B is set so fascias line up). The ridge deduction is half the ridge thickness measured along the hip's or valley's plan direction; other framing details (hips against king commons, supporting and shortened valleys) change it.
- Bracing capacities and stiffnesses in the racking demo are illustrative, in the range of AWC SDPWS allowable wind shears. Nail strength comparisons are reference withdrawal values and a diameter-squared guide, not design values.
- Code references are summaries of the 2021 IRC; numbering and requirements change between editions, and Florida, high-wind and seismic areas add their own. The adopted code, approved plans, truss and engineered-lumber drawings and the connector maker's instructions govern.

A self-test runs on load and logs to the console whether the core calculations (including the framing-square rafter table values, hip backing and drop, unequal-pitch geometry, a span-table value, the wall framer and the stair calculator) and every cross-reference resolve.
