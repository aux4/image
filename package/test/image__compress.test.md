# image compress

```file:test-input.ppm
P3
4 4
255
255 0 0  255 0 0  0 255 0  0 255 0
255 0 0  255 0 0  0 255 0  0 255 0
0 0 255  0 0 255  255 255 0  255 255 0
0 0 255  0 0 255  255 255 0  255 255 0
```

```afterAll
rm -f compressed-*.jpg
```

## with default quality

### should compress with default quality

```execute
aux4 image compress test-input.ppm --output compressed-default.jpg
```

```expect
Compressed test-input.ppm (quality: 80) -> compressed-default.jpg
```

## with custom quality

### should compress with specified quality

```execute
aux4 image compress test-input.ppm --quality 50 --output compressed-low.jpg
```

```expect
Compressed test-input.ppm (quality: 50) -> compressed-low.jpg
```
