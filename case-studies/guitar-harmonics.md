---
layout: default
---
# Guitar Harmonics

🚧 Outline for now

## Fretting Note vs Harmonics

When you fret a note, you pinch the string against one of the frets. This means the part above the fret will not vibrate. The part below the fret vibrates. This is equivalent to playing an open string with a _shorter length_.

- Fretting a string: wave equation with constraints:
    - $f([0, x]) = 0$
    - $f(x) = 0$
    - $f(L) = 0$
    - Equivalent problem to constraints $f(0) = 0, f(L - x) = 0$, i.e. wave equation on a _shorter string_ fixed at both ends.

When you play a harmonic of the string, you lightly touch the string without making contact with the fretboard. This means the point where you touch the string is fixed, but the string may vibrate both above and below. 

- Activating harmonic: wave equation with constraints:
    - $f(0) = 0$
    - $f(x) = 0$
    - $f(L) = 0$
    - The solutions will be explored below, but in short, the set of harmonics is restricted, but it depends on the choice of $x$ as a fraction of the string's length.

## Nodes of Each Harmonic

> Touching a point on the string a fraction of the way down its length will produce the harmonic of its denominator in lowest terms.


Let's look at the different harmonics of the full string and see where they have a node, i.e. values of $x$ where $f(x) = 0$.

| Harmonic number | Nodes at |
|-----|---|
| 1   | $0, L$ |
| 2   | $0, L/2, L$ |
| 3   | $0, L/3, 2L/3, L$ |
| ... | ...|
| n   | $0L/n=0, 1L/n, 2L/n, ..., nL/n=L$ |

So each harmonic $n$ has nodes at multiples of $L/n$ along the string. These are the key points for activating the harmonic.

However, there is some overlap. E.g. the point $L/2$ is a node for harmonics 2, 4, 6, and so on. If you touch the string at this point and strum, it will sound like the _lowest_ of these, i.e. the second harmonic.

We can summarize this as follows:
- Harmonics will be heard at points $x = (m/n)L$ where $m/n$ is a rational number in _lowest terms_
- More specifically, the $n$-th harmonic will be heard, regardless of the choice of $m$

## Locating Harmonics on a Guitar String

Where do these fractions of the string show up on a guitar fretboard? Let's list decimal values for both frets and harmonics and collate them into a list.

### Fret Positions 

- An open string has length $L_0$ and sounds at frequency $f_0$ which depends on its tuning.
- The nth fret increases the pitch by $n$ semitones, i.e. $f_n = 2^{n/12}f_0$
- $f \propto 1/L$ where $L$ is the length of the vibrating portion of the string (i.e. the portion between the fret and the bridge)
- This means $L \propto 1/f$
- Since we scaled $f$ by $2^{n/12}$, $L$ is _divided_ by $2^{n/12}$, i.e. $L_n = 2^{-n/12}L_0$, measured from the bridge.
- Measuring from the nut, we have $L_0 - L_n = (1 - 2^{-n/12})L_0$

Let's make a table of the fret positions measured from the nut.

| Fret number | $x = (1 - 2^{-n/12})L$ |
|---|---|
|0  | $0$ (exact) |
|1  | $0.056L$|
|2  | $0.109L$
|3  | $0.159L$
|4  | $0.206L$
|5  | $0.251L$
|6  | $0.293L$
|7  | $0.333L$
|8  | $0.370L$
|9  | $0.405L$
|10 | $0.439L$
|11 | $0.470L$
|12 | $0.5L$ (exact)
|13 | $0.528L$
|14 | $0.555L$
|15 | $0.580L$
|16 | $0.604L$
|17 | $0.625L$
|18 | $0.646L$
|19 | $0.666L$
|20 | $0.685L$
|21 | $0.702L$
|22 | $0.719L$
|23 | $0.735L$
|24 | $0.75L$ (exact)

### Harmonic Positions

Now, let's list the positions where each harmonic can be heard for the first 8 harmonics

| Harmonic $n$ | $k/n$ (fraction of length) |
| -------- | ---------- |
|   1      | $0, 1$ |
|   2      | $0.5$ |
|   3      | $0.333, 0.667$ |
|   4      | $0.25, \cancel{0.5}, 0.75$ |
|   5      | $0.2, 0.4, 0.6, 0.8$ |
|   6      | $0.167, \cancel{0.333}, \cancel{0.5}, \cancel{0.667}, 0.833$ |
|   7      | $0.143, 0.286, 0.429, 0.571, 0.714, 0.857$
|   8      | $0.125, \cancel{0.25}, 0.375, \cancel{0.5}, 0.625, \cancel{0.75}, 0.875$|

### Pattern Along Fretboard

Let's interleave these values to see where they show up on
the fretboard. The dashed lines indicate frets. Indented
lines indicate harmonics that show up between frets.

```
0----------0      n=1 (open string)
1----------0.056
2----------0.109
  0.125           n=8
  0.143           n=7
3----------0.159
  0.167           n=6
  0.2             n=5 (~4th fret)
4----------0.206
  0.25            n=4 (~5th fret)
5----------0.251
  0.286           n=7
6----------0.293
7----------0.333  n=3 (rounded)
8----------0.370
  0.375           n=8
  0.4             n=5
9----------0.405
  0.429           n=7
10---------0.439
11---------0.470
12---------0.5    n=2 (exact)
13---------0.528
14---------0.555
  0.571           n=7
15---------0.580
  0.6             n=5
16---------0.604
17---------0.625  n=8 (rounded)
18---------0.646
19---------0.666
  0.667           n=3
20---------0.685
21---------0.702
  0.714           n=7
22---------0.719
23---------0.735
24---------0.75   n=4 (exact)
  0.8             n=5  ---|
  0.833           n=6     |--- around electric
  0.857           n=7     |    guitar pickups
  0.875           n=8  ---|
```

TODO: I'd like to make a visualization in p5 that shows this pattern to scale