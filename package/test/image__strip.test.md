# image strip

```file:test-input.ppm
P3
2 2
255
128 128 128  128 128 128
128 128 128  128 128 128
```

```afterAll
rm -f stripped-output.png
```

## with output file

### should strip metadata to new file

```execute
aux4 image strip test-input.ppm --output stripped-output.png
```

```expect
Stripped metadata from test-input.ppm -> stripped-output.png
```

## in place

### should strip metadata in place

```execute
aux4 image strip test-input.ppm
```

```expect
Stripped metadata from test-input.ppm
```
