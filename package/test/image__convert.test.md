# image convert

```file:test-input.ppm
P3
2 2
255
255 0 0  0 255 0
0 0 255  255 255 0
```

```afterAll
rm -f test-input.png converted-output.png
```

## with default output name

### should convert using input name with new extension

```execute
aux4 image convert test-input.ppm --format png
```

```expect
Converted test-input.ppm -> test-input.png
```

## with explicit output

### should convert to specified output path

```execute
aux4 image convert test-input.ppm --format png --output converted-output.png
```

```expect
Converted test-input.ppm -> converted-output.png
```
