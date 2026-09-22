# Default design system

Use this system when the user does not provide a different template or brand guide. It adapts the established 华韦达 investment-recommendation style to HTML and PowerPoint. Interpret that style as a high-density visual research deck, not a minimalist 2 × 2 card deck.

## Canvas and layout

- Use a 16:9 canvas: 1920 x 1080 HTML pixels and 13.333333 x 7.5 inches in PowerPoint.
- Use a pure-white #FFFFFF background.
- Use a 12-column grid with approximately 5% left and right margins.
- Keep covers and chapter dividers restrained. Let evidence-heavy slides carry higher information density.
- Prefer one coherent composition with three to seven evidence zones over four equal text cards surrounded by unused white space.
- On technical, product, process, and industry-structure pages, reserve roughly 30–60% of the content area for a mechanism drawing, product or equipment image, process flow, annotated architecture, map, or data visualization.
- Use a thin title rule, compact source footer, and optional bottom conclusion band to create continuity across the deck.
- Reserve a consistent footer area for sources, scope notes, confidentiality labels, and page numbers.

## Preferred page archetypes

- **Hero mechanism:** one dominant annotated mechanism or product visual plus two to four smaller comparison or evidence modules and a bottom synthesis band.
- **Evidence mosaic:** a decisive chart or table supported by compact callouts, product photographs, benchmarks, or source excerpts.
- **Process or architecture:** a left-to-right or top-to-bottom native flow with a supporting equipment image or generated schematic.
- **Competitive landscape:** a structured matrix, timeline, or positioning map with logos or product thumbnails, not a prose-only list.
- **Risk and recommendation:** a native table or scored framework; imagery is optional when it would not add evidence.

Do not repeat one archetype across an entire section. Match the composition to the argument.

## Color system

| Role | Color |
| --- | --- |
| Primary navy | #12355B |
| Supporting blue | #2B6EAA |
| Light blue field | #EAF2F8 |
| Primary text | #1F2933 |
| Secondary text | #5E6B78 |
| Rules and borders | #C9D5E1 |
| Soft evidence field | #F4F7FA |
| Risk or warning accent | #E86F25 |

Use navy for titles, conclusions, and key numbers. Use supporting blue for structure and navigation. Use orange only for genuine risks, warnings, or contrasts. Subtle blue gradients may be used inside mechanism illustrations or major headers when they improve depth, but keep the slide background pure white.

## Typography

Use font roles consistently rather than mixing fonts decoratively.

| Content | Chinese | English and numbers |
| --- | --- | --- |
| Cover and slide titles | Microsoft YaHei Bold | Times New Roman Bold |
| Section and module headings | Microsoft YaHei Semibold/Bold | Times New Roman Bold |
| Body and tables | Microsoft YaHei | Times New Roman |
| Direct quotations, epigraphs, definition-style excerpts | STKaiti or KaiTi | Times New Roman |
| Notes, captions, source lines, methodology and scope statements | SimSun | Times New Roman |

Use Song type for small factual apparatus because it remains formal and compact. Use Kai type for actual quoted or definition-like language, not as a general small-text font.

HTML fallback stacks:

~~~css
--font-sans-zh: "Microsoft YaHei", "PingFang SC", "Noto Sans CJK SC", sans-serif;
--font-serif-zh: "SimSun", "Songti SC", "Noto Serif CJK SC", serif;
--font-kai-zh: "STKaiti", "KaiTi", "Kaiti SC", serif;
--font-latin: "Times New Roman", Times, serif;
~~~

Recommended PowerPoint ranges:

- deck title: 30–42 pt;
- slide title: 26–32 pt;
- module heading: 18–22 pt;
- body: 16–18 pt where possible;
- sources and notes: 9–11 pt.

Use the same font role in HTML and PowerPoint. Verify that the actual rendering environment has the intended fonts before locking line breaks.

## Information hierarchy

Use a conclusion-first research structure when evidence supports it:

1. Direct subject or supported takeaway title.
2. Primary evidence or mechanism.
3. Counterevidence, limitation, or boundary.
4. Investment or decision implication when relevant.
5. Source and methodology footer.

Avoid generic slogans, empty subtitles, marketing language, decorative badges, pill labels, heavy shadows, and repetitive rounded cards. Use thin rules, restrained fills, imagery, charts, and alignment to create structure.

## Visual assets

- Keep tables, charts, timelines, simple process diagrams, comparison frameworks, annotations, and image labels native and editable.
- Use SVG for icons when available.
- Use images for equipment, photography, complex scientific illustrations, detailed exploded views, and visual explanations that native shapes cannot express efficiently.
- Keep every image independent from titles, labels, and data so it can be moved or replaced.
- Mark technical illustrations as schematic when scale or construction is illustrative.
- Prefer one large content-bearing image over several tiny decorative icons. Avoid image collages with no analytical purpose.
- Generated images should normally exclude labels and long text; overlay those elements natively in HTML and PowerPoint.

## Page conventions

- Keep the cover minimal, with a restrained technical or industrial visual if useful.
- Use plain subject titles for setup and explanatory pages.
- Use takeaway titles only when the slide establishes the stated conclusion.
- Use a bottom conclusion bar only when it adds a decision-relevant synthesis.
- Put source names, dates, units, statistical scope, and assumptions on the slide when they affect interpretation.
- Keep axis-aligned rules and bars truly axis-aligned. Use dedicated rectangles at 0° rotation rather than borders, skewed polygons, or transformed groups.
