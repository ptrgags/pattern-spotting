# Dirac Delta

🚧 Outline for now

## Definition

$$\delta(x) = \begin{cases}
    \infty & x = 0 \\
    0 & x \ne 0
\end{cases}$$

This represents a spike at the origin.

This is not a function in the usual sense, though I'm not familiar with the relevant math (distribution theory) to explain it. I'll defer to the [wikipedia page](https://en.wikipedia.org/wiki/Dirac_delta_function) for now.

## Shifted Dirac Delta

The Dirac Delta can be shifted to have the spike at $d$ instead of 0. This works exactly like shifting any function:

$$\delta_d(x) = \delta(x - d)$$

Using this notation, we can write the unshifted Dirac Delta as $\delta_0$:

$$\delta_0(x) = \delta(x-0) = \delta(x)$$

## A Spiky Basis

In practice, we use the shifted Dirac Delta as a basis for signals that have values at a few specific points, and 0 everywhere else. For example:

$$f(x) = \delta_1(x) + \frac{1}{2}\delta_2(x) + \frac{1}{3}\delta_3(x)$$

A common use for this is for defining a frequency spectrum
(see [Fourier Transform](./fourier-transform.md) and related pages). In such a context, the above equation would be interpreted as follows:

- The signal has amplitude 1 at a frequency of 1 Hz
- The signal has amplitude 1/2 at a frequency of 2 Hz
- The signal has amplitude 1/3 at a frequency of 3 Hz
