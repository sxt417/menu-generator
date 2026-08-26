---
name: menu-generator
description: Turn an uploaded dish, dessert, coffee, cocktail, or other food photo into a refined 3:4 Chinese- or English-language fine-dining menu image, dynamically selecting evidence-based modules by food or beverage type. Use for restaurant menu posters or single-page editorial menu visuals; do not use for ecommerce product-detail pages or multi-page menu catalogs.
---

# Menu Generator

Create a believable premium-restaurant still-life menu poster from the user's food photo. Preserve the dish's identity and original plating while improving its photographic presentation and adding a subtle editorial information system. The result should feel quiet, refined, and materially real—never like a PPT, UI card, ordinary restaurant menu, or ecommerce layout.

## Required input

Before inspecting, drafting, or generating anything, require the user to choose one menu language: Chinese or English. If the user has not already stated the choice, ask exactly one concise opening question—`请选择菜单版本：中文还是英文？`—and stop until the user answers. Do not default to Chinese, infer a language from the restaurant name or conversation language, or silently produce a bilingual version. Record the answer as `menu_language: zh` or `menu_language: en`; it controls every primary title, description, section label, flavor axis, annotation, and returned menu text. A small secondary-language alias may appear only when the applicable layout allows it, and must never turn the page into an unrequested bilingual menu.

After the language is known, require at least one usable dish or drink photo. If none is attached, ask the user to upload it and stop. Also require the restaurant display name before composition: when it is missing, ask one concise question for the exact name, spelling, capitalization, and separator styling, then stop until the user answers. Preserve that display name verbatim regardless of the selected menu language. The restaurant display name must be explicitly provided by the user. Never invent, infer, generate, substitute, translate, transliterate, or fabricate a restaurant name, brand name, studio name, wordmark, fictional identity, or neutral placeholder such as `MAISON`, `ATELIER`, `RESTAURANT`, `STUDIO`, `SAN`, or `TABLE`. Use user-provided dish name, ingredients, dietary claims, pairing, and price as authoritative. Never invent a price, provenance, dietary claim, alcohol content, or hidden ingredient.

## Rule precedence

When instructions overlap or conflict, apply them in this order:

1. Non-negotiable rules and explicit contracts in `SKILL.md`.
2. The subject-specific layout contract: [references/beverage-layout.md](references/beverage-layout.md) for standalone beverages; [references/food-layout.md](references/food-layout.md) for food and desserts.
3. [references/editorial-style.md](references/editorial-style.md).
4. [references/visual-system.md](references/visual-system.md).
5. [references/dynamic-information-system.md](references/dynamic-information-system.md).
6. [references/modes.md](references/modes.md).

Lower-priority references must never override higher-priority rules. `modes.md` controls presentation concept and editorial direction only. It must never override food/beverage classification, hero scale, camera angle, vessel preservation, panel or border geometry, restaurant identity, typography hierarchy, flavor-profile restrictions, supporting-object limits, structural lines, negative space, or information-module limits. When two rules still conflict at the same level, apply the stricter and more deterministic rule.

## Workflow

1. Inspect the source image before generating anything. Internally record:

   ```yaml
   menu_language:
   dish:
     name:
     category:
     main_ingredients:
     supporting_elements:
     cooking_style:
     flavor_profile:
     visual_character:
     container:
     cuisine_style:
     source_viewpoint:
     cutout_scope:
     target_viewpoint:
     flavor_bar:
       sweet:
       sour:
       optional_dimensions:
     information_system:
       category:
       core_modules:
       auxiliary_labels:
       micro_details:
       omitted_fields:
       evidence_notes:
     confidence_notes:
   ```

   Distinguish visible facts from cautious inference. If the exact dish name or a material fact cannot be inferred safely, use a descriptive name or ask one concise question only when the answer would materially change the result.

