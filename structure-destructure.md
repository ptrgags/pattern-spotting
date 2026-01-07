# Structure and Destructure

- destructure: take a value and break it down into parts
- structure: take the parts and combine them back into the whole
- i.e. "equal to the sum of its parts"

## Connection: Construction IRL

- Lego set: building from bricks, disassembling into bricks
    - interesting detail: there are steps to disassembly
    - curiosity: what is the structure of combining bricks? in theory union of bricks is fine, but in practice, a model falls apart if bricks are not physically connected'
- assembling/disassembling furniture, vehicles, anything really

## Connections: Music

- MIDI note number <-> octave, pitch class
    - observation: mathematically this is the same as 1D <-> 2D indices!
    - more generally you can think of dividing frequency range (semitones from a reference pitch) into octave, semitones, cents 
- decomposing audio signal
    - projection: compute FT at a specific frequency
    - constructor: compute inverse FT for full spectrum

## Connections: Art

- digital art: splitting an image file into layers, compositing them
    - this only works for project files (`.psd, .kra`, ...I forget the extension for GIMP... `.xcd`?). For flat raster formats, composition is lossy!
    - vector graphics are more easily split/merged
- Digital colors have multiple possible projections
        - sRGB <-> R, G, B components (bit twiddling or object-oriented color)
        - oklch <-> lightness, chroma, hue
        - color space <-> a, b, c in general
        - Using color space transformations, you can 
            - though transformations may not always be invertible...


## Connections: Programming

- `vec.x, vec.y, vec.z` are projections, `vector(x, y, z)` is a constructor
- Gamepad joystick axis to left/right signals: `left = max(x_axis, 0), right: min(x_axis, 0)` <-> `left + right`
- `(row = index // cols, row = index % cols)` and `rows * cols + index` when converting 1D to 2D grid indices
- bit twiddling to pack/unpack multiple fields from a single integer
    - constructor: `packed = BITWISE_OR(i, field[i] << shift[i])`
    - projections: `field[i] = (packed >> shift[i]) & mask[i]`
- object oriented programming: struct(a, b, c...) is a constructor, object.a, obj.b, obj.c getters are projections
    - note that you can also _modify_ individual fields    

## Connections: Math

- Category theory
    - categorical product is a tuple type
    - only defined up to isomorphism
    - the projection functions and the constructor (when inverses) are an isomorphism to the categorical product
`floor, fract <-> add` 
    - project from $\mathbb{R} \to \mathbb{Z} \times [0, 1]$
- real/imag part of a complex number, `a + bi` is the constructor
- `sign, abs`, `sign * abs`... kinda. Have to be nitpicky about the domain of these functions to handle zero correctly
- partitioning a set, unioning it back together
- Raster Tangles grammar rule
    - projection: Decompose pixels by sub-region address. Also decoration pixels
    - constructor: union of sub-regions and decoration



