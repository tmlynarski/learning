# Sheet & Seam: a sheet metal ductwork workshop

A single-file, offline teaching page about how ductwork is designed, laid out, cut, folded, seamed, joined and installed. It is the workshop companion to [Air in Motion](../hvac-duct-lab/), which covers airflow and duct sizing.

Open `index.html` in any current browser. There are no dependencies, fonts, CDNs or network calls. Your place, inputs, theme and quiz answers are kept in the browser's localStorage. The page still works if storage is blocked.

## Sections

1. **Anatomy.** A small supply and return system drawn in plan, the way a shop drawing shows it. Click any of the 24 numbered parts to see its name, other names, how it is made, how it is attached, and whether it is usually stock, made to size, custom or bought in.
2. **Shapes & metal.** Rectangular, spiral, snap-lock, flat oval, flex and duct board. An aspect-ratio explorer shows why flat ducts use more metal and have more friction. Also a galvanized gauge table (in, mm, lb/ft², kg/m²), materials, size conventions and pressure classes.
3. **Seams & joints.** Animated cross-sections of the Pittsburgh lock, snap lock, grooved seam, standing seam, S slip, drive cleat, TDF/TDC flange and the crimped round slip joint. You can step through them, play them, or scrub them with a slider (arrow keys work too).
4. **Fittings atlas.** 29 fittings in plan view with airflow: elbows and offsets, transitions, rectangular and round branches and takeoffs, plenums, end caps and in-line devices. Each one lists how it is built, how it is attached, when to use it, its relative pressure loss and whether it is usually a stock part.
5. **Pattern shop.** Flat-pattern generators with bend lines, seam and connector allowances, cut lists and a true-size SVG download:
   - straight section (two L-halves with Pittsburgh allowances)
   - radius elbow (cheeks and wrappers)
   - gored round elbow (parallel lines, all gores nested on one strip)
   - round reducer (radial lines)
   - square-to-round (triangulation, with a true-length table, offsets and a 1- or 2-piece option)

   Inches or millimetres; switching units converts the values.
6. **Shop to site.** The office → shop → site flow, with tools and common mistakes at each step. Also hangers, seal classes, insulation, fasteners and hand tools.
7. **Glossary.** 96 searchable terms. Each links to the section where it is drawn or animated.
8. **Check yourself.** 14 questions with explanations, and a "stock, made to size, custom or bought in?" sorter.

## How the drawings work

**Seams.** Each sheet is a polyline stored as segment lengths and the turn angle after each segment. A forming step changes the turn angles (folding), the sheet's offset (moving it into place) and its opacity. The animation interpolates the angles, so segment lengths stay the same and the metal folds instead of stretching. Thickness and gaps are drawn much larger than life.

**Patterns.** These use the three classic layout methods.
- **Straight sections and radius elbows** are direct geometry. Wrapper lengths are the arc lengths R·θ at the throat and the heel.
- **Gored elbows** use parallel-line development. A full gore turning α has a height of 2(R + r cos φ)·tan(α/2) at circumferential angle φ, with half gores at the ends. Alternate gores are turned 180°, so every gore shares a cut line with its neighbour and the strip has no waste.
- **Cones** use radial-line development. The slant height is s = √(H² + (r₁ − r₂)²), the pattern radii are R₁ = s·r₁/(r₁ − r₂) and R₂ = R₁ − s, and the sector angle is 360°·r₁/R₁.
- **Square-to-rounds** use triangulation. Each rectangle corner fans to a quarter of the circle, and each side midpoint joins the circle point opposite it. The triangles are laid flat one after another from their true 3-D edge lengths. Each new vertex is placed on the opposite side of the shared edge from the previous triangle. The circle edge is stepped off in chords, as you would with dividers.

The 1:1 SVG is written in real inches or millimetres. Print it at 100% (actual size) to make a card model before cutting metal.

## Limits

This is an educational tool, not a fabrication standard.
- Allowances (Pittsburgh pocket about 1 in, single flange ¼ in, and so on) are typical defaults and can be edited. Real figures come from your own roll formers.
- The gauge rule of thumb, hanger spacing and pressure-loss ratings are for orientation only.
- Material thickness, bend allowance and springback are not included in the patterns.

Real work follows the governing code, the project specification, SMACNA *HVAC Duct Construction Standards — Metal and Flexible* (or EN 1505/1506 and DW/144 in Europe) and the fitting manufacturers' data.
