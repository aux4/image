#### Description

The `resize` command changes the dimensions of an image. It supports absolute pixel dimensions (e.g., `800x600`), width-only or height-only constraints (e.g., `800x` or `x600`), and percentage scaling (e.g., `50%`).

ImageMagick preserves the aspect ratio by default when only one dimension is specified. To force exact dimensions ignoring aspect ratio, append `!` to the size (e.g., `800x600!`). To only shrink an image larger than the target, and leave a smaller one untouched (never upscale), append `>` instead (e.g., `1568x1568>`).

`--output`'s own file extension drives the output format, so resizing a `.heic`/`.webp`/`.tiff`/... input into a `.jpg`/`.png`/... output converts it in the same pass — no separate `image convert` call needed.

- **`--autoOrient`** (default `false`) — rotate/flip the image upright according to its EXIF orientation tag before resizing. Cameras and phones commonly store a photo's real orientation as metadata instead of rotating the pixels themselves; without this, a resized photo can come out sideways or upside down.
- **`--strip`** (default `false`) — remove EXIF/ICC/other metadata from the output, in the same pass (equivalent to a following `image strip`, without the extra `magick` invocation).

#### Usage

```bash
aux4 image resize <input> --size <size> [--autoOrient true|false] [--strip true|false] --output <file>
```

--size        Target size (e.g., 800x600, 800x, x600, 50%, 800x600!, 1568x1568>)
--output      Output file path (extension drives format conversion)
--autoOrient  Rotate/flip upright per EXIF orientation before resizing (default: `false`)
--strip       Remove EXIF/ICC/other metadata from the output (default: `false`)

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

Prepare a phone photo for a vision API in one pass — fix its orientation, cap it at 1568px without
upscaling smaller photos, strip metadata, and convert HEIC to JPEG, all in a single `magick` call:

```bash
aux4 image resize IMG_1234.heic --size "1568x1568>" --autoOrient true --strip true --output prepared.jpg
```

```text
Resized IMG_1234.heic to 1568x1568> -> prepared.jpg
```
