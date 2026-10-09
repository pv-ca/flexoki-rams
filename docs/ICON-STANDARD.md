# Application icon standard

The Eden reference defines the rounded application-tile family. This is a project design contract, separate from the freedesktop icon-theme format.

For a transparent square canvas of side S:

- Visible plate side: T = round(S × 0.96).
- Plate offset: L = floor((S − T) / 2) on each axis.
- Measure the bounding box at alpha ≥ 128: [L, L, L + T, L + T].
- At 48 px, the plate is 46 × 46 px at [1, 1, 47, 47].
- Use consistent rounding when opposite margins differ by one pixel.

Preserve the proportions and identity of the internal symbol. Equal plate geometry does not prove equal perceived size; review visual weight and position beside the reference at actual display size.

Separate plate, highlight, subject and shadows in editable sources. Detailed approved raster artwork may retain a raster master; embedding PNG in SVG does not make the illustration fully vector.

This tile profile applies to plated application icons. Folder silhouettes, actions, status symbols, MIME types and emblems need their own profiles. Keep filled folders and their content previews; never replace large folders with a small symbolic outline merely to unify the theme.

Exports must preserve transparency, canvas margins, scale metadata and identical artwork for aliases. Validate native Qt lookup and the actual desktop surface after installation.
