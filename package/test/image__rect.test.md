# image rect

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
rm -f rect-*.png
```

## with single rectangle

### should draw a rectangle

```execute
aux4 image rect test-input.ppm --rect 2x2+1+1 --output rect-single.png
```

```expect
Drew rectangles on test-input.ppm -> rect-single.png
```

## with multiple rectangles

### should draw multiple rectangles

```execute
aux4 image rect test-input.ppm --rect 2x2+0+0 --rect 2x2+2+2 --output rect-multi.png
```

```expect
Drew rectangles on test-input.ppm -> rect-multi.png
```
