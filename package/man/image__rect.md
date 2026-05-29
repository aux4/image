#### Description

The `rect` command draws one or more outlined rectangles on an image. It is useful for visual debugging, highlighting regions of interest, or annotating bounding boxes from vision model output.

Each rectangle is specified with ImageMagick geometry `WxH+X+Y` (width, height, top-left X, top-left Y). Multiple `--rect` flags can be passed to draw several rectangles in one call.

The original image is not modified — the result is written to the output path.

#### Usage

```bash
aux4 image rect <input> --rect <WxH+X+Y> [--rect <WxH+X+Y> ...] --output <file> [--color <color>] [--strokeWidth <px>]
```

--rect         Rectangle region as `WxH+X+Y` (repeatable)
--output       Output file path (required)
--color        Stroke color, any ImageMagick color (default: `red`)
--strokeWidth  Line thickness in pixels (default: `3`)

#### Example

Draw a single rectangle:

```bash
aux4 image rect photo.jpg --rect 200x100+50+30 --output annotated.jpg
```

```text
Drew rectangles on photo.jpg -> annotated.jpg
```

Draw multiple rectangles with custom style:

```bash
aux4 image rect photo.jpg --rect 200x100+50+30 --rect 150x80+300+200 --color blue --strokeWidth 5 --output annotated.jpg
```

```text
Drew rectangles on photo.jpg -> annotated.jpg
```
