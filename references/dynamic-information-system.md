# Dynamic menu information system

Use this reference to decide what information a menu page should contain. It governs content selection and density. Layout geometry remains governed by [visual-system.md](visual-system.md), [editorial-style.md](editorial-style.md), and, for standalone beverages, [beverage-layout.md](beverage-layout.md).

## Core principle

Do not give every dish the same information structure. First classify the subject, then select the smallest set of modules that explains its identity and experience. The result should resemble curated editorial annotations around food, not a fixed form, dashboard, or traditional menu table.

All primary communication must use the menu language explicitly selected at the start of the workflow. For `zh`, use Chinese primary copy and allow tiny English labels such as `MAIN INGREDIENT`, `PAIRING`, or a category name only as subordinate accents. For `en`, use English for every essential title, description, section label, flavor axis, annotation, and returned text; a tiny Chinese alias is optional only when useful and must remain subordinate. Do not create an unrequested bilingual menu. Menu or item numbering appears only when the user explicitly requests a numbering system.

## Evidence and claims

- Treat user-supplied names, ingredients, price, alcohol, dietary claims, provenance, signature status, and pairing as authoritative.
- Never invent a price, alcohol content, hidden ingredient, provenance, dietary claim, restaurant accolade, or signature status.
- A descriptive item name, conservative sensory tendency, and credible generic pairing category may be inferred when well supported. State uncertainty internally and omit doubtful fields.
- Show `SIGNATURE`, `MUST TRY`, `CHEF'S PICK`, `招牌`, or a signature year only when the user supplied that status, explicitly requested the mark, or the project context establishes it.

## Classification

Choose one primary category:

1. **Main course / full meal** — plated mains, bowls, substantial savory dishes.
2. **Snack / fruit / dessert** — light bites, fruit plates, pastries, and desserts. Desserts always follow the food layout and never use beverage flavor charts.
3. **Cocktail / alcoholic beverage** — only when alcohol is supplied or confidently established.
4. **Coffee / tea / non-alcoholic beverage** — coffee, tea, soda, juice, mocktail, and uncertain sparkling drinks without verified alcohol.
5. **Ingredient-led presentation** — produce, salad, tasting component, or dish whose ingredient relationship is the story.
6. **Signature / Chef Special** — only with supported signature, seasonal, limited, or chef-special status.

## Selection sequence

Before composing, determine:

1. the primary category;
2. the most important supported ingredient;
3. whether zero to three evidence-supported ingredient, pairing, or necessary service objects deserve annotation;
4. for a standalone beverage, the three or four most relevant sensory dimensions;
5. for food, whether a drink pairing materially helps;
6. for food, whether a one- or two-sentence dining tip adds useful service guidance;
7. whether signature or recommendation status is supported;
8. the smallest combination of modules that communicates the item well.

Record the chosen core modules, auxiliary labels, micro-details, and omitted unsupported fields before layout.

## Density budget

- Select **2–4 core information modules**.
- Add **1–3 auxiliary labels**.
- Add **1–2 micro structural details**.
- Preserve broad negative space. Remove a low-priority module before shrinking type or enlarging the primary card.
- Do not place all available modules on one page.
- Do not force all selected modules into the primary card. Prefer one compact framed primary card plus one main-ingredient label, at most one object annotation node, and the required category mark. Add an index only when the user explicitly requested a numbering system.

## Priority hierarchy

- **Level 1:** the food or beverage itself; item name in the selected menu language.
- **Level 2:** one-sentence description; main ingredients or verified recipe.
- **Level 3:** supplied price; beverage flavor profile; food dining tip; food drink pairing.
- **Level 4:** main-ingredient label; recommendation badge; object annotation; signature mark; category; user-requested menu index.

Level 4 elements must remain tiny and subordinate. Any secondary-language alias belongs primarily at this level.

## Module catalog

### Basic info

- **Primary-language item name:** required, concise, accurate, first typographic level.
- **Secondary-language alias:** optional, much smaller than the primary name; uppercase and tracked when it is English.
- **One-sentence description:** one or two restrained lines; explain the sensory relationship without marketing language.
- **Price:** show only when supplied.

