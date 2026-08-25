# Food menu layout contract

Read this reference for plated mains, snacks, savory sides, fruit, pastries, desserts, salads, and other food pages. It defines the food-specific information system. Beverage pages instead follow [beverage-layout.md](beverage-layout.md).

## Food and beverage distinction

- Food pages do **not** use sensory baselines, five-tick flavor scales, markers, `Level`, or any other bar-style flavor profile.
- Reserve the compact line-and-marker flavor profile for standalone beverages.
- Communicate a food item's taste through its name and one restrained description, not through quantified-looking axes.

## Primary food panel

Use one compact transparent or nearly transparent panel enclosed by a complete four-sided black frame. Organize it as two or three stacked editorial sections:

1. **Item identity** — Chinese item name, optional small English alias, one- or two-line description, and supplied price aligned quietly to the right.
2. **用餐提示 / SAN. TIPS.** — one useful serving, eating, or experience note when supported.
3. **推荐搭配 / RECOMMENDED DRINK** — one to three credible drink pairings when pairing adds value.

The first section is mandatory. Use the second and third when supported; omit an empty section rather than inventing content. Main ingredients may appear in the description or as one small external annotation, but should not automatically become a table-like ingredient row.

## Content rules

- Keep the description concrete: identify the main food, visible preparation, seasoning, texture, or accompaniment in one or two short lines.
- A dining tip must help the guest: eat while hot, squeeze a visible citrus wedge, mix a visible sauce, share, or order with a suitable drink. Do not invent a preparation step or service ritual that the image does not support.
- Pairings may use credible generic categories such as清酒、清爽型鸡尾酒、气泡水、冷泡茶、咖啡, or another suitable beverage category.
- Use a specific cocktail, producer, vintage, brand, or menu item only when the user supplied it or the project includes an authoritative beverage list.
- Show price only when supplied. Never copy names, prices, pairings, or claims from a visual reference into an unrelated user's menu.

## Section geometry

- Draw every outer edge and internal divider in solid black `#000000` at the same optical hairline weight.
- Every divider between food-card sections must run fully from the left outer border to the right outer border and physically meet both vertical frame edges, forming clean T-junctions. Do not leave divider ends floating inside the frame.
- Text remains inset from the outer frame and from both sides of each divider. A divider may touch the frame but must never touch a glyph.
- Keep generous vertical whitespace above and below each divider. Make the first section slightly more prominent; keep tips and pairing sections lighter.
- Do not turn the panel into a dense form or dashboard. Prefer short paragraphs and a simple one-to-three-item pairing list.

## Suggested Chinese structure

```text
菜品名称
一至两行克制描述                         ¥价格  # only when supplied
──────────────────────────────────────────  # touches both side borders
用餐提示 / SAN. TIPS.
一至两句有用的食用或服务建议
──────────────────────────────────────────  # touches both side borders
推荐搭配 / RECOMMENDED DRINK
清酒 / 清爽型鸡尾酒 / 气泡水
```

## Food-panel QA

Before delivery, confirm:

- no flavor baselines, ticks, markers, `Level`, or sensory chart appears on the food page;
- the first section contains the item name and concise description, with price only when supplied;
- any tip is useful and evidence-based;
- any pairing is credible, and specific named drinks appear only with authoritative support;
- each internal divider touches both vertical outer borders with no visible gap;
- all frame and divider strokes remain black, closed, and visible in the final raster;
- text has clear padding and does not touch a border or divider.
