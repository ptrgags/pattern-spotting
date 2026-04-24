---
layout: default
---
## Fourier Transform

## Prerequisites

This page uses definitions and notation from the following pages:

- [Uniform Circular Motion](./circular-motion.html)

## Definition

> The Fourier Transform takes a signal in time and decomposes it into
> periodic motion at various frequencies (i.e. a **frequency spectrum**)
>
> Furthermore, this transform is invertible. The inverse transform takes a
> frequency spectrum and turns it into a time signal.

$$
\begin{align*}
\mathscr{F}f(t) &= \hat{f} (k) = \int_{-\infty}^\infty f(t) e^{-i 2\pi k t} dt \\
\mathscr{F^{-1}}\hat{f}(k) &= f (t) = \int_{-\infty}^\infty \hat{f}(k) e^{-i 2\pi k t} dk \\
\end{align*}
$$

There are already plenty of great explanations of the Fourier Transform out there, so I'll defer to them:

- "But what is the Fourier Transform? A visual introduction" by Grant Sanderson (3Blue1Brown) on [YouTube](https://youtu.be/spUNpyF58BY?si=PVU2ZzNc5tNfJndB) and an [interactive website](https://www.3blue1brown.com/lessons/fourier-transforms/)
- ["An Interactive Guide To the Fourier Transform"](https://betterexplained.com/articles/an-interactive-guide-to-the-fourier-transform/) on BetterExplained.com
- ["Demystifying Fourier Analysis"](https://dsego.github.io/demystifying-fourier/) by Davorin Šego

## Shorthand

I like to use the following abbreviations to make the Fourier Transform
more readable.

- I like to define a function $C_k(t) = e^{2\pi i k t}$ (see [Uniform Circular Motion](./circular-motion.html)) to abbreviate the complex exponential. This has some benefits:
    - It emphasizes that that exponential represents _circular motion_. 
    - Using a subscript emphasizes which variable is held constant.
    - Quite a few operations can be written concisely. E.g. when multiplying complex exponentials, $C_aC_b = C_{a+b}$
    - It saves writing $2 \pi i$ in many places.
- Sometimes I like to drop the function arguments and just use the function name. E.g. $f$ instead of $f(t)$. This puts emphasis on the signal as a function object rather than a formula for computing specific time/frequency samples.
- Sometimes I'm lazy and write $\int$ instead of $\int_{-\infty}^\infty$ since this is the most common integral bounds in this context.

Combining all of the above, I abbreviate the Fourier Transform as:

$$
\begin{align*}
\mathscr{F}f &= \hat{f} = \int f C_{-k} dt \\
\mathscr{F^{-1}}\hat{f} &= f = \int \hat{f} C_{t} dk \\
\end{align*}
$$

## Related Patterns

- [Fourier Symmetries](./fourier-symmetries.html) - The Fourier Transform has several symmetries that help simplify or avoid the calculus in many places