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
rm -f resized-*.ppm resized-*.png
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

## never-upscale geometry (>)

### should leave a smaller-than-target image untouched when the size ends with >

```execute
aux4 image resize test-input.ppm --size "100x100>" --output resized-noupscale.ppm
magick identify -format "%wx%h" resized-noupscale.ppm
```

```expect:partial
Resized test-input.ppm to 100x100> -> resized-noupscale.ppm
4x3
```

## --autoOrient and --strip

### should accept both flags without error, resizing in one pass

```execute
aux4 image resize test-input.ppm --size 2x2 --autoOrient true --strip true --output resized-oriented-stripped.ppm
magick identify -format "%wx%h" resized-oriented-stripped.ppm
```

```expect:partial
Resized test-input.ppm to 2x2 -> resized-oriented-stripped.ppm
2x2
```

### the output file's own extension converts format in the same pass

```execute
aux4 image resize test-input.ppm --size 2x2 --output resized-converted.png
file resized-converted.png
```

```expect:partial
Resized test-input.ppm to 2x2 -> resized-converted.png
*PNG image data*
```
