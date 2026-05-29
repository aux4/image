#### Description

The `resize` command changes the dimensions of an image. It supports absolute pixel dimensions (e.g., `800x600`), width-only or height-only constraints (e.g., `800x` or `x600`), and percentage scaling (e.g., `50%`).

ImageMagick preserves the aspect ratio by default when only one dimension is specified. To force exact dimensions ignoring aspect ratio, append `!` to the size (e.g., `800x600!`).

#### Usage

```bash
aux4 image resize <input> --size <size> --output <file>
```

--size    Target size (e.g., 800x600, 800x, x600, 50%, 800x600!)
--output  Output file path

#### Example

```bash
aux4 image resize photo.jpg --size 800x600 --output photo-resized.jpg
```

```text
Resized photo.jpg to 800x600 -> photo-resized.jpg
```

Resize to 50% of original:

```bash
aux4 image resize photo.jpg --size 50% --output photo-half.jpg
```

```text
Resized photo.jpg to 50% -> photo-half.jpg
```
