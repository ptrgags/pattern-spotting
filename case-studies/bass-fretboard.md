# Case Study: Bass Fretboard

![Diagram of bass fretboard](figures/bass-fretboard-blank.png)

## Fretboard Structure

![Diagram illustrating grid steps as moving 1 fret down the string or across to the next string](figures/bass-fretboard-steps.png)

- A bass guitar typically has 4 strings that stretch down the length of the fretboard.
- There are roughly 20 frets (metal bars across the neck of the guitar) used to locate notes along the string.
    - Note: This diagram is not to scale. The frets are [spaced _logarithmically_](../patterns/log-fret-spacing.md) to produce the correct pitches.
    - The number of frets varies from bass to bass.
- Taken together, the frets and strings form a grid. Let's define a **grid step** as moving to the next fret or string, as pictured in the diagram above.
    - This is analagous to [City Blocks](./city-blocks.md) in that we treat the two directions on equal footing, even though physically these steps are not the same size.

## Pitches On The Fretboard

![Diagram of bass fretboard with pitches labeled in scientific pitch notation from E1 to G3 labeled. Notes from the C major scale are written in red, while the sharps are drawn in blue.](figures/bass-fretboard-pitches.png)

In standard tuning, a bass guitar's strings are tuned to `E1, A1, D2, G2`. As you move down the string, each fret increases the pitch by one semitone. The diagram above shows all the pitches for the first 12 frets of the fretboard.

There's a lot going on in the above diagram, so let's break down
the pitches into pitch classes and octaves:

![Fretboard with pitch classes labeled. This is the same as the previous diagram, but with the octave numbers removed](figures/bass-fretboard-pitch-classes.png)

If we erase the octave numbers, we get the pitch classes. Notice that the same letter appears in several spots on the fretboard.

![Fretboard with the octaves labeled. This is the same as the first pitch diagram, but with the note letters remove](figures/bass-fretboard-octaves.png)

If instead we erase the letters, we get the octave numbers.
Here, we get a diagonal [gradient](../patterns/gradient.md) from the low E string, increasing slowly both down the string and across the strings.

## Pitch Symmetries

Studying the diagrams from the previous diagram,
we can identify some [symmetries](../patterns/symmetry.md). First, let's look at the absolute pitches again:

![Diagram illustrating with arrows pointing out the relationships described below](figures/bass-fretboard-note-symmetries.png)

- When we move 5 frets down the string, then over to the next lowest string, the pitch is exactly the same.
- When we move 2 frets down the string, and 2 strings up, we get a pitch exactly one octave (a perfect eighth) higher.

If we define the functions:
- `pitch(fret, string)` - get the absolute pitch of a particular fret and string (as in the diagram)
- `translate(frets, strings)` - Move across the fretboard by the number of frets and strings specified
- `transpose(interval)` - Increase a pitch by a musical interval

Then `pitch()` has:

- `translate(5, -1)`-symmetry
- `(translate(2, 2), transpose(P8))`-symmetry

Next, let's do the same thing for the pitch class diagram:

![Pitch class diagram with arrows pointing out the symmetries described below](figures/bass-fretboard-pitch-class-symmetries.png)

- Again, moving 5 frets down the string and 1 string down produces an identical pitch class
- This time, moving 2 frets over and 2 strings up produces the _same_ value, as we are ignoring octaves.

So if `pitch_class(frets, strings)` is a function that returns the pitch class, then this function has the following symmetries:

- `translate(-5, 1)`-symmetry
- `translate(2, 2)`-symmetry

TODO: If you include octave, the symmetry is changed:




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

To make a scale on a fretboard, we need to make
a (somewhat irregular) box around 12 distinct pitches. There many ways to do this, so let's define some constraints:

- The box should use as few frets as possible. This helps to limit moving one's hand up and down the string
- Let's examine pitches within a single octave.

With these constraints, we get 5 possible scale boxes, each one shifting one fret down the string from the previous one. Since semitones are arranged in diagonal fashion, the box changes shape slightly.

![box shape 1. The root note is in the bottom right. This one extends across 4 strings](figures/bass-scale1.png)
![box shape 2. The leftmost column of notes are moved to the bottom right](figures/bass-scale2.png)
![box shape 3. This one is the most balanced around the root note](figures/bass-scale3.png)
![box shape 4](figures/bass-scale4.png)
![box shape 5. Now the root note is on the bottom left](figures/bass-scale5.png)

TODO: This is related to fundamental domains
TODO: If you ignore octave, the scale boxs fit together in a p1 wallpaper pattern

