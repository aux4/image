#### Description

The `grid` command overlays a labeled pixel coordinate grid on top of an image. It draws thin lines at regular intervals and prints numeric axis labels so the result can be fed to a vision LLM that needs to report bounding boxes in precise pixel coordinates. Vision models read grid labels far more reliably than they estimate raw pixel positions, so this command is useful when you want an LLM to return tight crop geometries (e.g. for downstream `aux4 image crop`).

The original image is not modified — the grid is baked into a new output file.

#### Usage

```bash
aux4 image grid --input <in.png> --output <out.png> [--step <px>] [--labelStep <px>] [--color <color>] [--fontSize <pt>]
```

--input      Input image file (required)
--output     Output file path (required)
--step       Grid line spacing in pixels (default: `50`)
--labelStep  Numeric label spacing in pixels (default: `100`)
--color      Grid and label color, any ImageMagick color (default: `red`)
--fontSize   Label font size in points (default: `12`)

#### Example

```bash
aux4 image grid --input page-02.png --output page-02-grid.png --step 50 --labelStep 100 --color "rgba(255,0,0,0.5)"
```

```text
Grid overlay on page-02.png (step: 50px, labels: 100px) -> page-02-grid.png
```