### Dish description

Use for mains, snacks, salads, fruit, desserts, and full meals. Combine name, one-sentence description, and supplied price. Do not repeat the same description elsewhere.

### Main ingredients

Use for food dishes. List the three to six most important supported ingredients, separated cleanly. Do not enumerate every seasoning.

### Ingredient list

Use for cocktails, coffee, special beverages, and ingredient-led items when composition itself has value. A beverage may show a fuller verified recipe. Food dishes should usually use only main ingredients. Never infer hidden spirits, syrups, dairy, allergens, or garnish.

### Flavor profile

Use a compact visual profile on standalone beverage pages. Food and dessert pages never use sensory baselines, ticks, markers, `Level`, numeric scales, radar graphics, or a structured flavor profile; express their flavor character through concise descriptive words or textual tasting notes instead. For beverages, choose three or four representative dimensions rather than a fixed universal set. Possible axes include sweet, sour, bitter, body, fresh, creamy, herbal, salty, and refreshing.

All baselines and ticks are black as defined in [editorial-style.md](editorial-style.md). Use one muted accent only for markers. Flavor positions are approximate sensory tendencies, not measurements.

### Alcoholic drink profile

For a verified cocktail or alcoholic beverage, prefer three or four selected-language axes from these mappings:

- `酒体` / `Level`
- `甜度` / `Sweet`
- `酸度` / `Sour`
- `苦度` / `Bitter`
- `咸鲜感` / `Salty`
- `奶油感` / `Creamy`
- `清爽度` / `Fresh`

Use `酒体` only when alcohol is established. Do not use it for coffee, tea, soda, juice, mocktails, or uncertain drinks.

### Taste category

Use one tiny footer label to summarize the overall character. Render only the side that matches the selected language, for example:

- `酸甜 / SWEET & SOUR`
- `清爽 / REFRESHING`
- `浓郁`
- `醇厚`
- `酒体突出 / SPIRIT FORWARD`
- `轻盈`
- `奶油感`
- `烟熏`
- `清鲜`

Show one category only. Do not duplicate every flavor axis in prose.

### Pairing

Recommend one to three credible pairings. If the user did not request alcohol, allow or prefer tea, coffee, sparkling water, or another non-alcoholic category. Avoid specific vintages, brands, or ingredients without evidence.

### Chef's note / menu tip

For food, use at most one or two short sentences under `用餐提示` for Chinese or `DINING TIP` for English, with an optional subordinate translation label. Give genuinely useful service guidance, such as eating while hot, squeezing a visible citrus wedge, mixing a visible component, or sharing. Do not write a paragraph and do not invent preparation instructions or rituals that are not supported.

### Food drink pairing

For food, use `推荐搭配` for Chinese or `RECOMMENDED DRINK` for English, with one to three credible drink categories when pairing adds value. Generic categories such as清酒、清爽型鸡尾酒、气泡水、冷泡茶、咖啡, sake, a refreshing cocktail, sparkling water, cold-brew tea, or coffee may be inferred conservatively. Use a specific cocktail, producer, vintage, brand, or menu item only when the user supplied it or an authoritative project menu establishes it.

### Main ingredient label

Use one tiny technical annotation near the hero or a visible supported ingredient:

```text
MAIN INGREDIENT
CARROT
```

or, for Chinese:

```text
主要食材
胡萝卜
```

It must use a complete black fine-line frame, tiny type, and technical or specimen-label restraint. It must not compete with the primary card.

### Object annotation

Annotate no more than three intentionally presented supporting objects. Every supporting object must have an ingredient, pairing, or necessary service rationale and must be supported by visible source evidence, explicit user information, a selected ingredient module, a selected pairing module, or necessary service context directly related to the item. Purely decorative objects and objects added only to fill negative space are prohibited. Do not label every object.

### Recommendation badge

