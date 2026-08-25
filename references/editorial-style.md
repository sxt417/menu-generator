# Editorial style system

Apply this reference to every final menu composition. The goal is a quiet fine-dining still-life poster with subtle information design—not merely a tidy menu layout.

## Visual character

Use these qualities as decision criteria: editorial food menu, fine-dining still life, minimal luxury, quiet elegance, premium minimalism, Japanese restraint, refined typography, soft studio lighting, subtle information design, and controlled asymmetry.

The food must remain the first visual read. Type and decoration support it at a lower contrast and smaller scale.

## Density and layout

- Plate and bowl hero scale: the complete vessel with food should occupy approximately 62–70% of canvas width and 30–38% of canvas height. Treat 72% width or 40% height as the correction threshold unless a close crop was requested. Standalone beverages use the smaller approved scale in [beverage-layout.md](beverage-layout.md).
- Negative space: approximately 55–68% for plates and bowls and broader for the approved beverage layout.
- Framed information block width: generally 24–32% of canvas width; expand only when Chinese legibility requires it.
- Outer margins: about 80–110 px on a 1024–1086 px-wide canvas; scale proportionally.
- Typical relationship: micro brand/menu label at upper right, light information block at upper-left or upper-middle, enlarged hero dish across the lower half, and optional micro-label near an edge. Reposition the information block when needed instead of shrinking the food back to a distant scale.
- Allow slight asymmetry. Avoid a rigid centered stack, excessive alignment, or a fully occupied upper half.

If the page feels crowded, remove information or decoration before shrinking text. If the information block competes with the food, reduce its size, fill opacity, border contrast, or content.

## Typography

### Restaurant and category cluster

- Use the supplied restaurant display name verbatim; if it was not supplied, ask for it before composing.
- Place the restaurant name at the top of the upper-right identity cluster. At 1536 px canvas width, begin around 26–32 px, weight 650–700, and adjust only for name length. It should be visibly larger and bolder than the category but remain subordinate to the dish title and hero.
- Put one concise professional category directly below, normally in tracked uppercase English: `STARTER`, `MAIN COURSE`, `SIDE`, `DESSERT`, `COCKTAIL`, `COFFEE`, `TEA`, or `NON-ALCOHOLIC`, chosen from the actual subject. Never use `SIGNATURE` or `SEASONAL` as a substitute unless that status is supported separately.
- Center the restaurant name, category, optional short hairline, and optional item index on exactly one shared axis. Use `text-anchor: middle` or an equivalent deterministic alignment method; do not eyeball separate left offsets.
- Do not place a duplicate Chinese category above the restaurant name. A Chinese category may appear elsewhere only when it carries necessary primary information.
- Standalone beverages override the category pattern: use restaurant name → short black hairline → English item name, centered on one axis. Omit the category and any `DRINK / 01`-style index unless the user explicitly requests them. See [beverage-layout.md](beverage-layout.md).

### Chinese title

- Use medium or restrained semibold weight, normally 500–600; never ultra-bold.
- At 1024–1086 px canvas width, start around 34–48 px and scale to the composition. Prefer smaller when the title is long or enclosed by the information frame.
- Line height: 1.15–1.25. Letter spacing: around -0.02em unless the selected CJK font renders poorly with negative tracking.
- Use warm near-black such as `#2B2A28`, `#35322E`, or `#3A342F`, not pure black.
- Prefer Source Han Sans SC, Noto Sans SC, MiSans, HarmonyOS Sans SC, Alibaba PuHuiTi, or an available equivalent. A medium Source Han Serif SC or Noto Serif SC title may be paired with sans-serif body text when it improves the cuisine mood.

### English subtitle

- Treat it as a label, not a second headline.
- Use uppercase, 12–14 px, weight 400–500, tracking 0.16–0.20em, and warm gray near `#7E776F` on a 1024–1086 px-wide canvas.

### Description

