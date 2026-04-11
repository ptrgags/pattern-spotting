# Case Study: Bass Fretboard

![Diagram of bass fretboard](figures/bass-fretboard-blank.png)

Patterns

![Diagram of bass fretboard with note names listed. Notes from the C major scale are colored in red, sharps are colored in blue](figures/bass-fretboard-notes.png)

In standard tuning, a bass guitar's strings are tuned to E, A, D, and G from bottom to top. As you move down the string, each fret increases the pitch by one semitone. The diagram above labels these pitches. There are several patterns hiding here:

![bass fretboard with frets numbered with number of semitones from the open E string. Two arrows are drawn on top. One moves along a string, showing that each fret is +1 semitone. Another points across the strings, showing that each string is +5 semitones higher than the next lower string](figures/bass-fretboard-semitones.png)

- The structure of the fretboard is a [Rectangular Iso Keyboard](../patterns/rect-iso-piano.md). The above diagram replaces the note labels with semitones above the lowest note (E on the open E string) to illustrate this
    - As mentioned above, moving down the string results in increasing the pitch by 1 semitone, i.e. a minor second
    - E, A, D, G are each 5 semitones, i.e. a perfect fourth apart. So moving up one string increases the pitch by a perfect fourth
    - So this is a `(m2, P4)` isometric keyboard, but cropped to the number of strings and frets on the neck of the bass.

![The semitone diagram, but now there are many parallel stripes drawn diagonally across the fretboard. The thicker black stripes mark every octave above the lowest note. The many narrow blue lines mark the 12 semitones between octaves.](figures/bass-fretboard-stripes.png)

- Since we increase pitch in two different directions, there are several copies of most notes. Imagine 
    - Visually, this looks like a set of parallel [stripes](../patterns/stripes.md)
    - You could interepret this as a [plane wave](../patterns/plane-wave.md)
- If you gather up one fret from each pitch class, you can make a [chromatic scale](../patterns/uniform-scale.md). See [§ Scales on a Fretboard](#scales-on-a-fretboard) below for more details

## Scales on a Fretboard

TODO: Maybe this should be a separate case study

To make a scale on a fretboard, we need to make
a (somewhat irregular) box around 12 distinct pitches. There many ways to do this, so let's define some constraints:

- The box should use as few frets as possible. This helps to limit moving one's hand up and down the string
- Let's examine pitches within a single octave.

With these constraints, we get 5 possible scale boxes, each one shifting one fret down the string from the previous one. Since semitones are arranged in diagonal fashion, the box changes shape slightly.

![box shape 1. The root note is in the bottom right. This one extends across 4 strings](figures/bass-scale1.png) ❌TODO: this diagram is missing the 7 on the G string!!
![box shape 2. The leftmost column of notes are moved to the bottom right](figures/bass-scale2.png)
![box shape 3. This one is the most balanced around the root note](figures/bass-scale3.png)
![box shape 4](figures/bass-scale4.png)
![box shape 5. Now the root note is on the bottom left](figures/bass-scale5.png)

TODO: This is related to fundamental domains
TODO: If you ignore octave, the scale boxs fit together in a p1 wallpaper pattern

```
pitch_class T(-5, 1) = pitch_class
pitch_class T(2, 2) = pitch_class
```

TODO: If you include octave, the symmetry is changed:

```
semi T(-5, 1) = semi
semi T(2, 2) = T(P8) semi
```