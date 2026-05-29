#### Description

The `strip` command removes all EXIF metadata from an image, including GPS coordinates, camera information, timestamps, and other embedded data. This is useful for privacy before sharing or uploading images.

If `--output` is not specified, the input file is modified in place. When `--output` is provided, the original file is preserved and a clean copy is written to the output path.

#### Usage

```bash
aux4 image strip <input> [--output <file>]
```

--output  Output file path (default: overwrite input in place)

#### Example

Strip metadata in place:

```bash
aux4 image strip photo.jpg
```

```text
Stripped metadata from photo.jpg
```

Strip metadata to a new file:

```bash
aux4 image strip photo.jpg --output photo-clean.jpg
```

```text
Stripped metadata from photo.jpg -> photo-clean.jpg
```
