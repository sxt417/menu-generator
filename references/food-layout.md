# Food menu layout contract

Read this reference for plated mains, snacks, savory sides, fruit, pastries, desserts, salads, and other food pages. Desserts are always food for layout and flavor-profile rules. Beverage pages instead follow [beverage-layout.md](beverage-layout.md).

## Food and beverage distinction

- Food and dessert pages do **not** use sensory baselines, five-tick flavor scales, markers, `Level`, numeric flavor scales, radar-style graphics, or any structured flavor chart.
- Reserve the compact line-and-marker flavor profile for standalone beverages.
- Communicate a food item's taste through its name and one restrained description, not through quantified-looking axes.

## Upper-right identity cluster

Use the supplied restaurant display name with the concise professional category directly beneath it. Center both on one shared vertical axis. Do not switch to a menu index, subtitle, slogan, or decorative metadata. The restaurant name must come from the user and must never be invented or replaced with a neutral placeholder.

## Primary food panel

Use one compact transparent or nearly transparent panel enclosed by a complete four-sided black frame. Organize it as two or three stacked editorial sections:

1. **Item identity** — item name in the selected menu language, optional small secondary-language alias, one- or two-line description in the selected language, and supplied price aligned quietly to the right.
2. **Dining tip** — use `用餐提示` for Chinese or `DINING TIP` for English; include one useful serving, eating, or experience note when supported.
3. **Drink pairing** — use `推荐搭配` for Chinese or `RECOMMENDED DRINK` for English; include one to three credible drink pairings when pairing adds value.

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

## Suggested localized structure

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

```text
ITEM NAME
One or two restrained descriptive lines      PRICE  # only when supplied
──────────────────────────────────────────  # touches both side borders
DINING TIP
One useful serving or eating note
──────────────────────────────────────────  # touches both side borders
RECOMMENDED DRINK
Sake / Refreshing cocktail / Sparkling water
```

## Food-panel QA

Before delivery, confirm:

- no flavor baselines, ticks, markers, `Level`, numeric scale, radar graphic, or sensory chart appears on the food or dessert page;
- the first section contains the item name and concise description, with price only when supplied;
- the item name, description, section labels, tip, and pairing consistently use the selected menu language;
- any tip is useful and evidence-based;
- any pairing is credible, and specific named drinks appear only with authoritative support;
- each internal divider touches both vertical outer borders with no visible gap;
- all frame and divider strokes remain black, closed, and visible in the final raster;
- text has clear padding and does not touch a border or divider.
- one loose standalone food item without any original or edible holder is presented in exactly one physically suitable container; food that already has a vessel, liner, wrapper, skewer, or edible holder receives no additional container.
