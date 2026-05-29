#### Description

The `compare` command highlights the visual differences between two images and produces a diff output image. Pixels that differ are marked in red, while unchanged areas remain as-is.

Both input images must have the same dimensions for comparison. The command outputs the difference metric value, which quantifies how different the images are.

Supported metrics:
- **AE** — Absolute Error (number of different pixels)
- **RMSE** — Root Mean Squared Error
- **PSNR** — Peak Signal to Noise Ratio
- **SSIM** — Structural Similarity Index
- **MAE** — Mean Absolute Error

#### Usage

```bash
aux4 image compare <input> --input2 <file> [--output <file>] [--metric <metric>]
```

--input2  Second image file to compare against
--output  Diff output file path (default: diff.png)
--metric  Comparison metric (default: AE)

#### Example

```bash
aux4 image compare original.png --input2 modified.png
```

```text
Compared original.png and modified.png (AE) -> diff.png
```

```bash
aux4 image compare v1.jpg --input2 v2.jpg --output changes.png --metric SSIM
```

```text
Compared v1.jpg and v2.jpg (SSIM) -> changes.png
```
