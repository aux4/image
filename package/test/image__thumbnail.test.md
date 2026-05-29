# image thumbnail

```file:test-input.ppm
P3
4 3
255
255 0 0  255 0 0  0 255 0  0 255 0
255 0 0  255 0 0  0 255 0  0 255 0
0 0 255  0 0 255  255 255 0  255 255 0
```

```afterAll
rm -f thumb-*.png
```

## with default size

### should generate thumbnail

```execute
aux4 image thumbnail test-input.ppm --output thumb-default.png
```

```expect
Thumbnail test-input.ppm (150x150) -> thumb-default.png
```

## with custom size

### should generate thumbnail with custom dimensions

```execute
aux4 image thumbnail test-input.ppm --size 2x2 --output thumb-custom.png
```

```expect
Thumbnail test-input.ppm (2x2) -> thumb-custom.png
```