When supported, use a restrained `[ SIGNATURE ]`, `[ MUST TRY ]`, `[ CHEF'S PICK ]`, or `[招牌]`. Never use promotional phrases such as `爆款`, `必吃榜`, or `人气第一`.

### Signature mark

When supported, place a tiny corner mark such as `SIGNATURE` or `HOUSE SIGNATURE` with a supplied or explicitly requested year. Do not add it to every page.

### Category and user-requested menu index

Use the subject-appropriate professional category required by the identity contract. A menu or item index may appear only when the user explicitly requests a numbering system. Never generate a random or decorative `MENU / 03`, `PLATE / 03`, `DRINK / 04`, or similar index.

## Content templates

### Template A — Main course / full meal

Choose two to four core modules from:

- selected-language name and optional secondary-language alias;
- one-sentence description;
- supplied price;
- one evidence-based dining tip;
- one to three credible drink pairings;
- optionally three to six main ingredients when they materially clarify the dish.

Never add a flavor chart to this template. Follow [food-layout.md](food-layout.md).

Possible auxiliary nodes: one main-ingredient label and one supported object annotation. Add a menu index only when explicitly requested by the user.

### Template B — Snack / fruit / dessert

Prefer name, one-sentence description, supplied price, an optional dining tip, and credible drink pairing. Add main ingredients or one object annotation only when useful. Never add a flavor chart. Keep the page lighter than a main-course page and follow [food-layout.md](food-layout.md).

### Template C — Verified cocktail / alcoholic beverage

Prefer name, fuller verified ingredient list, a three- or four-axis alcoholic drink profile, one taste-category footer, and supplied price. Optional nodes include one main-ingredient label, one visible garnish annotation, and a supported recommendation badge. Apply [beverage-layout.md](beverage-layout.md).

### Template D — Coffee / tea / non-alcoholic special

Prefer name, verified ingredients, a three- to four-axis profile, one main-ingredient label, and optional pairing. Never show `酒体` or alcohol strength. Apply [beverage-layout.md](beverage-layout.md).

### Template E — Ingredient-led presentation

Prefer name, one-sentence ingredient story, three to six main ingredients, an optional dining tip, and a credible drink pairing. Never add a flavor chart to food. Use one or two supported ingredient annotations to explain relationships without turning the page into a recipe diagram, and follow [food-layout.md](food-layout.md).

### Template F — Signature / Chef Special

Use the appropriate base template for the food or drink, then add at most one supported recommendation badge or signature mark. Signature status does not justify adding unsupported provenance, price, ingredients, or claims.

## Composition requirements

- The mandatory primary card remains compact, transparent or nearly transparent, and fully enclosed by a black four-sided frame.
- A food card uses stacked identity, dining-tip, and pairing sections as applicable. Every divider between those sections runs fully from the left outer border to the right outer border and meets both vertical edges with no gap.
- Food cards never use flavor bars. Standalone beverage cards use a compact three- or four-axis flavor profile.
- Do not turn the dynamic information system into one large card. Distribute lower-priority information into a few tiny annotation nodes.
- Every drawn line is black: frames, dividers, flavor baselines, ticks, micro-frames, and annotation rules.
- No glyph may touch or overlap any line. Preserve the padding and raster QA rules in [editorial-style.md](editorial-style.md).
- Typography, badges, annotations, and any user-requested index must remain subordinate to the hero.

## Dynamic-system QA

Before delivery, confirm:

- one primary category and one matching template were selected;
- only two to four core modules were used;
- auxiliary labels and micro-details stay within the density budget;
- primary communication consistently uses the selected menu language and any secondary language is only a micro-label or alias;
- ingredients, price, alcohol, signature status, and claims are supported;
- alcoholic and non-alcoholic drink profiles are not confused;
- food and dessert pages contain no flavor baselines, ticks, markers, `Level`, numeric scales, radar graphics, or sensory chart;
- each food-section divider touches both vertical outer frame edges;
- the primary card is compact and lower-priority information is distributed sparingly;
- all structural lines are black and no text intersects them;
- unsupported modules are omitted rather than filled speculatively.
