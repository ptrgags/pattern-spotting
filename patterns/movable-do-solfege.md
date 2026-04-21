# Moveable Do Solfege

Table based on ["Moveable Do Solfege Explained"](https://music-theory-practice.com/guides/moveable-do-solfege-explained) from `music-theory-practice.com`

| Semitones from tonic | Scale degree | Solfege | Comments |
|----|----|-----|---|
| 0  |  1 | Do  |
| 1  | #1 | Di  | Same pitch as Ra, but in contexts where we raise the 1 instead of lowering the 2 |
| 1  | b2 | Ra  | Re is the natural pitch, so Ra is used instead |
| 2  |  2 | Re  |
| 3  | #2 | Ri  |
| 3  | b3 | Me  |
| 4  |  3 | Mi  |
| 5  |  4 | Fa  |
| 6  | #4 | Fi  |
| 6  | b5 | Se  |
| 7  |  5 | Sol | Sometimes abbreviated as So. I prefer So since it's 2 letters like the other syllables. |
| 8  | #5 | Si  |
| 8  | b6 | Le  |
| 9  |  6 | La  |
| 10 | #6 | Li  |
| 10 | b7 | Te  |
| 11 |  7 | Ti  |
| 12 |  8 | Do  | We repeat at the octave |

These syllables are based on scale degrees, not specific pitches. For example, `Do Re Me Fa` would be `C D E F` in C Major, but `F G A Bb` in F Major.

## Chromatic Scale in Solfege

As an example, let's go up and down the [chromatic scale](./uniform-scale.html). Going upwards, we use sharps, going downwards,
we use flats. Here's the corresponding solfege:

```
Up the Scale:
 1 #1  2 #2  3  4 #4  5 #5  6 #6  7 8
Do Di Re Ri Mi Fa Fi So Si La Li Ti Do

Down the Scale:
 8  7 b7  6 b6  5 b5  4  3 b3  2 b2  1
Do Ti Te La Le So Se Fa Mi Me Re Ra Do
```

SOUND: A sound clip of the chromatic scale being sung in solfege

## More Details

🚧TODO: More details. Outline for now

- The basic pattern is `Do Re Mi Fa So(l) La Ti Do` for a major scale, the other syllables were added later for sharps and flats.
- To add a sharp, change the vowel to `i`
- To add a flat, usually you change the vowel to `e`
    - Exception: `Re` already uses `e` so it becomes `Ra` instead
- Scale degrees and solfege syllables are isomorphic (there's a one-to-one correspondence between them)
    - this mapping has `(add a sharp, change vowel to i)`-symmetry
    - This mapping _almost_ has `(add a flat, change vowel to e)` symmetry.
    - It would be interesting to create a different set of syllables with more symmetry
- The mapping from scale degrees to semitones is onto, but not one-to-one
    - Inverse is a multi-valued function
    - In practice you need more context to determine how to determine which enharmonic equivalent to use.

