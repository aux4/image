#### Description

The `watermark` command overlays text onto an image. It supports configurable position (gravity), text color, and font size. This is useful for applying copyright notices, branding, or labels to images.

Supported gravity positions:
- **NorthWest**, **North**, **NorthEast**
- **West**, **Center**, **East**
- **SouthWest**, **South**, **SouthEast**

The text is rendered with a 10-pixel offset from the edge to avoid clipping.

#### Usage

```bash
aux4 image watermark <input> --text <text> [--gravity <position>] [--color <color>] [--fontSize <size>] [--font <font>] --output <file>
```

--text      Watermark text
--gravity   Watermark position (default: SouthEast)
--color     Text color name or hex code (default: white)
--fontSize  Font size in points (default: 36)
--font      Font name or path to a font file (optional, uses system default)
--output    Output file path

#### Example

```bash
aux4 image watermark photo.jpg --text "© 2025 MyBrand" --output photo-branded.jpg
```

```text
Watermarked photo.jpg -> photo-branded.jpg
```

```bash
aux4 image watermark photo.jpg --text "DRAFT" --gravity Center --color red --fontSize 72 --output photo-draft.jpg
```

```text
Watermarked photo.jpg -> photo-draft.jpg
```
