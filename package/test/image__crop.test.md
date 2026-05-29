# image crop

```file:test-input.ppm
P3
4 4
255
255 0 0  0 255 0  0 0 255  255 255 0
128 0 0  0 128 0  0 0 128  128 128 0
64 0 0  0 64 0  0 0 64  64 64 0
32 0 0  0 32 0  0 0 32  32 32 0
```

```afterAll
rm -f cropped-*.ppm
```

## with geometry

### should crop a region from the image

```execute
aux4 image crop test-input.ppm --geometry 2x2+1+1 --output cropped-region.ppm
```

```expect
Cropped test-input.ppm (2x2+1+1) -> cropped-region.ppm
```

## with top-left crop

### should crop from the origin

```execute
aux4 image crop test-input.ppm --geometry 3x3+0+0 --output cropped-origin.ppm
```

```expect
Cropped test-input.ppm (3x3+0+0) -> cropped-origin.ppm
```
