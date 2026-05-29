# image resize

```file:test-input.ppm
P3
4 3
255
255 0 0  255 0 0  255 0 0  255 0 0
0 255 0  0 255 0  0 255 0  0 255 0
0 0 255  0 0 255  0 0 255  0 0 255
```

```afterAll
rm -f resized-*.ppm
```

## with pixel dimensions

### should resize to specified dimensions

```execute
aux4 image resize test-input.ppm --size 2x2 --output resized-pixels.ppm
```

```expect
Resized test-input.ppm to 2x2 -> resized-pixels.ppm
```

## with percentage

### should resize by percentage

```execute
aux4 image resize test-input.ppm --size 50% --output resized-percent.ppm
```

```expect
Resized test-input.ppm to 50% -> resized-percent.ppm
```
