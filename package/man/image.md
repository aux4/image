#### Description

The `image` command provides a suite of image manipulation tools powered by ImageMagick. It supports resizing, format conversion, compression, metadata inspection, watermarking, metadata stripping, thumbnail generation, and image comparison.

Requires ImageMagick v7+ (`magick` command) to be installed.

#### Usage

```bash
aux4 image <command>
```

Available commands:

- **resize** — Resize an image by dimensions or percentage
- **convert** — Convert an image to a different format
- **compress** — Compress an image by adjusting quality
- **info** — Display image metadata and properties
- **watermark** — Apply a text watermark to an image
- **strip** — Remove EXIF and metadata from an image
- **thumbnail** — Generate a thumbnail with smart cropping
- **crop** — Crop a rectangular region from an image
- **compare** — Compare two images and highlight differences
