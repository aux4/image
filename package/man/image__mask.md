#### Description

The `mask` command paints a solid-color rectangle over a region of an image. It is useful for redacting unwanted content in-place — step numerals overlapping an illustration, page numbers, watermarks, private text, or any fixed-location artifact — without re-cropping the image.

The region is specified with ImageMagick geometry `WxH+X+Y` (width, height, top-left X, top-left Y) where the origin is the top-left corner. The fill color accepts any ImageMagick color string (`white`, `black`, `#ff0000`, `rgba(0,0,0,0.5)`, etc.).

The original image is not modified — the masked result is written to the output path.

#### Usage

```bash
aux4 image mask --input <in.png> --output <out.png> --geometry <WxH+X+Y> [--color <color>]
```

--input     Input image file (required)
--output    Output file path (required)
--geometry  Rectangle region as `WxH+X+Y` (required)
--color     Fill color, any ImageMagick color (default: `white`)

#### Example

```bash
aux4 image mask --input step-01.png --output step-01.png --geometry 80x90+20+30 --color white
```

```text
Masked step-01.png (80x90+20+30, white) -> step-01.png
```