- Keep to one or two short lines. Write a precise dish note, not advertising copy or a technical explanation.
- Prefer concrete sensory relationships: “酥炸鸡肉与柔滑肉汁，配以土豆泥、青豆与卷心菜。”
- Avoid exaggerated words such as “超级”“美味”“香喷喷”“浓郁爆汁”.

### Metadata labels and values

- Labels such as 主要食材, 用餐提示, 推荐搭配, or beverage flavor labels: 11–13 px, warm gray near `#8E867E`, tracking 0.04–0.08em.
- Values: 15–17 px, weight 400–500, near `#35322E`.
- Labels must never be darker, larger, or heavier than the description.

Scale all suggested sizes proportionally for larger exports, and inspect the raster at 100% before delivery.

## Lightweight information blocks

Avoid a dashboard card, large opaque rectangle, dense table, or form-like rows. Prefer one of these patterns:

### Food pattern · Sectioned editorial card

```text
菜品名称
一句菜品描述                         ¥价格  # only when supplied
──────────────────────────────────────  # touches both side borders
用餐提示 / SAN. TIPS.
一至两句有用的食用或服务建议
──────────────────────────────────────  # touches both side borders
推荐搭配 / RECOMMENDED DRINK
一至三种可信的酒水类别
```

Food cards never contain sensory baselines, ticks, markers, `Level`, or a flavor chart. Read [food-layout.md](food-layout.md) for content and evidence rules.

### Beverage pattern · Recipe and flavor profile

```text
饮品名称
配方 / 主要成分

Level  ─┼─┼─●─┼─┼─  # verified alcohol only
Sweet  ─┼─┼─┼─●─┼─
Sour   ─┼─┼─┼─┼─●─
Creamy ─┼─●─┼─┼─┼─

总体味型                         ¥价格  # only when supplied
```

Use one complete four-sided frame on every page. The frame is an output requirement, not optional decoration. Draw the outer frame, internal dividers, beverage flavor baselines, and ticks in black `#000000`; do not lower their opacity until they read as gray or white. At 1024–1086 px canvas width, start around 1–1.25 px. Keep little or no fill and generous internal padding. Food cards may use two full-width section dividers; each must physically meet both vertical outer borders without a visible gap. Keep the panel small and visually quiet rather than turning it into a dashboard.

Inspect the final raster at both thumbnail size and 100%. All four outer edges must form a clearly closed black rectangle, and every internal structural line must remain black and readable. If an edge disappears into the background, raise stroke width before delivery; never compensate by adding a large opaque card or shadow.

No text may overlap or touch a structural line. Keep visible glyph bounds at least about 20 px from the frame on a 1024–1086 px-wide canvas, scaled proportionally. The title must sit fully below the top edge; horizontal dividers require whitespace above and below; flavor labels must end before the baseline begins. Make the visible bottom inset after the final glyph, tick, marker, or baseline optically match the top and side insets. Check the rasterized glyph bounds rather than relying only on SVG coordinates or text baselines.

The primary frame should contain the item name plus the subject-appropriate modules. Food uses concise description, supplied price, dining tip, and drink pairing as applicable; beverages use verified ingredients, flavor profile, taste label, and supplied price. A second micro-frame may annotate one garnish or component, but is never required.

## Beverage-only bar-style sensory display

Place a compact sensory chart inside every standalone beverage panel. Never use it for food:

```text
Sweet  ─┼─┼─●─┼─┼─
Sour   ─┼─┼─┼─●─┼─
Herbal ─┼─┼─┼─┼─●─
Body   ─┼─●─┼─┼─┼─
```

- Choose three or four dimensions selected by [dynamic-information-system.md](dynamic-information-system.md). Do not force the same axes onto every drink.
- Use a hairline baseline, five evenly spaced ticks, and one 4–6 px marker per row on a 1024–1086 px-wide canvas; scale proportionally.
- Align labels and bars precisely. Use one muted accent for all markers.
- This is an editorial flavor tendency, not quantified nutritional or recipe data.
- Never render it as a filled progress bar, segmented pill, radar chart, or colorful dashboard component.

