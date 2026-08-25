---
name: menu-generator
description: Turn an uploaded dish, dessert, coffee, cocktail, or other food photo into a refined 3:4 fine-dining menu image, dynamically selecting evidence-based Chinese information modules by food or beverage type. Use for restaurant menu posters or single-page editorial menu visuals; do not use for ecommerce product-detail pages or multi-page menu catalogs.
---

# Menu Generator

Create a believable premium-restaurant still-life menu poster from the user's food photo. Preserve the dish's identity and original plating while improving its photographic presentation and adding a subtle editorial information system. The result should feel quiet, refined, and materially real—never like a PPT, UI card, ordinary restaurant menu, or ecommerce layout.

## Required input

Require at least one usable dish or drink photo. If none is attached, ask the user to upload it and stop. Also require the restaurant display name before composition: when it is missing, ask one concise question for the exact name, spelling, language, capitalization, and separator styling, then stop until the user answers. Preserve that display name verbatim. Use user-provided dish name, ingredients, dietary claims, pairing, and price as authoritative. Never invent a restaurant name, price, provenance, dietary claim, alcohol content, or hidden ingredient.

## Workflow

1. Inspect the source image before generating anything. Internally record:

   ```yaml
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

2. Isolate the hero dish before composing the menu. Extract the complete food subject together with its original serving vessel and any integral liner or garnish. Remove the source table, room, hands, unrelated props, and background. Preserve fine edges, handles, translucent glass, steam, and natural gaps; avoid halos, clipped rims, or a sticker-like outline. Read [references/visual-system.md](references/visual-system.md) for the required camera angle and isolation rules.

3. Classify the subject and select its information modules before composing. Read and follow [references/dynamic-information-system.md](references/dynamic-information-system.md). Assign one concise professional menu category label supported by the subject, such as `STARTER`, `MAIN COURSE`, `SIDE`, `DESSERT`, `COCKTAIL`, `COFFEE`, `TEA`, or `NON-ALCOHOLIC`; do not use an unsupported signature or seasonal label as the category. Then select one presentation mode from [references/modes.md](references/modes.md). Prefer Editorial Dish Menu or Ingredient Story Menu; reserve Pairing Menu for drinks, desserts, and pairing-led items. For plated mains, snacks, sides, fruit, pastries, desserts, salads, and other foods, read and follow [references/food-layout.md](references/food-layout.md). For any cocktail, highball, coffee, tea, juice, or other standalone beverage, read and follow [references/beverage-layout.md](references/beverage-layout.md); its beverage-specific geometry overrides the general subject-scale and camera defaults.

4. Draft the selected information modules in Chinese before image generation. Keep copy specific, restrained, and sensory; avoid generic praise such as“美味”“超级好吃”“香喷喷”. Use only the smallest useful set of modules for the classified subject. Food pages use name, short description, supplied price, an evidence-based dining tip, and credible drink pairings as applicable; they never use flavor baselines, ticks, markers, or sensory charts. Standalone beverages use a compact 3–4-axis flavor profile with dimensions appropriate to the drink. Treat marker positions as tendencies, not laboratory measurements. Omit unsupported fields instead of filling them speculatively.

5. Build the visual at exactly 3:4, preferably 1536×2048 px or 1024×1365 px. Use the uploaded photo as the primary image reference. Preserve food proportions, dish type, vessel, and recognizable plating. Present the isolated dish from the prescribed elevated three-quarter frontal view, or use the beverage-specific near-frontal view defined in [references/beverage-layout.md](references/beverage-layout.md). Use image editing/generation for the photographic base, but request no lettering in that base image; reserve quiet space for later typography. Read [references/editorial-style.md](references/editorial-style.md) before deciding layout density, supporting objects, micro-labels, or information-card treatment. Treat a user-supplied ingredient list as explicit evidence for restrained physical ingredient cues outside the vessel. When a dominant flavor ingredient is supplied or strongly evidenced, place one to three recognizable, scale-correct specimens beside the vessel when they improve recognition—for example, one butterfly-pea blossom beside a butterfly-pea drink or two or three natural cinnamon sticks beside a cinnamon-flavored drink. A flower, leaf, or bud normally needs only one intact specimen or a short natural stem. Keep every cue close to but not touching the hero, match the scene's camera and light, and never add an unsupported ingredient.

6. Add menu typography with a deterministic layout method such as SVG/HTML rendering or image compositing. Do not rely on an image model to draw Chinese characters. Apply the type hierarchy in [references/editorial-style.md](references/editorial-style.md). Every page must include one compact primary information panel enclosed by a complete four-sided hairline frame. Put only the selected core modules in it; distribute optional annotations into small secondary nodes instead of enlarging the card. Food panels use stacked identity, dining-tip, and pairing sections as applicable; every internal section divider must extend fully to and physically meet both vertical outer borders. Food panels never include flavor bars. Standalone beverage panels use a compact bar-style flavor profile. The frame must be visibly present in the final raster, not merely defined in the editable source. Keep the visible content inset optically consistent on all four sides; the lowest label, tick, marker, or glyph must retain the same apparent bottom padding as the title has at the top and the content has at the left and right. For standalone beverages, build the upper-right identity cluster in this exact order: supplied restaurant name, a short hairline immediately below it, then the English item name. Center all three on one shared axis. Do not show a category label or an item-index field such as `DRINK / 01` there unless the user explicitly requests it. Food pages may retain the category-based cluster defined in [references/editorial-style.md](references/editorial-style.md).

7. Inspect the final image at full size. Correct it if any required quality gate fails.

## Non-negotiable visual rules

- For plates and bowls, use the approved compact hero scale: the complete vessel with its food should normally occupy about 62–70% of canvas width and 30–38% of canvas height, with roughly 55–68% negative space. Treat 72% width or 40% height as a correction threshold unless the user explicitly requests a closer crop. If the first photographic pass is larger, make one scale-only correction that reduces the vessel, food, integral garnish, sauce, and contact shadow together—about 20% is the normal first adjustment—while preserving the camera, placement, and plating. Small desserts and standalone beverages follow their subject-specific ranges in [references/visual-system.md](references/visual-system.md) and [references/beverage-layout.md](references/beverage-layout.md). Do not shrink the subject until it feels distant.
- Use an ivory, warm-gray, or soft-beige studio background, not pure ecommerce white, dramatic gradients, patterned scenery, or a kitchen environment.
- Aim for natural soft studio light, real material texture, plausible contact shadows, accurate food scale, and editorial food photography.
- Do not produce CGI-looking food, plastic textures, implausible garnish, floating objects, excessive props, or a crowded collage.
- Supporting objects must be few, scale-correct, and tied to visible, user-supplied, or otherwise strongly evidenced ingredients. A single flower, leaf, bud, fruit slice, or other recognizable specimen may sit outside the vessel as an ingredient cue; use two or three pieces only when the ingredient reads more naturally as a small group, such as cinnamon sticks. Never add a new ingredient that changes the dish's meaning.
- Use low-saturation color. Let the food supply the main accent color.
- Default to a slightly elevated three-quarter frontal view: show both the top of the food and the front/side depth of its vessel. Do not switch to flat lay, straight-on elevation, or exaggerated wide-angle perspective.
- Prefer slight asymmetry and quiet visual tension over rigid centering. Typography, cards, labels, and decoration must remain visibly subordinate to the dish.
- Never use an oversized ultra-bold Chinese title, a large opaque information card, dense table-like rows, or large areas of harsh pure-black/pure-white contrast. Structural hairlines are the exception: frames, dividers, flavor baselines, and ticks must render in black.
- A compact four-sided framed information panel is mandatory. All four edges must remain visibly closed at both thumbnail size and 100% inspection. Use a black stroke approximately 1–1.25 px at 1024 px width; never omit the frame or reduce its opacity until it looks gray or disappears. The panel must remain smaller and lighter than the hero, never resembling a dashboard card.
- Text must never touch, cross, sit on top of, or visually merge with a frame, divider, flavor baseline, or tick. Preserve explicit padding around text and verify glyph bounding boxes in the final raster, especially the title against the top border and the last flavor row against the bottom border. The panel's visible top, bottom, left, and right insets must read as equal or intentionally matched; never let the last row collapse the bottom padding.
- Food pages never use flavor baselines, ticks, markers, `Level`, or any sensory chart. Standalone beverage pages use 3–4 relevant dimensions with thin black baselines, five ticks, and a small marker; never use a filled UI progress bar.
- In a food panel, every internal section divider must connect flush to the left and right outer frame edges; floating divider ends are a correction failure.

## Output contract

Return all three:

1. One final 3:4 menu image, displayed or linked for the user.
2. Chinese menu text containing the dynamically selected core and auxiliary modules. Always include the item name; include description, ingredients, flavor, pairing, note, price, or labels only when selected and supported. Include restaurant name or price only when the user supplied them; a clearly fictional neutral wordmark is acceptable when a brand mark is needed for composition.
3. A concise visual rationale covering the chosen mode/style, composition logic, and why each supporting ingredient or object was included.

## Quality gates

Before delivery, confirm:

- the final file is 3:4 and the dish remains recognizably the same dish;
- the hero extraction contains the complete dish and original vessel, with clean edges and no remnants of the source environment;
- the viewpoint shows the food surface and vessel depth from a slightly elevated three-quarter frontal angle, without implausible perspective warping;
- Chinese text is selectable before rasterization or visually checked after rasterization, with no malformed characters, spelling errors, clipping, or microscopic type;
- hierarchy is clear: restaurant name, item identity, dish name, description, details, optional price;
- on standalone beverage pages, the supplied restaurant name is reproduced verbatim and the upper-right cluster reads restaurant name → short hairline → English item name on one centered axis, with no category or `DRINK / 01`-style index unless the user explicitly requested one; on food pages, any category-based identity cluster follows [references/editorial-style.md](references/editorial-style.md);
- the Chinese title is restrained in size and weight, the English subtitle reads as a small label, and metadata is lighter than body copy;
- the information area is compact and editorial rather than a dominant UI card or form;
- the information modules match the classified subject and respect the density budget; unused or unsupported modules are omitted;
- at least one fine-line information frame is present; food panels contain no flavor chart, while standalone beverage panels use 3–4 consistent axes with restrained markers;
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
