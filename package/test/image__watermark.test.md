# image watermark

```file:test-input.ppm
P3
4 4
255
0 0 128  0 0 128  0 0 128  0 0 128
0 0 128  0 0 128  0 0 128  0 0 128
0 0 128  0 0 128  0 0 128  0 0 128
0 0 128  0 0 128  0 0 128  0 0 128
```

```afterAll
rm -f watermarked-*.png
```

## with default settings

### should apply watermark with defaults

```execute
aux4 image watermark test-input.ppm --text "Test" --output watermarked-default.png
```

```expect
Watermarked test-input.ppm -> watermarked-default.png
```

## with custom settings

### should apply watermark with custom gravity and color

```execute
aux4 image watermark test-input.ppm --text "DRAFT" --gravity Center --color red --fontSize 48 --output watermarked-custom.png
```

```expect
Watermarked test-input.ppm -> watermarked-custom.png
```
