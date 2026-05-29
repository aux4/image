#### Description

The `crop` command extracts a rectangular region from an image. The region is specified using ImageMagick geometry format: `WxH+X+Y`, where `W` and `H` are the width and height of the crop area, and `X` and `Y` are the offset from the top-left corner.

The `+repage` flag is applied automatically to reset the virtual canvas, ensuring the output image has clean dimensions matching the cropped region.

Geometry examples:
- **300x200+50+100** — crop a 300x200 region starting at position (50, 100)
- **500x500+0+0** — crop the top-left 500x500 pixels
- **200x200+100+0** — crop 200x200 starting 100 pixels from the left edge

#### Usage

```bash
aux4 image crop <input> --geometry <WxH+X+Y> --output <file>
```

--geometry  Crop region in WxH+X+Y format
--output    Output file path

#### Example

```bash
aux4 image crop photo.jpg --geometry 300x200+50+100 --output photo-cropped.jpg
```

```text
Cropped photo.jpg (300x200+50+100) -> photo-cropped.jpg
```
