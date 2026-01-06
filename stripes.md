# Stripes

## Outline

- Even stripes (same width on and off) are like a square wave
- Even stripes are like a steady rhythm with rests in between
    - kick drum pattern: `x.x.` (quarter notes)
    - snare drum pattern: `.x.x` (quarter notes)
    - High hat pattern: `x.x.x.x.x.x.x.x.` (16th notes)
- variation: non-uniform stripes
    - Like a pulse wave/PWM on a synth
    - connection: Pokemon cries chained multiple pulse widths together to make more waveforms
    - barcodes
- variation: many colors
- variation: warp the stripes into waves and other shapes
- in 3D: slabs with gaps in between
    - would be easy to visualize in Minecraft
- Animated version
    - The most obvious thing to do is adjust the phase
- Recipe: Axis-aligned stripes
    - texture: rectangle split half and half with two colors `x.`. Then repeat in both directions:
```
x.x.x.x.x.x.x.x. ...
x.x.x.x.x.x.x.x. ...
x.x.x.x.x.x.x.x. ...
x.x.x.x.x.x.x.x. ...
```
    - vector graphics: draw parallel lines or rectangles
        - `line(i * dx, 0, i * dx, height)`
        - if you want to get nitpicky, you need to choose the stroke width carefully for uniform stripes.
        - or `rect(2 * i * dx, 0, stripe_width, height)`
        - for the other stripes, use `(2 * i + 1) * dx` instead in rect recipe
    - shader: `square_wave(uv.x)`
    - knitting: rib stitch! as a chart:
```
-v-v-v-v-v-v-v-v
-v-v-v-v-v-v-v-v
-v-v-v-v-v-v-v-v
-v-v-v-v-v-v-v-v
```
    - though it's knitted (knit N, purl N) on row 0, 2, 4, ... and (purl N, knit N) on rows 1, 3, 5, ...
    - take range `[0, 1, ..., N] % 2` to get a digital square wave