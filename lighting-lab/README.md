# Lumen & Lux: interior and exterior lighting design

A single-file, offline primer on lighting and lighting design, from the lumen to the landscape. Open `index.html` in any current browser. It has no dependencies or network calls. Your place and theme are kept in the browser's localStorage, and the page still works if storage is blocked.

## Sections

1. **Light & measure.** A clickable section through a downlight: lumens, candelas, lux and foot-candles, luminance and efficacy, with the inverse-square and cosine laws worked live as you move the light and the point. Typical illuminance and luminance tables; the eye, adaptation and age; reflectance.
2. **Colour & spectrum.** Fourteen modelled sources (candle, incandescent, halogen, five LEDs, fluorescent, ceramic metal halide, high- and low-pressure sodium, amber LED, daylight). For each: the spectrum with the day and night eye curves, computed CCT and Duv, S/P ratio and blue content, and twelve colour swatches rendered under the source beside a blackbody reference, with or without chromatic adaptation. A colour-temperature slider, CCT uses, CRI, R9 and TM-30, metamerism.
3. **Lamps & LEDs.** Sources compared by efficacy, CRI, CCT, life and dimming; lamp shape codes and bases; how a white LED works; drivers, binning and flicker; an L70 lumen-maintenance chart; replacing old lamps.
4. **Beams & luminaires.** Nine distributions (spot to Lambertian, batwing, direct/indirect, indirect) with a polar candela plot, floor section, beam and field angles, centre illuminance and a computed spacing criterion. Beam spreads, glare and shielding, reading a spec sheet, luminaire families.
5. **Interior principles.** A living room you light layer by layer (downlights, cove, wall wash, reading lamp, art accent, decorative) with relative luminances, ratios and commentary, including the cave effect. Kelly's three kinds of light, an accent-contrast slider, luminance ratios, design principles and recommended light levels.
6. **Room calculator.** A point-by-point illuminance map of a room for any size, layout, distribution, reflectances and light loss factor, with average, minimum, maximum, uniformity and power density, checked against the lumen method (RCR, CU, LLF) with a one-click layout fix.
7. **Room by room.** Placement rules, targets and common mistakes for eleven home and commercial spaces, and a 30° art-aiming tool that traces reflections off glazing and frame shadows.
8. **Daylight.** A sidelit room in section with the sun placed by city, date, hour and orientation, an adjustable overhang, sun penetration and daylight zones; an average daylight factor calculator; sDA, ASE and glare control.
9. **Exterior & dark sky.** Seven exterior luminaires from bare lamp to full cutoff, integrated over the sphere for uplight (with an approximate BUG uplight rating), high-angle light, ground and property-line illuminance, glare and a colour-weighted sky-glow index, checked against Model Lighting Ordinance zones. The five principles, distribution types I–V, wildlife (Florida sea-turtle rules) and exterior light levels.
10. **Landscape & façade.** Twelve illustrated techniques (uplighting, moonlighting, grazing, washing, silhouetting, shadowing, path, step, accent, cross-lighting, water, façade) and a 12 V system designer: voltage drop by cable, run and layout, transformer tap and loading.
11. **Controls & energy.** Linear, square-law and logarithmic dimming against perceived brightness, with fixed, dim-to-warm and halogen colour; dimming protocols; sensors and schedules; tunable white and circadian light; a lamp-swap savings calculator; what energy codes require.
12. **Glossary.** About 95 searchable terms, each linked to its section.
13. **Check yourself.** 16 questions with explanations.

## Limits

These are educational models, simplified on purpose:
- Spectra are modelled from Gaussian bands and blackbody curves, tuned to the stated CCT, not measured lamp data. The CIE 1931 observer is the Wyman–Sloan–Shirley analytic fit and the scotopic curve an asymmetric Gaussian. The "swatch fidelity" score is this page's own CIELAB measure on twelve synthetic swatches; it behaves like CRI but is not CRI or TM-30. Screen colours depend on the display.
- The room calculator sums direct light point by point from idealised distributions and adds reflected light as one uniform integrating-sphere term, so it is optimistic in corners. Its lumen-method CU is a generic table, scaled for the distribution.
- The spacing criterion is computed by a simple two-luminaire rule; manufacturers' published values use other methods.
- Exterior distributions are idealised shapes; BUG uplight ratings use the TM-15 uplight lumen thresholds only; property-line limits follow the MLO performance values, simplified.
- Recommended light levels are rounded typical ranges after IES guidance. Code references (NEC, IRC, IBC, IECC, ASHRAE/IES 90.1) are summaries; the adopted edition governs.

A self-test runs on load and logs to the console whether the core calculations and every cross-reference resolve.
