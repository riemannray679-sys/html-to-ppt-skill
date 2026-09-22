# HTML–PPT implementation contract

## Shared coordinate system

Use 1920 x 1080 as the canonical HTML canvas. Map it to a 13.333333 x 7.5 inch PowerPoint slide.

~~~text
x_inches = x_pixels / 144
y_inches = y_pixels / 144
width_inches = width_pixels / 144
height_inches = height_pixels / 144
~~~

Keep the same geometry in both deliverables. Do not eyeball the PowerPoint layout after HTML approval.

Use integer pixel coordinates for axis-aligned shapes in the shared specification. Preserve at least 4 px of width for visible structural rules so antialiasing does not make them appear crooked. Map coordinates numerically; do not infer PowerPoint geometry from a browser screenshot.

## HTML structure

Create one HTML document with one fixed-size section per slide:

~~~html
<section class="slide" data-slide-id="slide-01" aria-label="Slide 1">
  <h1 data-ppt-type="text" data-ppt-id="slide-01-title">Slide title</h1>
</section>
~~~

Give every meaningful element a stable data-ppt-id. Use data-ppt-type values from this set:

- text
- shape
- image
- svg
- line
- connector
- table
- chart
- group

Optional semantic attributes:

- data-editable="true|false"
- data-from="element-id"
- data-to="element-id"
- data-source-id="source-id"
- data-layer="background|content|annotation|footer"

Use absolute positions for final slide elements. Flexbox or grid may help during composition, but freeze computed positions before creating the PPTX.

## Element mapping

| HTML element | PPT representation |
| --- | --- |
| Text node or heading | Native text box |
| Bordered or filled block | Native shape |
| Simple line or arrow | Native line or polyline |
| Relationship connector | Native connector when rearrangement matters; otherwise fixed line |
| Semantic table | Native table, or grouped cell shapes when strict geometry matters |
| Data-backed chart | Native chart with embedded data |
| SVG icon | Independent SVG object |
| Photograph or complex illustration | Independent raster image |
| Full slide | Never convert to a single image for the editable PPTX |

Every image planned in the specification must be present in both deliverables. In HTML, embed the accepted file bytes as a data URI. In PowerPoint, insert the same accepted source file as a separate object. Do not replace the image with an empty frame, external URL, placeholder, or screenshot of a larger page.

## Text rules

- Keep text as text in both outputs.
- Preserve exact wording, punctuation, units, and intentional line breaks.
- Specify font family, size, weight, line height, alignment, and text-box padding.
- Disable uncontrolled auto-fit. Fix overflow by revising layout or content, not by silently shrinking type.
- Do not put meaningful text in CSS pseudo-elements, SVG outlines, or raster images.
- Use the same installed font or approved fallback in the HTML renderer and PowerPoint.

## Arrow and flow rules

- Store both semantic endpoints and final visual coordinates.
- Use fixed coordinates for presentation fidelity.
- Use dynamic connectors only when node movement is a user requirement.
- Route lines behind nodes and labels unless the reference explicitly shows otherwise.
- Group fixed arrows with the logical module they belong to when supported.

## Axis-aligned geometry rules

- Represent a vertical bar as a rectangle with fixed x, y, width, and height and exactly 0° rotation.
- Represent a horizontal rule as a rectangle or line with exactly equal endpoint y values and 0° rotation.
- Do not use CSS skew, border triangles, rotated one-pixel lines, or freeform wedges for structural bars.
- If HTML uses a border as a visual shortcut, map that border to a separate native rectangle in PowerPoint rather than converting the enclosing shape outline.
- Keep x, y, width, and height untransformed in the shared specification; avoid nested transforms for elements that must remain orthogonal.

## Asset rules

- Keep images at sufficient resolution for their displayed size.
- Preserve aspect ratios unless the approved design deliberately crops the asset.
- Use SVG for simple icons and logos when available.
- In the HTML, embed small SVG and image assets or package them so the document works offline.
- In the PPTX, keep each asset as a distinct object rather than baking it into a slide screenshot.
- Keep labels, arrows, quantitative callouts, legends, and sources outside generated raster art so those elements remain editable.
- Treat generated technical illustrations as explanatory artwork, not factual evidence, and label them as schematic when appropriate.

## CSS restrictions

Avoid features that do not map reliably to PowerPoint:

- responsive reflow;
- animations and transitions;
- backdrop filters, blend modes, and complex filters;
- text in pseudo-elements;
- complex masks and clip paths for evidence-bearing content;
- layout that depends on external scripts or network calls;
- external web fonts that are not embedded and licensed.

Use flat fills, borders, restrained shadows, simple rotations, and explicit geometry.

## Tables and charts

Keep table data in structured cells. Use native PPT tables when row and column editing matters. Use grouped cell shapes when exact visual matching matters more than table operations, but keep every cell's text editable.

Keep chart data in a structured dataset. Create a native PPT chart when the chart type is supported. If a specialized scientific plot must remain an image, keep its title, legend, callouts, and source text editable whenever practical, and disclose the non-editable plot.

## Validation

Render both outputs at the same aspect ratio and compare slide by slide. Check:

- identical content and slide order;
- text wrapping and font substitution;
- alignment, padding, and object bounds;
- arrow paths and endpoint placement;
- image crops and aspect ratios;
- image existence, source parity, resolution, and successful offline loading;
- table geometry and chart values;
- 0° rotation and strict vertical or horizontal alignment of structural rules and bars;
- source notes and page numbers;
- editability of every required element.

Do not use PDF-to-PPT conversion as the primary route. Do not treat a successful file export as visual validation.