2. Isolate the hero dish before composing the menu. Extract the complete food subject together with its original serving vessel and any integral liner or garnish. Remove the source table, room, hands, unrelated props, and background. Preserve fine edges, handles, translucent glass, steam, and natural gaps; avoid halos, clipped rims, or a sticker-like outline. If the source shows one loose standalone food item with no plate, bowl, tray, wrapper, liner, or edible container, add one contextually appropriate serving container that supports and presents it. Treat that container as the hero's necessary serving vessel, not as a decorative supporting object. Never apply this completion rule when any original serving or edible container already exists. Read [references/visual-system.md](references/visual-system.md) for the required camera angle, container selection, and isolation rules.

3. Classify the subject and select its information modules before composing. Read and follow [references/dynamic-information-system.md](references/dynamic-information-system.md). Treat every dessert as food, never as a beverage. Assign one concise professional menu category label supported by the subject, such as `STARTER`, `MAIN COURSE`, `SIDE`, `DESSERT`, `COCKTAIL`, `COFFEE`, `TEA`, or `NON-ALCOHOLIC`; do not use an unsupported signature or seasonal label as the category. Then select one presentation mode from [references/modes.md](references/modes.md). Prefer Editorial Dish Menu or Ingredient Story Menu; use Pairing Menu only for standalone beverages or genuinely pairing-led food while retaining the applicable subject contract. For plated mains, snacks, sides, fruit, pastries, desserts, salads, and other foods, read and follow [references/food-layout.md](references/food-layout.md). For any cocktail, highball, coffee, tea, juice, or other standalone beverage, read and follow [references/beverage-layout.md](references/beverage-layout.md); its beverage-specific geometry overrides the general subject-scale and camera defaults.

4. Draft the selected information modules in the chosen menu language before image generation. Keep copy specific, restrained, and sensory; avoid generic praise such as `美味`, `超级好吃`, `香喷喷`, `delicious`, `amazing`, or `mouth-watering`. Use only the smallest useful set of modules for the classified subject. Food pages use name, short description, supplied price, an evidence-based dining tip, and credible drink pairings as applicable; they never use flavor baselines, ticks, markers, or sensory charts. Standalone beverages use a compact 3–4-axis flavor profile with dimensions localized to the selected language and appropriate to the drink. Treat marker positions as tendencies, not laboratory measurements. Omit unsupported fields instead of filling them speculatively.

5. Build the visual at a target 3:4 vertical aspect ratio. Prefer the exact 1536×2048 export; use 1024×1365 as the compact generation format. When exact 3:4 output is supported, prefer exact 3:4. Do not crop or distort the composition solely to compensate for minor generator resolution rounding. Use the uploaded photo as the primary image reference. Preserve food proportions, dish type, original serving vessel, and recognizable plating. Present the isolated dish from the prescribed elevated three-quarter frontal view, or use the beverage-specific near-frontal view defined in [references/beverage-layout.md](references/beverage-layout.md). Use image editing/generation for the photographic base, but request no lettering in that base image; reserve quiet space for later typography. Read [references/editorial-style.md](references/editorial-style.md) before deciding layout density, supporting objects, micro-labels, or information-card treatment. Add a supporting object only when it is supported by visible source evidence, explicit user information, a selected ingredient module, a selected pairing module, or necessary service context directly related to the item. Purely decorative props and objects added only to fill negative space are prohibited. The total number of supporting objects must never exceed three.

6. Add menu typography with a deterministic layout method such as SVG/HTML rendering or image compositing. Do not rely on an image model to draw any final lettering. Apply the language-aware type hierarchy in [references/editorial-style.md](references/editorial-style.md). Every page must include one compact primary information panel enclosed by a complete four-sided hairline frame. Put only the selected core modules in it; distribute optional annotations into small secondary nodes instead of enlarging the card. Food panels use stacked identity, dining-tip, and pairing sections as applicable; every internal section divider must extend fully to and physically meet both vertical outer borders. Food and desserts never include flavor bars, sensory ticks, numeric scales, or structured flavor charts; their flavor information may appear only as concise descriptive words or textual tasting notes. Standalone beverage panels use the fixed compact bar-style flavor profile. The frame must be visibly present in the final raster, not merely defined in the editable source. Keep the visible content inset optically consistent on all four sides; the lowest label, tick, marker, or glyph must retain the same apparent bottom padding as the title has at the top and the content has at the left and right. Food pages use the supplied restaurant name above the concise professional category in the upper-right identity cluster. Standalone beverages use the supplied restaurant name, a short hairline immediately below it, then the item name in the selected menu language. Center each cluster on one shared axis. Do not show any category, `DRINK / 01`, `BEVERAGE / 02`, `MENU / 03`, or other index on beverage pages unless the user explicitly requests a numbering system.

