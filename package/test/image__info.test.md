# image info

```file:test-input.ppm
P3
3 2
255
255 0 0  0 255 0  0 0 255
255 255 0  0 255 255  255 0 255
```

## with default output

### should show image summary

```execute
aux4 image info test-input.ppm
```

```expect:partial
test-input.ppm PPM 3x2 *?
```

## with verbose output

### should show detailed metadata

```execute
aux4 image info test-input.ppm --verbose true
```

```expect:partial
**Geometry: 3x2+0+0**
```
