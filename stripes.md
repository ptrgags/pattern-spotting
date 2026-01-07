# Stripes

## Uniform Stripes

- stripes where the lines and gaps are the same width
- Connection: Digital Audio
    - Square waves
    - in digital audio, a square wave toggles between two values with the same amount of time on as time off
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
- knitting: rib stitch! (see chart below)
    - though it's knitted (knit N, purl N) on row 0, 2, 4, ... and (purl N, knit N) on rows 1, 3, 5, ...
    - take range `[0, 1, ..., N] % 2` to get a digital square wave
- Connection: Music
    - steady rhythms with rests
    - kick drum pattern: `x.x.` (quarter notes)
    - snare drum pattern: `.x.x` (quarter notes)
    - High hat pattern: `x.x.x.x.x.x.x.x.` (16th notes)
- Connection: Knitting
    - rib stitch
    - End result has columns of N knits (v) and N purls (-)
    - See charts below
- Connection: Higher dimensions
    - instead of stripes, slabs with gaps in between
    - recipe: Minecraft
    - recipe: raymarching stack of slabs
- IRL: Crosswalks
    - White stripes on the dark asphalt
    - usually uniform stripes, though not always required (see for example [PennDOT standards](https://gis.penndot.gov/BPR_PDF_FILES/Documents/LTAP/TechSheets/TS_193.pdf))

```
knitting chart examples
-v-v-v-v-v-v-v-v
-v-v-v-v-v-v-v-v
-v-v-v-v-v-v-v-v
-v-v-v-v-v-v-v-v

Row 0, 2, ... (knit 1, purl 1) * k
Row 1, 3, ... (purl 1, knit 1) * k

--vv--vv--vv--vv
--vv--vv--vv--vv
--vv--vv--vv--vv
--vv--vv--vv--vv

Row 0, 2, ... (knit 2, purl 2) * k
Row 1, 3, ... (purl 2, knit 2) * k

---vvv---vvv---vvv
---vvv---vvv---vvv
---vvv---vvv---vvv
---vvv---vvv---vvv

Row 0, 2, ... (knit 3, purl 3) * k
Row 1, 3, ... (purl 3, knit 3) * k
```

- Examples in my work
    - traditional art: stripes are a very common hatching pattern for filling regions when drawing in pen
    - `p5-sketchbook`: AnimatedTangle
    - plane waves in `symmetry-sketchbook`

## Oriented stripes

- stripes at an angle
- recipe: vector
    - see how I did this in p5-sketchbook
- recipe: shader
    - `dot(uv, wave_vector)` sets the direction normal to each plane
- 3D: oriented planes

## Thin stripes

- lego bricks
- white keys on a piano
- grid lines for one axis on graph paper
- pin stripes
- this is really just a special case of non-uniform stripes where 
- rhythms with no rests, but distinct note onsets
    - e.g. `xxxxxxxx` as 8 separate notes, not `x-------`
    which is one long note for 8 steps

## Non-uniform stripes

- stripes where the lines may be not the same thickness
- Connection: Digital Audio
    - if uniform stripes are a square wave, then non-uniform stripes are a pulse wave (non-uniform pulse width)
    - or even a chain of different pulse widths. See for example pokemon cries
- Connection: Music
    - if a steady rhythm was uniform stripes, then the non-uniform stripes would be any rhythm involving note
    onsets
    - nuance: 
- Connection: Piano keyboard
    - pattern of white and black keys when you look at
    - the top part of the keys `.X.X..X.X.X.`
- Connection: Barcodes
    - 1D barcodes 
- Connection: Digital signals
    - an sequence of binary is like a set of stripes
    - `0b101000010001` stripes

## Multi-color stripes

- Set of non-uniform stripes, but now each stripe has a color
- Connection: Music
    - using the rhythm analogy, adding color could be
    like adding velocity to a drum rhythm
    - or, a rhythm with pitches
    - or, a monophonic General MIDI drum kit pattern

## Animating stripes

- The most obvious thing to do is adjust the phase
- what about adjusting frequency?

## Other Variations

- warp stripes into waves and other patterns