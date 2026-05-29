# image mask

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
rm -f masked-*.png
```

## with default color

### should paint a white rectangle over the region

```execute
aux4 image mask test-input.ppm --output masked-default.png --geometry 2x2+1+1
```

```expect
Masked test-input.ppm (2x2+1+1, white) -> masked-default.png
```

## with explicit color

### should paint a black rectangle over the region

```execute
aux4 image mask test-input.ppm --output masked-black.png --geometry 2x2+0+0 --color black
```

```expect
Masked test-input.ppm (2x2+0+0, black) -> masked-black.png
```
