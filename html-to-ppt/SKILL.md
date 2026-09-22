---
name: html-to-ppt
description: Generate one self-contained fixed-layout HTML presentation and one matching PPTX in a single uninterrupted invocation, with research-grade analysis, meaningful visual assets, and an editable narrative and data layer. Use when the user asks for one-click HTML plus PowerPoint creation, wants to design slides in HTML before PowerPoint, wants HTML converted into an editable deck, or needs image-rich industry-research, investment-committee, technical, market-sizing, or project-report slides. Default to a 16:9 pure-white and deep-navy (#12355B) high-density investment-research style unless the user supplies another template. Always deliver both .html and .pptx in the same final response; never pause between them, silently omit imagery, or substitute screenshots, PDF conversion, or full-slide raster images for editable PowerPoint content.
---

# HTML to editable PowerPoint

## Core contract

Create two coordinated deliverables:

1. One self-contained HTML file containing every slide.
2. One PPTX with the same slide count, content, layout, and visual hierarchy.

Treat invocation of this skill as authorization to create, validate, and deliver both files in one continuous run. Do not stop after the HTML, ask whether to continue to PowerPoint, or require a separate approval for the PPTX. Send the final response only after both deliverables are ready, unless a genuine technical or authorization blocker prevents completion.

Keep titles, body text, tables, data charts, shapes, conclusion bars, labels, and arrows native and editable in PowerPoint. Keep photos, equipment renders, scientific illustrations, and other complex visuals as separate movable and replaceable image or SVG objects. Treat this as hybrid editability: the analytical narrative stays editable while complex imagery remains an independent replaceable layer. Never satisfy editability by placing a screenshot of the HTML or a full-slide image into PowerPoint.

Do not omit meaningful visuals merely to maximize native editability. For slides about equipment, products, physical mechanisms, scientific processes, system architecture, market structure, or competitive alternatives, create or source an appropriate content-bearing visual and use the same asset in HTML and PPTX. If image generation or retrieval is unavailable, build a native schematic rather than falling back to empty text cards.

When working in ChatGPT or Codex, load and follow the available Presentations skill before creating the PPTX. Use the platform's supported presentation-generation tools and render-and-verify workflow. If the current environment cannot create a real PPTX, state that limitation instead of presenting a screenshot as an editable deck.

## Load the bundled guidance

- Read [references/design-system.md](references/design-system.md) before designing slides without a user-supplied template.
- Read [references/content-visual-standard.md](references/content-visual-standard.md) before outlining or producing analytical slides.
- Read [references/html-ppt-contract.md](references/html-ppt-contract.md) before implementing either deliverable.
- Use [assets/base-slide.html](assets/base-slide.html) as the HTML starting point when practical.
- Read [references/universal-model-prompt.md](references/universal-model-prompt.md) when the user wants a portable prompt or a GitHub package for ChatGPT, GLM, Claude, Gemini, or another model.

An explicit user template or brand guide overrides the default design system. Preserve the two-file and editability contracts unless the user explicitly changes them.

## Workflow

### 1. Build the argument and evidence

Use the content and decisions already established in the current conversation. Ask a clarification only when missing information would materially change the deliverables and cannot be resolved with a reasonable assumption. If the request supplies enough content or an agreed outline, proceed immediately without repeating questions. Do not create an artificial approval checkpoint merely because the workflow contains an HTML stage and a PPTX stage.

Create a page-by-page plan that gives every slide one clear analytical job. For each analytical slide, record the question, supported conclusion, mechanism or reasoning, concrete evidence, boundary or counterpoint, decision implication, and intended visual. Preserve exact supplied wording when the user requests strict reproduction. Separate facts, assumptions, hypotheses, and illustrative schematics. Keep source notes attached to the claims they support.

Use provided source material first. When the user requests research or the available environment supports it, fill material evidence gaps with current, authoritative sources and cite them. Do not pad a slide with definitions or generic advantages when the decision depends on maturity, performance, bottlenecks, economics, competitive position, or risk. A slide that could be written without examining the project or industry evidence is not deep enough.

### 2. Build one shared slide specification

Use one internal slide specification for both outputs. Record for every element:

- slide ID and reading order;
- semantic type;
- exact text and intentional line breaks;
- x, y, width, and height on a 1920 x 1080 canvas;
- fill, stroke, typography, padding, and alignment;
- source asset and crop;
- visual purpose, provenance, and whether the asset is factual, illustrative, or schematic;
- editability requirement;
- connection endpoints for arrows and flows;
- source or citation when applicable.

Do not independently redesign the PPT after finishing the HTML. Both files must derive from the same specification.

### 3. Create the visual assets

Plan and create the visual assets before final slide layout. Reuse user-supplied images when suitable. Otherwise retrieve authoritative product or industry visuals, generate clean technical illustrations, or build native vector schematics. Technical, product, process, and industry-structure slides should normally devote 30–60% of the content area to a meaningful visual rather than small decorative icons.

Keep generated or retrieved images free of evidence-bearing text whenever possible. Add labels, numbers, arrows, and conclusions as native HTML and PowerPoint objects. Mark generated technical art as schematic when it could be mistaken for a factual photograph or exact engineering drawing. Embed each accepted visual into the standalone HTML and insert the same source asset as an independent PPTX object. Do not continue with an unexplained blank image region or silently drop an asset.

### 4. Create the HTML

Create a single standalone .html file. Put all slides in that file as fixed 1920 x 1080 sections. Inline the CSS and SVG assets, and embed required images as data URIs so the file remains viewable without network access or companion asset folders. Do not use responsive reflow, animation, external web fonts, or runtime content generation.

Keep text as HTML text. Keep data and table values in structured markup. Add stable element IDs and data-ppt-* semantics described in the HTML-PPT contract. Use explicit line breaks only where the layout requires them.

Render and inspect the HTML before producing the PPTX. Fix clipping, crowding, weak hierarchy, unreadable sources, inconsistent spacing, missing assets, shallow evidence, and pages that have collapsed into repetitive text cards. Then proceed directly to the PPTX in the same run without waiting for user confirmation.

### 5. Create the editable PPTX

Map the shared specification to the 16:9 PowerPoint canvas. Create native PowerPoint objects for:

- titles, body copy, quotations, notes, and sources;
- rectangles, rounded rectangles, lines, and simple diagram shapes;
- tables and data charts;
- arrows, timelines, flow relationships, and conclusion bars.

Insert SVG icons and complex visual assets as separate objects. Use fixed lines or polylines with arrowheads when exact routing matters. Use dynamic connectors only when the user needs nodes to be rearranged later, then verify their routing.

Use native axis-aligned rectangles for vertical bars and horizontal rules. Set their rotation to exactly 0 degrees and map explicit x, y, width, and height values from the shared specification. Do not approximate a bar with a skewed polygon, rotated line, CSS border artifact, or transformed group.

Group elements by logical module and assign useful object names when supported. Keep citations in the slide footer or speaker notes according to the requested design.

### 6. Compare and correct

Render the PPTX at the same 16:9 aspect ratio as the HTML. Compare the two slide by slide. Correct:

- text wrapping and overflow;
- font substitution;
- margins, padding, and alignment;
- arrow endpoints and paths;
- table row and column geometry;
- icon or image crops;
- missing images, low-resolution visuals, or asset mismatches between formats;
- unintended rotation, slanted rules, unequal card edges, or coordinate-rounding drift;
- missing citations or source notes;
- slide count and order.

Prefer content cuts or layout correction over unreadably small type. Do not claim visual parity until the rendered outputs have been inspected.

Reject an output in which a planned visual is absent from either format. Reject an output in which an intended vertical or horizontal element is visibly non-axis-aligned. Prefer a deliberate mixed-media page over a visually empty but technically editable one.

### 7. Deliver

Return exactly the two primary files unless the user asks for more:

- 项目名_演示稿.html
- 项目名_v1.0（HTML同版可编辑）.pptx

Deliver both links together in the same final response. State any material element that remains non-editable. Do not deliver internal screenshots, temporary renderings, manifests, or build files unless requested.
