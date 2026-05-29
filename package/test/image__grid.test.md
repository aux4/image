# image grid

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
rm -f gridded-*.png
```

## with default settings

### should overlay a grid on the image

```execute
aux4 image grid test-input.ppm --output gridded-default.png
```

```expect
Grid overlay on test-input.ppm (step: 50px, labels: 100px) -> gridded-default.png
```

## with custom step

### should respect a custom grid step

```execute
aux4 image grid test-input.ppm --output gridded-step.png --step 2 --labelStep 2
```

```expect
Grid overlay on test-input.ppm (step: 2px, labels: 2px) -> gridded-step.png
```
