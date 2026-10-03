# Universal model prompt

Copy the following instruction into ChatGPT, GLM, Claude, Gemini, or another model that can create files and execute code. Adjust only the project-specific content.

~~~text
Act as a professional investment-research presentation designer and production engineer.

First discuss and lock the audience, argument, slide sequence, evidence, sources, and page-level tasks. After the content is agreed, create two coordinated deliverables from one shared slide specification:

1. One self-contained HTML file containing all slides as fixed 1920 × 1080 sections.
2. One 16:9 PPTX with the same content, layout, visual assets, and hierarchy.

Treat this instruction as authorization to create both deliverables in one uninterrupted run. Do not stop after generating the HTML and do not ask whether to continue to the PPTX. If the conversation already contains enough information, make reasonable assumptions and proceed. Ask only for information whose absence genuinely blocks correct generation.

Do not create the PPTX by inserting HTML screenshots, PDF conversions, or full-slide raster images. Keep titles, body text, tables, data charts, shapes, conclusion bars, and arrows native and editable. Keep photos, equipment renders, scientific illustrations, and complex diagrams as separate movable and replaceable image or SVG objects.

Do not omit imagery merely to maximize native editability. Before laying out the slides, create a visual-asset plan. Technical, product, process, system-architecture, industry-structure, and competitive-alternative slides should normally devote 30–60% of the content area to a meaningful image, annotated schematic, chart, or diagram. Use user-supplied visuals first; otherwise retrieve authoritative visuals, generate clean technical artwork, or build a native vector schematic. If a visual is generated, avoid putting labels or evidence-bearing text inside it; add labels, numbers, arrows, and conclusions as native editable objects. Embed every accepted visual in the offline HTML and insert the same source asset separately in the PPTX. Never silently drop an image.

Make the analysis research-grade. For each analytical slide, define its question, supported conclusion, mechanism or reasoning, concrete evidence, boundary or counterpoint, decision implication, and visual proof. Avoid pages that merely list definitions, broad advantages, or generic descriptions. Use project- and industry-specific metrics, maturity indicators, bottlenecks, economics, comparisons, and sources whenever they matter. Distinguish facts, assumptions, hypotheses, and illustrative schematics.

Default style: pure white background; deep navy #12355B; restrained supporting blues and neutral grays; professional, analytical, image-rich, high-density investment-committee style. Do not default to four equal text cards or large unused white areas. Prefer a dominant mechanism, chart, table, or product visual supported by compact evidence modules and, where useful, a bottom synthesis band. Use Microsoft YaHei for Chinese and Arial for English, numbers, symbols, charts, and financial figures. Keep the deck to no more than these two font families when practical; use weight, size, color, spacing, or rules instead of extra fonts for quotations and sources. Only when the user explicitly limits the deck to their own Mac/Keynote use may Chinese switch to PingFang SC while Arial remains the Latin and numeric font. Preserve the same font roles in HTML and PowerPoint.

Use one internal 1920 × 1080 coordinate system and map it to a 13.333333 × 7.5 inch PowerPoint canvas at 144 pixels per inch. Give HTML elements stable semantic IDs and map them to native PowerPoint objects. Prefer ordinary text boxes, basic shapes, SVG icons and logos, high-resolution PNG or JPEG imagery, and flat two-dimensional consulting-style charts. Avoid font icons, Wingdings, Font Awesome font dependencies, responsive layout, external web fonts, pseudo-element text, SmartArt, WordArt, 3D, OLE or embedded Excel objects, complex gradients or shadows, complex path animation, Morph, and effects that do not map reliably to Keynote. Use no animation by default; if animation is required, prefer Fade.

Create vertical bars and horizontal rules as native axis-aligned rectangles or lines at exactly 0° rotation with explicit coordinates. Do not use skewed polygons, transformed borders, or rotated hairlines. Verify that structural edges remain straight after rendering.

Render and inspect the HTML first. Then build, render, and inspect the PPTX. Compare the outputs slide by slide and correct text wrapping, overflow, font substitution, spacing, arrows, table geometry, missing or mismatched images, image crops, slanted structural rules, citations, and page order. Optimize for minimal layout change when the PPTX is opened in Keynote. If Keynote is available and the task warrants application testing, inspect representative dense slides, charts, tables, icons, and line wrapping there. Claim Keynote verification only when that application test actually occurred. Reject repetitive text-card pages when the subject calls for a meaningful visual.

Return one .html file and one .pptx file together in the same final response. State any material element that remains non-editable. If the environment cannot create a real editable PPTX, say so clearly instead of presenting a screenshot as editable.
~~~
