# aux4/image

Image manipulation toolkit powered by ImageMagick. Provides commands for resizing, format conversion, compression, metadata inspection, watermarking, metadata stripping, thumbnail generation, and image comparison.

## Installation

```bash
aux4 aux4 pkger install aux4/image
```

Requires ImageMagick v7+ to be installed. The package will attempt to install it automatically via your system package manager if not found.

## Quick Start

```bash
# Resize an image
aux4 image resize photo.jpg --size 800x600 --output photo-small.jpg

# Convert to WebP
aux4 image convert photo.jpg --format webp

# Generate a thumbnail
aux4 image thumbnail photo.jpg --size 150x150 --output thumb.jpg

# Get image info
aux4 image info photo.jpg
```

## Commands

### resize

Resize an image by pixel dimensions or percentage.

```bash
aux4 image resize <input> --size <size> --output <file>
```

Supports absolute dimensions (`800x600`), single-axis constraints (`800x`, `x600`), percentage (`50%`), and forced exact dimensions (`800x600!`).

```bash
aux4 image resize photo.jpg --size 800x600 --output photo-resized.jpg
```

```text
Resized photo.jpg to 800x600 -> photo-resized.jpg
```

### convert

Convert an image between formats (JPEG, PNG, WebP, TIFF, GIF, BMP).

```bash
aux4 image convert <input> --format <format> [--output <file>]
```

If `--output` is omitted, the output file uses the input name with the new extension.

```bash
aux4 image convert photo.jpg --format webp
```

```text
Converted photo.jpg to webp -> photo.webp
```

### compress

Reduce image file size by adjusting quality and stripping metadata.

```bash
aux4 image compress <input> [--quality <1-100>] --output <file>
```

```bash
aux4 image compress photo.jpg --quality 75 --output photo-compressed.jpg
```

```text
Compressed photo.jpg (quality: 75) -> photo-compressed.jpg
```

### info

Display image metadata and properties.

```bash
aux4 image info <input> [--verbose <true|false>]
```

Use `--verbose true` for detailed metadata including EXIF data, color space, and image statistics.

```bash
aux4 image info photo.jpg
```

```text
photo.jpg JPEG 4032x3024 4032x3024+0+0 8-bit sRGB 3.2MB 0.000u 0:00.000
```

### watermark

Apply a text watermark to an image.

```bash
aux4 image watermark <input> --text <text> [--gravity <position>] [--color <color>] [--fontSize <size>] [--font <font>] --output <file>
```

Supports 9 gravity positions (NorthWest, North, NorthEast, West, Center, East, SouthWest, South, SouthEast).

```bash
aux4 image watermark photo.jpg --text "© 2025 MyBrand" --output photo-branded.jpg
```

```text
Watermarked photo.jpg -> photo-branded.jpg
```

### strip

Remove EXIF and metadata from an image (GPS, camera info, timestamps).

```bash
aux4 image strip <input> [--output <file>]
```

Without `--output`, the input file is modified in place.

```bash
aux4 image strip photo.jpg --output photo-clean.jpg
```

```text
Stripped metadata from photo.jpg -> photo-clean.jpg
```

### thumbnail

Generate a thumbnail with smart center-cropping to exact dimensions.

```bash
aux4 image thumbnail <input> [--size <WxH>] --output <file>
```

Unlike resize, thumbnail fills the exact target dimensions by cropping from the center.

```bash
aux4 image thumbnail photo.jpg --size 300x200 --output thumb.jpg
```

```text
Thumbnail photo.jpg (300x200) -> thumb.jpg
```

### crop

Crop a rectangular region from an image.

```bash
aux4 image crop <input> --geometry <WxH+X+Y> --output <file>
```

Uses ImageMagick geometry format: width x height + X offset + Y offset from the top-left corner.

```bash
aux4 image crop photo.jpg --geometry 300x200+50+100 --output photo-cropped.jpg
```

```text
Cropped photo.jpg (300x200+50+100) -> photo-cropped.jpg
```

### grid

Overlay a labeled coordinate grid on an image. Useful for vision-LLM bounding-box prompts.

```bash
aux4 image grid <input> --output <file> [--step <px>] [--labelStep <px>] [--color <color>] [--fontSize <size>] [--font <path>]
```

```bash
aux4 image grid photo.jpg --step 50 --labelStep 100 --output photo-grid.jpg
```

```text
Grid overlay on photo.jpg (step: 50px, labels: 100px) -> photo-grid.jpg
```

### mask

Paint a solid-color rectangle over a region of an image. Useful for redacting content.

```bash
aux4 image mask <input> --output <file> --geometry <WxH+X+Y> [--color <color>]
```

```bash
aux4 image mask scan.png --geometry 80x90+20+30 --color white --output scan-redacted.png
```

```text
Masked scan.png (80x90+20+30, white) -> scan-redacted.png
```

### rect

Draw outlined rectangles on an image for visual debugging or annotation.

```bash
aux4 image rect <input> --rect <WxH+X+Y> [--rect ...] --output <file> [--color <color>] [--strokeWidth <px>]
```

Supports multiple `--rect` flags to draw several rectangles in one call.

```bash
aux4 image rect photo.jpg --rect 200x100+50+30 --rect 150x80+300+200 --color blue --output annotated.jpg
```

```text
Drew rectangles on photo.jpg -> annotated.jpg
```

### compare

Compare two images and produce a visual diff highlighting differences.

```bash
aux4 image compare <input> --input2 <file> [--output <file>] [--metric <metric>]
```

Supported metrics: AE, RMSE, PSNR, SSIM, MAE.

```bash
aux4 image compare original.png --input2 modified.png --metric SSIM
```

```text
Compared original.png and modified.png (SSIM) -> diff.png
```
