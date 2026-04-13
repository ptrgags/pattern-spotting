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

## As Whole and Half Steps

Let's look at the modes in terms of whole steps
(`W = 2` semitones) and half steps (`H = 1` semitones)
between adjacent notes (looping around at the end).
This will strip away the tonic note, allowing us
to isolate the structure of the mode

```
C D E F G A B C -> W W H W W W H
```

Then we get the following pattern:

```
W W H W W W H    Ionian
W H W W W H W    Dorian
H W W W H W W    Phrygian    
W W W H W W H    Lydian
W W H W W H W    Mixolydian
W H W W H W W    Aeolian
H W W H W W W    Locrian
```

TODO: this is an example of applying a functor, though I need to work out the details.
- pitches -> cyclic deltas in semitones
- (tonic, mode) -> mode
- label_mode(half steps) -> mode
- need to check the functor laws

## As Scale Degrees

There's more structure here, but it's a bit hidden,
and will take a couple steps to get there. First,
let's count up semitones from the tonic for each
mode:

```
W W H W W W H  -> 0 2 4 5 7 9 11    Ionian
W H W W W H W  -> 0 2 3 5 7 9 10    Dorian
H W W W H W W  -> 0 1 3 5 7 8 10    Phrygian    
W W W H W W H  -> 0 2 4 6 7 9 11    Lydian
W W H W W H W  -> 0 2 4 5 7 9 10    Mixolydian
W H W W H W W  -> 0 2 3 5 7 8 10    Aeolian
H W W H W W W  -> 0 1 3 5 6 8 10    Locrian
```

Looking at this new table, the rows look mostly similar to each other, with a semitone difference in a
couple places. This becomes more evident if we switch
from semitones to scale degrees with sharps or flats
added (relative to Ionian). This is done in two parts:

- Compare the semitone value to the corresponding entry in the Ionian row. 
    - If the pitch is higher than the Ionian one, add a sharp (`#`) 
    - If the pitch is the same, don't add anything.
    - If the pitch is lower than the Ionian one, add
    a flat (`b`)
- The column number, starting with 1

<details>
<summary>Worked example: Mixolydian Mode</summary>

Let's juxtapose the Ionian and Mixolydian modes
to see the pattern

```
0 2 4 5 7 9 11 Ionian
0 2 4 5 7 9 10 Mixolydian
             b (sharps and flats)
1 2 3 4 5 6  7 (column numbers)
=
1 2 3 4 5 6 b7 Mixolydian scale degrees
```

The first 6 scale degrees are identical to those
in Ionian, so we have `1 2 3 4 5 6`.

However, the seventh is one semitone less (10 instead of 11), so this is a flat 7, i.e. `b7`.

All together, we get `1 2 3 4 5 6 b7`.
</details>

Applying this to all the rows, we get the scale
degrees for each mode:

```
0 2 4 5 7 9 11 -> 1  2  3  4  5  6  7    Ionian
0 2 3 5 7 9 10 -> 1  2 b3  4  5  6 b7    Dorian
0 1 3 5 7 8 10 -> 1 b2 b3  4  5 b6 b7    Phrygian    
0 2 4 6 7 9 11 -> 1  2  3 #4  5  6  7    Lydian
0 2 4 5 7 9 10 -> 1  2  3  4  5  6 b7    Mixolydian
0 2 3 5 7 8 10 -> 1  2 b3  4  5 b6 b7    Aeolian
0 1 3 5 6 8 10 -> 1 b2 b3  4 b5 b6 b7    Locrian
```

## Modes Ordered by Flats

The table at the end of the previous section looks a bit scrambled... what if we sorted by number of flats?
(using negative numbers for sharps)

```
-1    1  2  3 #4  5  6  7    Lydian
 0    1  2  3  4  5  6  7    Ionian
 1    1  2  3  4  5  6 b7    Mixolydian
 2    1  2 b3  4  5  6 b7    Dorian
 3    1  2 b3  4  5 b6 b7    Aeolian
 4    1 b2 b3  4  5 b6 b7    Phrygian
 5    1 b2 b3  4 b5 b6 b7    Locrian
```

