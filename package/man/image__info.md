#### Description

The `info` command displays metadata and properties of an image file. By default, it shows a summary line with format, dimensions, color depth, and file size. Use `--verbose true` for detailed metadata including color space, compression, EXIF data, and image statistics.

#### Usage

```bash
aux4 image info <input> [--verbose <true|false>]
```

--verbose  Show detailed metadata (default: false)

#### Example

```bash
aux4 image info photo.jpg
```

```text
photo.jpg JPEG 4032x3024 4032x3024+0+0 8-bit sRGB 3.2MB 0.000u 0:00.000
```

```bash
aux4 image info photo.jpg --verbose true
```

```text
Image:
  Filename: photo.jpg
  Format: JPEG (Joint Photographic Experts Group JFIF format)
  Geometry: 4032x3024+0+0
  Resolution: 72x72
  ...
```
