# Normalized Values

🚧 Outline for now

## Unsigned Value

- A value from $[0, 1]$
- In synthesizers and other audio software, this is sometimes called a "unipolar" signal
- Examples:
    - Percentages as a decimal value
    - On the GPU, color values are represented as unsigned floating point values in the range $[0, 1]$ (and values outside this range are clamped to this range)
    - In 3D graphics, UV coordinates are usually a pair of unsigned float values that represent percentages across a texture
    - On a synthesizer, an envelope adjusts the volume (or other parameter) of a note over time. It does this by producing unsigned values interpreted as "percentage of max volume"

## Signed Value

- A value from $[-1, 1]$
- In synthesizers and other digital audio software, this is sometimes called "bipolar"
- Examples:
    - In digital audio, waves are often represented as siagned float values oscillating between 1 and -1
    - In 3D graphics, [clip space (external link)](https://learnopengl.com/Getting-started/Coordinate-Systems) coordinates are signed values[^1] that determine a volume of space that will visible on the screen.

[^1]: Well... at least in OpenGL all three coordinates are signed. See ["Coordinate Systems"](https://learnopengl.com/Getting-started/Coordinate-Systems) from Learn Open GL. In other graphics APIs like WebGPU, the z-coordinate is an *unsigned* depth coordinate.

## Converting between Signed and Unsigned

You can convert between the two kinds of
signals using the following pair of functions, which are inverses of each other:

```
to_unsigned(signed) = 0.5 + 0.5 * signed
to_signed(unsigned) = 2 * unsigned - 1 
```

## Decomposing Signed into sign and magnitude

- Deconstruct: `(sign, magnitude) = (sgn(x), abs(x))`
- Construct: `x = sign * magnitude`
- This is example of the [construct/deconstruct](./construct-deconstruct.html) pattern[^2]

[^2]: ...with some minor hair splitting over the domain and range due to zero having more than one represntation E.g. $(+1, 0) = (0, r) = (-1, 0)$.

## Normalizing Values

- If you have a value $x$ in a finite range $[0, N]$, then you can produce an unsigned value by computing $x / N$
- If you have a value in a finite range $[-N, N]$, you can produce a signed value by computing $x/N$