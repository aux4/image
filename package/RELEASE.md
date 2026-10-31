# Release Notes

## 1.1.0

- **Feature:** `image resize` gained `--autoOrient` (rotate/flip the image upright per its EXIF
  orientation tag before resizing — cameras and phones commonly store real orientation as metadata
  instead of rotating the pixels) and `--strip` (remove EXIF/ICC/other metadata), both `false` by
  default so existing callers are unaffected. Both run in the same `magick` invocation as the resize
  itself — no extra process per image. Also documented (no code change needed — ImageMagick already
  honors it) that `--size` accepts a trailing `>` (e.g. `1568x1568>`) to only shrink an image larger
  than the target, never upscaling a smaller one, and that `--output`'s own file extension converts
  format in the same pass (so a `.heic`/`.webp`/... input into a `.jpg`/`.png` output also converts
  it).
