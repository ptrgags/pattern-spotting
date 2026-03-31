# Case Study: Piano Keyboard

IMG: A couple octaves of a piano keyboard

## Patterns

IMG: diagram of the symmetries

- visual [symmetries](../patterns/symmetry.md) of the keyboard layout
    - `translate(12)` - Every time you move up the keyboard by 12 keys, the pattern of black and white keys looks the same.
    - `reflect(D)` - if you were to flip the keyboard backwards using a mirror placed on one of the D keys, you end up with the same pattern of black and white keys.
    Here, we're assuming that 
    - `reflect(G#)` - The same thing happens if you place the mirror at a G# on the keyboard.
- [Euclidean Rhythms](../patterns/euclidean-rhythms.md)
    - Euclidean rhythm `E(n, k)` puts $k$ objects into $n$ slots as evenly as possible.
    - Up to cyclic shift, the black keys within an octave match the pattern of `E(12, 5)`
    - The white keys then are the complimentary pattern `E(12, 7)`
- Musical Scales
    - If you play across the white keys, you get a [diatonic scale](../patterns/diatonic-scale.md).
    - If you play across the black keys, you get a [pentatonic scale](../patterns/pentatonic-scale.md)
    - If you move across the keyboard in fix-sized steps you get what I'll call [uniform scale](../patterns/uniform-scale.md) for lack of a better term

## Variations

- Isomorphic Keyboards
    - The piano keyboard layout is due to hundreds of years of history. Yet it's not the only way to arrange the 12 notes of the chromatic scale. [Isomorphic keyboards (wiki)](https://en.wikipedia.org/wiki/Isomorphic_keyboard) are layouts where musical intervals have the same shape anywhere on the keyboard.
    - [Rectangular Iso Keyboard](../patterns/rect-iso-piano.md) - The simplest thing is to make a 2D grid of pitches with a fixed step size in each direction 
        - [Bass Fretboards](./bass-fretboard.md) are one such example.
        - [Guitar Fretboards](./guitar-fretboard.md) _almost_ match this pattern.
    - [Hexagaonal Iso Keyboard](../patterns/hex-iso-piano.md) - If you put the notes on a hex grid with some slight modifications, you get an even