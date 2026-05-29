#### Description

The `compress` command reduces the file size of an image by adjusting the quality level and stripping metadata. The quality parameter controls the compression ratio — lower values produce smaller files with more visual loss.

Typical quality ranges:
- **90-100** — Near-lossless, minimal size reduction
- **70-85** — Good balance of quality and size
- **50-70** — Noticeable quality loss, significant size reduction
- **Below 50** — Heavy compression, visible artifacts

#### Usage

```bash
aux4 image compress <input> [--quality <1-100>] --output <file>
```

--quality  Quality level from 1 to 100 (default: 80)
--output   Output file path

#### Example

```bash
aux4 image compress photo.jpg --quality 75 --output photo-compressed.jpg
```

```text
Compressed photo.jpg (quality: 75) -> photo-compressed.jpg
```
