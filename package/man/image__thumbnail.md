#### Description

The `thumbnail` command generates a thumbnail from an image using smart cropping. Unlike simple resize, it crops to fill the exact target dimensions while preserving the most important part of the image (center gravity).

The process:
1. Resizes the image so the smallest dimension matches the target size
2. Crops from the center to the exact target dimensions

This ensures thumbnails are always the exact requested size with no letterboxing or distortion.

#### Usage

```bash
aux4 image thumbnail <input> [--size <WxH>] --output <file>
```

--size    Thumbnail size (default: 150x150)
--output  Output file path

#### Example

```bash
aux4 image thumbnail photo.jpg --output photo-thumb.jpg
```

```text
Thumbnail photo.jpg (150x150) -> photo-thumb.jpg
```

```bash
aux4 image thumbnail photo.jpg --size 300x200 --output photo-thumb-lg.jpg
```

```text
Thumbnail photo.jpg (300x200) -> photo-thumb-lg.jpg
```