That looks a lot cleaner! What patterns can we find here?

- This ordering explains hints at why we perceive some modes as "darker" than others. Our ears are so used to hearing the major scale (Ionian), so adding flats subverts our expectaions. Flats lower the pitch of some notes, so the more notes that are flatted, the stronger the effect. Similarly, the `#4` in the Lydian mode makes it a bit brighter than the major scale!
- As we go through the modes in this order, we always add one flat. However, which note gets a flat depends on the row.

Which scale degree gets flatted?

- First we flat the 4th (from `#4 -> 4`)
- Then we flat the 7th (from `7 -> b7`)
- The whole pattern is `4 -> 7 -> 3 -> 6 -> 2 -> 5`
- If we go back to letter names, we get `F B E A D G`. This is just a partial [Circle of Fourths](./uniform-scale.md)!

To summarize, to go to the next mode in the table,
take the most recently flatted note, move up a fourth and flat that note.

## Extending the Pattern

We already know that there are only 7 modes (as there are only 7 cyclic permutations of the notes `C D E F G A B`). However, the pattern from the previous section seems incomplete. The Circle of Fourths traverses all 12 pitch classes... How do we reconcile the two observations?

Let's see what happens if we take the pattern one step further. Let's start at Locrian and add one more flat.

Locrian was reached by adding a `b5`. One fourth up from `5` is... `1`. This gives the pattern:

```
b1 b2 b3 4 b5 b6 b7
```

Uh oh, we flatted the tonic! Now we can't quite compare it to the other mode since those start on a `1`. However, we can raise every scale degree by one to be more comparable. Let's see what we get:

```
b1 b2 b3  4 b5 b6 b7   ??? Mystery Mode
 1  2  3 #4  5  6  7   Lydian Mode
```

We seem to have looped back to the top of the table, now we have a Lydian mode! More specifically, the
Lydian mode for a tonic a half step lower.

This means we can extend the bottom of the table:

```
Table:
tonic (semitones from original)    Mode

??? (yet to be explored)
---
  1 Lydian
  1 Ionian
  1 Mixolydian
  1 Dorian
  1 Aeolian
  1 Phrygian
  1 Locrian
---
 b1 Lydian
 b1 Ionian
 b1 Mixolydian
 b1 Dorian
 b1 Aeolian
 b1 Phrygian
 b1 Locrian
---
bb1 Lydian
bb1 Ionian
... and so on with bbb1, bbbb1, etc.
```

What about the top end of the table? From inspection, it looks like the pattern wants to be:

```
... and so on
##1 Aeolian
##1 Lydian
---
 #1 Lydian
 ...
 #1 Aeolian 
 #1 Locrian
---
  1 Lydian
  1 Ionian
  ...
```

<details>
<summary>Two Proof sketches</summary>

- Apply the same process but in the other direction
    - Start at 1 _Lydian_
    - The last _sharp_ we applied was on the 4th
    - Go _down_ a fourth to `1` and flat that note.
    - The pattern is `#1 2 3 #4 5 6 7` 
    - Uh oh, we _sharped_ the tonic
    - So let's _flat_ everything to see the mode
    - `1 b2 b3 4 b5 b6 b7` -- that's Locrian mode
    - So the mode just above the table is `#1 Locrian`, as we predicted. 🪦
- OR continue descending until the table loops!
    - Since there are only 12 pitch classes, flatting the tonic 12 times will return to the start ($12 \equiv 0 \mod 12$)
    - So that means we looped around to the top of
    the table.
    - Furthermore, flatting the tonic 11 times is the same as sharping once. ($11 \equiv -1 \mod 12$)
    - So the row just above the table will be the _last_ mode, a half step _higher_.
    - i.e. `#1 Locrian`, as we predicted. 🪦
</details>

## The 84 Modes

TODO: I want to make a demo of this in `p5-sketchbook`; that will take some time. For now, picture a big circle with 84 tick marks. 12 major tick marks for the 12 tonic notes. In between each are 6 minor tick marks for the various modes.

There are 12 possible tonic notes, and 7 possible
modes. So `12 * 7 = 84` possible modes.