7. Inspect the final image at full size. Correct it if any required quality gate fails.

## Non-negotiable visual rules

- For plates and bowls, use the approved compact hero scale: the complete vessel with its food should normally occupy about 62–70% of canvas width and 30–38% of canvas height, with roughly 55–68% negative space. Treat 72% width or 40% height as a correction threshold unless the user explicitly requests a closer crop. If the first photographic pass is larger, make one scale-only correction that reduces the vessel, food, integral garnish, sauce, and contact shadow together—about 20% is the normal first adjustment—while preserving the camera, placement, and plating. Small desserts and standalone beverages follow their subject-specific ranges in [references/visual-system.md](references/visual-system.md) and [references/beverage-layout.md](references/beverage-layout.md). Do not shrink the subject until it feels distant.
- Use an ivory, warm-gray, or soft-beige studio background, not pure ecommerce white, dramatic gradients, patterned scenery, or a kitchen environment.
- Aim for natural soft studio light, real material texture, plausible contact shadows, accurate food scale, and editorial food photography.
- Do not produce CGI-looking food, plastic textures, implausible garnish, floating objects, excessive props, or a crowded collage.
- The original serving vessel is part of the subject identity and must be preserved. Never replace, redesign, recolor, simplify, restyle, resize disproportionately, or substitute the original plate, bowl, cup, glass, tray, serving board, container, or packaging vessel unless the user explicitly requests vessel replacement. Improve presentation through composition, lighting, spacing, typography, cropping, supported ingredients, and background treatment—not by silently replacing the vessel.
- Container completion applies only to one loose standalone food item that has no original plate, bowl, tray, wrapper, liner, packaging vessel, or edible container. Add exactly one understated, service-plausible container suited to the food's shape, weight, moisture, and eating context. It becomes part of the hero silhouette and must remain subordinate to the food. Never add a second container, place an existing vessel inside another vessel, or treat an edible shell, cup, cone, leaf wrap, skewer, or similar integral holder as containerless.
- Every supporting object must have a clear ingredient, pairing, or service rationale and must be supported by visible source evidence, explicit user information, a selected ingredient module, a selected pairing module, or necessary service context directly related to the item. Purely decorative props are prohibited. Do not add unrelated flowers, fabrics, plants, bottles, containers, or utensils, and do not add objects only to fill negative space. The total number of supporting objects must never exceed three.
- Use low-saturation color. Let the food supply the main accent color.
- Default to a slightly elevated three-quarter frontal view: show both the top of the food and the front/side depth of its vessel. Do not switch to flat lay, straight-on elevation, or exaggerated wide-angle perspective.
- Prefer slight asymmetry and quiet visual tension over rigid centering. Typography, cards, labels, and decoration must remain visibly subordinate to the dish.
- Never use an oversized ultra-bold primary-language title, a large opaque information card, dense table-like rows, or large areas of harsh pure-black/pure-white contrast. Structural hairlines are the exception: frames, dividers, flavor baselines, and ticks must render in black.
- A compact four-sided framed information panel is mandatory. All four edges must remain visibly closed at both thumbnail size and 100% inspection. Use a black stroke approximately 1–1.25 px at 1024 px width; never omit the frame or reduce its opacity until it looks gray or disappears. The panel must remain smaller and lighter than the hero, never resembling a dashboard card.
- Text must never touch, cross, sit on top of, or visually merge with a frame, divider, flavor baseline, or tick. Preserve explicit padding around text and verify glyph bounding boxes in the final raster, especially the title against the top border and the last flavor row against the bottom border. The panel's visible top, bottom, left, and right insets must read as equal or intentionally matched; never let the last row collapse the bottom padding.
- Food pages never use flavor baselines, ticks, markers, `Level`, or any sensory chart. Standalone beverage pages use 3–4 relevant dimensions with thin black baselines, five ticks, and a small marker; never use a filled UI progress bar.
- In a food panel, every internal section divider must connect flush to the left and right outer frame edges; floating divider ends are a correction failure.

