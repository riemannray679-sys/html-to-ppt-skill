# Default generation and Keynote compatibility

Use these rules as defaults. An explicit user request, supplied template, brand guide, or source deck remains authoritative. The skill's two-deliverable contract also remains authoritative: the editable PPTX is the primary presentation file and the self-contained HTML is its coordinated companion.

## Output and canvas

- Keep PPTX as the default editable presentation output. This skill also delivers the required self-contained HTML companion in the same run.
- Use 16:9 at 13.333 × 7.5 inches in PowerPoint and 1920 × 1080 pixels in HTML unless the user or a controlling template requires another size.
- Build for minimal layout change when the PPTX is opened in Keynote after PowerPoint generation.

## Fonts

- For external sharing or cross-platform use, default Chinese text to Microsoft YaHei and Latin letters, numbers, symbols, chart labels, and financial figures to Arial.
- Only when the user explicitly says the deck is for their own Mac/Keynote use may Chinese switch to PingFang SC while Latin letters and numbers remain Arial.
- Keep the complete deck to no more than two font families when practical. Use weight, size, color, spacing, or rules—not extra font families—to distinguish quotations, notes, captions, sources, and methodology.
- Do not use font icons or glyph dependencies such as Wingdings or Font Awesome fonts.

## Objects and media

- Prefer ordinary text boxes and basic shapes for editable structure, tables, simple diagrams, labels, and callouts.
- Prefer SVG for icons and logos. Use high-resolution PNG or JPEG for photographic or raster imagery, preserve aspect ratio, and avoid upscaling visibly soft assets.
- Keep charts two-dimensional, flat, and consulting-report-like. Prefer basic shapes, lines, and text or a simple native chart.
- Complex equipment art, scientific illustrations, and photographic assets may remain separate movable images or SVGs. Do not force them into hundreds of decorative native shapes merely to claim editability.

## Features to avoid

- Do not use SmartArt, WordArt, 3D effects, OLE objects, embedded Excel objects, complex gradients, heavy or complex shadows, complex path animation, or Morph by default.
- Use no animation by default. When animation is required, prefer a simple Fade.
- Avoid Office-only effects whose appearance or editability can change during PowerPoint-to-Keynote conversion.

## Mac/Keynote-only styling

When the user explicitly limits the deck to their own Mac/Keynote presentation, the design may use more whitespace, larger type, stronger imagery, and simpler charts. Keep the underlying file as PPTX and retain compatible text, shape, image, and chart structures unless the user explicitly requests a native Keynote artifact.

## Validation

- Confirm slide size, font policy, image quality, object editability, and the absence of unintended unsupported features.
- Render and inspect every slide. When Keynote is available and the task warrants application testing, open a test copy there and inspect representative dense slides, charts, tables, icons, and line wrapping.
- Say that Keynote or PowerPoint compatibility was checked only when the deck was actually opened and inspected in that application.
