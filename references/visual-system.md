# Visual and typography system

## Canvas and composition

- Ratio: exactly 3:4 vertical.
- Preferred export: 1536×2048 px; acceptable compact export: 1024×1365 px.
- For plates and bowls, target the approved compact scale: the complete vessel with food occupies about 62–70% of canvas width and 30–38% of canvas height, leaving roughly 55–68% negative space. Treat 72% width or 40% height as a correction threshold unless the user requests a closer crop. Standalone beverages use the smaller approved width-led scale in [beverage-layout.md](beverage-layout.md), which overrides this balance.
- Keep one dominant food anchor, one information zone, and one small brand zone. Align edges to a quiet editorial grid.

## Hero extraction and camera angle

- Isolate the food, its original serving vessel, and elements physically integral to the presentation, such as a paper liner, garnish resting on the dish, or a utensil intentionally served inside it.
- Exclude the original tabletop, restaurant environment, hands, packaging, unrelated plates, napkins, and incidental props unless the user explicitly asks to retain them.
- Preserve the entire vessel silhouette, including handles, feet, transparent edges, openings, and negative spaces. Refine the matte to remove color spill, bright fringes, jagged edges, and clipped food details.
- Match the reference look with a slightly elevated three-quarter frontal camera: approximately 25–35° downward from horizontal, neutral 50–85 mm-equivalent perspective, with the food surface visible while the front wall and side depth of the vessel remain clear.
- For beverage-only pages, use the consolidated camera, scale, placement, and panel-distance contract in [beverage-layout.md](beverage-layout.md).
- Avoid bird's-eye flat lay, eye-level straight-on presentation, Dutch tilt, extreme foreshortening, and wide-angle distortion.
- Place the hero mainly in the middle-lower field, normally near lower-center or slightly offset, leaving a clear but not excessive information zone above or beside it. Keep the vessel level unless the source presentation intentionally uses an angle.
- Default scale by subject type on a 3:4 canvas: small desserts occupy roughly 40–54% of canvas width and 38–56% of height including garnish; plates and bowls use the narrower approved reference range of roughly 62–70% of width and 30–38% of height. Always keep the full vessel visible with safe outer margins. If an initial plate or bowl pass exceeds 72% width or 40% height, perform a single-variable scale correction: reduce the complete vessel, food, integral garnish, sauce, and contact shadow together, normally by about 20% first, without changing viewpoint, center, or plating. Recheck the raster rather than trusting the prompt alone. Standalone drinks follow [beverage-layout.md](beverage-layout.md).
- Add a soft, physically plausible contact shadow directly beneath and slightly behind the vessel. The shadow must anchor the cutout without becoming a glow or heavy black oval.
- Beverage panel proximity is defined in [beverage-layout.md](beverage-layout.md); do not substitute a remote-corner card.

If the source photo already has a compatible viewpoint, use a true cutout and preserve its pixels wherever possible. If it was shot from a materially different viewpoint, a flat cutout cannot be rotated into the target angle. In that case, use image editing/generation to reconstruct the viewpoint with the isolated dish as an identity reference; preserve plating, food count, vessel design, proportions, and visible ingredients, and do not fabricate hidden details casually.

## Color

Base tokens; use the expanded system in [editorial-style.md](editorial-style.md) when composing the page:

```css
--background: #F4F0EA;
--text: #35322E;
--muted: #7B746C;
--border: #000000;
```

Use one restrained accent sampled from the dish, such as deep wine red, leaf green, or cream. Avoid high-saturation UI colors.

## Typography

- Place the supplied restaurant display name near the upper-right. Make it clearly larger and bolder than the professional menu-category label directly beneath it. Center the name, category, optional short hairline, and optional item index on one shared vertical axis. Preserve the restaurant name verbatim and do not place a duplicate Chinese category above it.
- Prefer a clean CJK-capable sans serif. Suitable choices include Noto Sans CJK SC, Source Han Sans SC, PingFang SC, or a verified local equivalent. Latin may use Helvetica Neue, Neue Haas Grotesk, Inter, or Suisse Intl.
- Use no more than two families and three weights.
- Keep the dish name prominent through placement and spacing rather than excessive size or weight. Keep descriptions readable and labels compact, with generous leading and short line lengths.
- Include one mandatory complete four-sided black information frame. At 1024 px width, start around 1–1.25 px and verify that every edge remains black and visible after rasterization. Keep the panel compact, transparent or nearly transparent, and free of shadows, pills, dashboard styling, or dense table subdivisions.
- Keep text clear of all structural lines. At 1024 px width, reserve at least about 20 px between the visible glyph bounds and the outer frame; scale proportionally. Food-section dividers must sit in dedicated whitespace and extend fully to meet both vertical outer borders. Beverage flavor baselines must begin after the label column with a clear gap.
- Render text separately from the photographic generation. Check the rasterized result at 100% zoom.

## Suggested food information block

Use only fields supported by evidence:

```text
菜品名称
一至两行克制描述

用餐提示  ·  一至两句有用建议
推荐搭配  ·  一至三种可信酒水类别
价格      ·  ¥XXX   # only when supplied
```

Food pages never use sensory baselines, ticks, markers, or a flavor chart. Follow [food-layout.md](food-layout.md). Favor short editorial labels and spacing over decorative icons. If space is tight, remove an unsupported or low-value field rather than shrinking type below comfortable reading size.

## Beverage flavor profile bar

For standalone beverages, include a compact bar-style sensory profile inside the framed information panel. Do not use this system for food.

- Choose three or four dimensions that fit the item, such as `Sweet`, `Sour`, `Bitter`, `Fresh`, `Herbal`, `Creamy`, `Body`, `Spice`, or `Umami`; do not force the same axes onto every item.
- Draw each row as a hairline baseline with five evenly spaced ticks and one small circular marker. Do not use filled progress tracks, pills, gradients, percentages, numbers, or dashboard gauges.
- Use solid black `#000000` for every baseline and tick. Use one low-saturation accent for all markers, preferably caramel `#A46F4D`, wine `#7C4B44`, or olive `#7B8263`.
- Keep row labels small and aligned; all bars must share the same start, end, tick spacing, and marker size.
- Treat marker positions as approximate sensory tendencies derived conservatively from visible ingredients and user information. Do not imply measured chemistry or exact recipe data.

## Photographic direction

Use natural soft side light, gentle tonal roll-off, visible but controlled texture, and real contact shadows. Retain the source vessel when it is part of the dish identity. A replacement plate or tray is acceptable only when it does not alter the food and clearly improves presentation. Keep supporting ingredients subordinate, sparse, and physically plausible.
