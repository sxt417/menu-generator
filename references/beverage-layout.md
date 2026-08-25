# Beverage menu layout contract

Read this reference for cocktails, highballs, wine, coffee, tea, juice, soda, and other standalone beverages. It consolidates the approved beverage solution and overrides general camera and hero-scale defaults where they conflict. Select content modules and beverage type first with [dynamic-information-system.md](dynamic-information-system.md).

## Canvas and visual balance

- Use an exact 3:4 portrait canvas, preferably 1536×2048 px.
- Use a quiet warm ivory, warm gray, or soft beige studio background with restrained texture and broad negative space.
- Keep the beverage in the lower-left field and the primary information panel diagonally above-right. Keep the brand or menu label small near the upper-right.
- Use the approved beverage reference scale derived from a 1086×1448 portrait example: the complete short tumbler occupies about 29% of canvas width and 32% of canvas height, with its base near 89% of canvas height. As the working range, keep standalone beverages at about 28–32% of canvas width. A short tumbler normally occupies about 31–36% of canvas height; taller glasses, handles, straws, and integral garnish may extend higher while preserving the same width-led visual scale and the vessel's natural proportions. Do not enlarge a drink merely to consume empty space.
- Preserve the entire vessel and a plausible contact shadow. Do not crop the base, rim, straw, garnish, handles, or transparent edges.

## Beverage camera and reconstruction

- Prefer a near-frontal camera with a mild 10–18° downward angle and a neutral 65–90 mm-equivalent perspective.
- Show the top opening as a narrow ellipse while keeping the vessel wall and vertical proportions dominant. Avoid flat eye-level elevation, overhead views, Dutch tilt, and wide-angle distortion.
- If the source viewpoint differs materially, reconstruct the view with image editing rather than rotating a flat cutout. Preserve the original vessel, liquid, ice, garnish arrangement, condensation, bubbles, and recognizable service details.
- Do not add alcohol, citrus, foam, fruit, price, provenance, or other recipe details that are not supplied or visibly supported.

## Glass-to-panel relationship

- Place the primary information panel above and diagonally to the right of the beverage, not in a remote corner.
- Measure the closest visible gap from the panel border to the glass, straw, or integral garnish. Target 3–6% of canvas height, approximately 60–120 px on a 2048 px-tall export.
- A small horizontal overlap between the projected bounding boxes is acceptable and can strengthen the relationship, but the frame must never touch, cover, or appear attached to the drink.
- Adjust the panel position rather than the approved beverage scale when preserving this gap; do not shrink the panel content or allow the two elements to collide.

## Upper-right identity cluster

- Use this exact sequence for standalone beverages: supplied restaurant display name, a short black hairline immediately below it, then the English item name.
- Center all three elements on one shared vertical axis. The restaurant name remains the largest and boldest element; the English item name is a small tracked label.
- Do not add a category label or an item index such as `DRINK / 01` to this cluster unless the user explicitly requests one. Classification still guides content selection internally but does not need to appear here.

## Information panel

- Use one compact transparent or nearly transparent panel, generally 24–32% of canvas width.
- Structure it around verified ingredients or recipe, a compact three- or four-axis flavor profile, one overall taste label, and supplied price. Unlike food panels, standalone beverage panels use the flavor-line system by default.
- Enclose it with a complete four-sided black `#000000` frame. Use about 1–1.25 px at 1024–1086 px canvas width or about 1.5–1.9 px at 1536 px width.
- Draw every structural line in black `#000000`: outer frame, internal dividers, flavor baselines, ticks, micro-frames, and any short accent rule. Never render structural lines in white, pale gray, or reduced opacity.
- Keep the Chinese beverage title at a clear semibold weight around 600. At 1024–1086 px canvas width, begin around 34–48 px and scale proportionally.
- Keep the English subtitle small, uppercase, tracked, and subordinate. Metadata must remain lighter than the description.
- Reserve at least about 20 px between visible glyph bounds and any frame edge on a 1024–1086 px-wide canvas, scaled proportionally. The title must sit fully below the top border. Match the visible bottom inset to the top and side insets; measure from the lowest glyph, tick, marker, or baseline rather than from its text baseline. Do not let the final flavor row sit closer to the bottom frame than the title sits to the top frame.
- No text may touch, cross, sit over, or visually merge with the frame, dividers, flavor baselines, or ticks. Check rasterized glyph bounds, not only SVG baselines.

## Required compact flavor profile

- Use three or four relevant dimensions on every standalone beverage page. A verified alcoholic drink may use `Level`, `Sweet`, `Sour`, plus one of `Bitter`, `Salty`, `Creamy`, `Fresh`, or `Herbal`. Coffee, tea, soda, juice, mocktails, and uncertain drinks must not use `Level`; choose from `Sweet`, `Sour`, `Bitter`, `Body`, `Fresh`, `Creamy`, or `Herbal` as appropriate.
- Use four rows maximum. At 1024–1086 px canvas width, keep row pitch around 24–30 px.
- Give labels a dedicated left column. Begin each baseline only after a clear label-to-line gap; labels must never sit on the line.
- Make each baseline about 58–66% of the panel's inner width, with five evenly spaced black ticks and one small circular marker.
- Use black for baselines and ticks. Use one restrained accent color only for the circular markers; do not use filled tracks, percentages, pills, or gradients.

## Optional micro-detail

- One small ingredient or service-note frame may appear away from the hero and primary panel.
- Its frame and divider must also be black. Keep it subordinate and do not introduce an unsupported ingredient.

## Evidence-based flavor cues

- Treat ingredients explicitly supplied by the user or printed in the source as sufficient evidence for a restrained physical cue outside the vessel. When one of those ingredients defines the drink's identity, add a small recognizable specimen beside the glass if it improves immediate recognition.
- Use one to three scale-correct pieces at most, placed close to but not touching or overlapping the glass. One intact blossom, leaf, bud, fruit slice, or short natural stem is normally sufficient; use multiple pieces only when the ingredient reads more naturally as a small group. Match the existing camera, surface contact, and light direction.
- A supported ingredient may appear both as integral garnish and as one restrained external specimen; the external cue must still feel intentional rather than decorative.
- For a butterfly-pea drink, one recognizable blue butterfly-pea blossom may rest on the surface outside the glass. Do not replace it with a generic blue flower.
- For a cinnamon-flavored drink, use two or three natural cinnamon sticks. Do not substitute star anise, orange, chocolate, nuts, powder piles, or other ingredients unless separately supported.
- Keep the cue below the information-panel area and subordinate to the drink; preserve the approved beverage scale and broad negative space.

## Beverage QA

Before delivery, inspect the final raster at thumbnail size and 100% and confirm:

- the hero uses the approved width-led scale of approximately 28–32% of canvas width; a short tumbler is approximately 31–36% of canvas height, while taller vessels and integral garnish may extend higher without becoming visually wider;
- the camera is near-frontal with a mild 10–18° downward view and undistorted glass proportions;
- the panel is diagonally above-right with a 3–6% canvas-height nearest-edge gap;
- all four frame edges are closed, black, and visible;
- the panel's visible top, bottom, left, and right insets are optically consistent, including after the last flavor row;
- every divider, flavor baseline, tick, micro-frame, and accent rule is black;
- no text intersects or touches any line;
- the required three or four flavor rows are present, compact, aligned, and readable;
- the upper-right cluster reads restaurant name → hairline → English item name and contains no unrequested category or `DRINK / 01` field;
- any physical flavor cue is supported, limited to one to three pieces, close to but not touching the vessel, and correctly lit and scaled;
- the drink remains recognizably the same and no unsupported ingredient or claim has been introduced.
