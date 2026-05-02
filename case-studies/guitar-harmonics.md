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

Let's make a table of the fret positions measured from the nut:

| Fret number | $x = (1 - 2^{-n/12})L_0$ |
|---|---|
|0  | $0$ (exact) |
|1  | $0.056L_0$|
|2  | $0.109L_0$
|3  | $0.159L_0$
|4  | $0.206L_0$
|5  | $0.251L_0$
|6  | $0.293L_0$
|7  | $0.333L_0$
|8  | $0.370L_0$
|9  | $0.405L_0$
|10 | $0.439L_0$
|11 | $0.470L_0$
|12 | $(1/2)L_0$ (exact)
|13 | $0.528L_0$
|14 | $0.555L_0$
|15 | $0.580L_0$
|16 | $0.604L_0$
|17 | $0.625L_0$
|18 | $0.646L_0$
|19 | $0.666L_0$
|20 | $0.685L_0$
|21 | $0.702L_0$
|22 | $0.719L_0$
|23 | $0.735L_0$
|24 | $(3/4)L_0$ (exact)