## Output contract

Return all three:

1. One final target-3:4 vertical menu image, displayed or linked for the user; use the preferred exact or accepted compact export defined above.
2. Menu text in the user's selected language containing the dynamically selected core and auxiliary modules. Always include the item name; include description, ingredients, flavor, pairing, note, price, or labels only when selected and supported. Include the restaurant name and price only when the user supplied them. Never create a fictional, neutral, substitute, translated, or placeholder identity.
3. A concise visual rationale covering the chosen mode/style, composition logic, and why each supporting ingredient or object was included.

## Quality gates

Before delivery, confirm:

- the final file uses the target 3:4 vertical aspect ratio—preferably 1536×2048, with 1024×1365 accepted as the compact generator format—and the dish remains recognizably the same dish;
- the user explicitly selected Chinese or English before any inspection or generation, and all primary menu copy consistently uses that language without an unrequested bilingual mixture;
- the hero extraction contains the complete dish and original vessel, with clean edges and no remnants of the source environment;
- a single loose standalone food item with no original or edible holder has exactly one suitable serving container, while any item that already has a vessel, liner, wrapper, or integral edible holder receives no additional container;
- the viewpoint shows the food surface and vessel depth from a slightly elevated three-quarter frontal angle, without implausible perspective warping;
- all menu text is selectable before rasterization or visually checked after rasterization, with no malformed characters, spelling errors, clipping, or microscopic type;
- hierarchy is clear: restaurant name, item identity, dish name, description, details, optional price;
- on standalone beverage pages, the supplied restaurant name is reproduced verbatim and the upper-right cluster reads restaurant name → short hairline → selected-language item name on one centered axis, with no category or index unless the user explicitly requested a numbering system; on food pages, the cluster reads supplied restaurant name → concise professional category and does not switch to a slogan, subtitle, or decorative index;
- the primary-language title is restrained in size and weight, any secondary-language alias reads as a small label, and metadata is lighter than body copy;
- the information area is compact and editorial rather than a dominant UI card or form;
- the information modules match the classified subject and respect the density budget; unused or unsupported modules are omitted;
- at least one fine-line information frame is present; food and dessert panels contain no flavor chart, while standalone beverage panels use 3–4 consistent axes with restrained markers;
- the final raster visibly shows all four sides of the primary information frame; if any edge blends into the background, darken or thicken it before delivery;
- every structural line is black in the final raster, including the outer frame, food-section dividers, and beverage flavor baselines and ticks; every food-section divider meets both vertical outer borders, while accent markers may retain the selected muted accent color;
- no glyph intersects or touches any structural line; the title has clear space above it and flavor labels end before their baselines begin;
- the last visible glyph, tick, baseline, or marker retains bottom padding that visually matches the panel's top and side padding;
- on beverage pages using a detached information panel, the panel sits diagonally above the vessel with a nearest-edge gap of roughly 3–6% of canvas height, unless the user's reference clearly calls for another relationship;
- the hero scale matches its subject-specific reference range and reads clearly at thumbnail size; for plates and bowls, verify the complete vessel stays near 62–70% of canvas width and 30–38% of canvas height, and correct anything above the 72% width or 40% height threshold unless a closer crop was requested;
- supporting objects number no more than three and every one has a clear ingredient, pairing, or service rationale; when a dominant flavor cue is used, its count, scale, proximity, and material appearance are plausible;
- the page reads as a real fine-dining or modern bistro menu rather than advertising creative;
- ingredients, pairings, and claims are evidence-based;
- no important source-photo detail has been unintentionally changed.
