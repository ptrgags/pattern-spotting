# Diatonic Modes

The 7 modes of the [Diatonic Scale](./diatonic-scale.md) are cyclic
permutations of the C major scale (aka Ionian mode):

```
C D E F G A B    C Ionian (major scale)
D E F G A B C    D Dorian
E F G A B C D    E Phrygian
F G A B C D E    F Lydian
G A B C D E F    G Mixolydian
A B C D E F G    A Aeolian (natural minor scale)
B C D E F G A    B Locrian
```

The above diagram is a mapping from 7 pitches to a label consisting of
a tonic note (the first note of the scale) and one of the 7 mode names

```
label_mode :: PitchClass[7] -> (PitchClass, {Io, Do, Ph, Ly, Mi, Ae, Lo})
```

Then `label_mode` has the following permutation [symmetry](./symmetry.md):

```
// Cycle the list of pitches one place to the left
let cycle_pitch(pitches) = permutation(C D E F G A B) * pitches

// The tonic note advances to the next scale degree,
// meanwhile the label advances to the next one in the list.
let cycle_mode(tonic, mode) = (
    cycle_pitch(tonic), 
    permutation(Io Do Ph Ly Mi Ae Lo) * mode
)

label_mode * cycle_pitch = cycle_mode * label_mode
```

<details>
<summary>Concrete Example</summary>

Starting with `pitches = F G A B C D E`

The left hand side says to do the following:

```
cycle_pitches(pitches) = G A B C D E F
label_mode(G A B C D E) = (G, Mixolydian)
```

The right hand side says to do the following:

```
label_mode(pitches) = (F, Lydian)
cycle_mode(F, Lydian) = (G, Mixolydian)
```

Both resulted in the same mode of G Mixolydian.
</details>