## Micro-detail system

Use at most two types of micro-detail on a page:

- a small numbering label such as `MENU / 01`, `PLATE / 01`, `No. 01`, `HOUSE SPECIAL`, or `CHEF'S NOTE`;
- one short, hairline accent near a title, information block, or page edge;
- a tiny English annotation such as `MAIN COURSE`, `PAIRING`, `MAIN INGREDIENT`, `SEASONAL PLATE`, or `CHEF'S RECOMMENDATION`;
- one or two ingredient labels such as `MAIN INGREDIENT : GRAVY` or `PAIRING : ICED BLACK TEA`.

Keep these details small and secondary. Any drawn line, including a micro accent line or secondary micro-frame, must use black `#000000`. Color accents are reserved for small solid markers or the food itself, not structural strokes.

## Supporting objects

Add zero to three small supporting objects only when they strengthen ingredient or pairing logic. An ingredient explicitly supplied by the user or printed in the source is valid evidence for an external physical cue. Valid examples include one recognizable blossom, leaf, bud, fruit slice, herb sprig, a small sauce cup, a few pepper grains, one glass of the recommended drink, a minimal silver fork, a corner of white napkin, or a small amount of verified raw ingredient. For flower-, leaf-, or bud-led items, one intact specimen or short natural stem is normally enough; for a butterfly-pea drink, one true butterfly-pea blossom may rest beside—but not touch—the glass. Use two or three pieces only when a small group is more natural, such as cinnamon sticks. Match scale, camera, surface contact, shadow, and light direction, and do not substitute a generic decorative flower for the named ingredient.

Keep the scene sparse. Do not turn it into lifestyle photography, a full table setting, or a collection of props. The hero dish must remain absolutely dominant. Do not add any object whose identity or relationship cannot be justified from the dish or user information.

## Color

Preferred backgrounds: `#F4F0EA`, `#F1ECE5`, or `#EEE8E0`.

Preferred type colors and mandatory structural-line color:

```css
--text-strong: #2B2A28;
--text: #35322E;
--text-muted: #7B746C;
--label: #8E867E;
--rule: #000000;
```

Use at most one low-saturation accent: wine `#7C4B44`, caramel `#A46F4D`, or olive gray-green `#7B8263`. Avoid pure white backgrounds, large areas of pure black, harsh high contrast, and decorative multicolor palettes. Black structural hairlines remain mandatory.

## Photography mood

Aim for a quiet premium editorial still life: soft studio light, delicate tonal transitions, realistic food texture, and a natural lightweight shadow. Avoid aggressive advertising light, glossy ecommerce separation, artificial 3D, plastic food, or a complex environment.

## Automatic correction pass

Before delivery, correct these failure modes:

- Oversized or overly bold Chinese title: reduce size and weight.
- Hero dish or drink feels too small or distant: enlarge it toward the middle of the subject-specific range while keeping the complete vessel and required information legible.
- A plate or bowl exceeds 72% of canvas width or 40% of canvas height, becomes clipped, or overwhelms the information: make a scale-only correction that reduces the complete vessel, food, integral garnish, sauce, and contact shadow together. Start around 20%, preserve its center and camera relationship, then remeasure the raster against the 62–70% width and 30–38% height target.
- Missing frame: add the compact black hairline frame before delivery. For food, remove any flavor chart and use evidence-based dining-tip or drink-pairing sections when useful; make every section divider meet both vertical borders. For standalone beverages, add the required three or four flavor rows.
- Large or heavy information card: reduce footprint, fill, internal density, and stroke width within the required hairline range; keep structural strokes black.
- Crowded page: increase negative space and remove low-value copy.
- Too many decorations or props: keep only the most meaningful one or two.
- Generic restaurant-menu or PPT feeling: strengthen still-life hierarchy, micro-annotation scale, and controlled asymmetry.
- Layout feels mechanically symmetrical: shift one secondary block or micro-detail while keeping the dish stable and the reading order clear.
