# image compare

```file:test-a.ppm
P3
2 2
255
255 0 0  0 255 0
0 0 255  255 255 0
```

```file:test-b.ppm
P3
2 2
255
0 0 255  0 255 0
255 0 0  0 255 255
```

```afterAll
rm -f diff-*.png
```

## with default settings

### should compare two images

```execute
aux4 image compare test-a.ppm --input2 test-b.ppm --output diff-default.png
```

```expect:partial
Compared test-a.ppm and test-b.ppm (AE) -> diff-default.png
```

## with custom metric

### should compare with RMSE metric

```execute
aux4 image compare test-a.ppm --input2 test-b.ppm --output diff-rmse.png --metric RMSE
```

```expect:partial
Compared test-a.ppm and test-b.ppm (RMSE) -> diff-rmse.png
```
