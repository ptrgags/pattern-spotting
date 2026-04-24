# Fourier Series for Basic Waves

🚧 Outline for now

## Sine and Cosine

$$
\mathscr{F}\sin_n = \frac{\delta_n - \delta_{-n}}{2 i}\\
\mathscr{F}\cos_n = \frac{\delta_n + \delta_{-n}}{2}
$$

TODO: Explain this, it's just the [circular motion definitions for sin/cos](./sin-cos-circle.html) + [linearity](./fourier-symmetries.html#linearity)

## Square

TODO:
    - The integral isn't too bad, you chop up the cycles into two half cycles with opposite signs
    - With a bit of algebra, you find that the two halves will have the same value, so you only need to compute one of the integrals
    - Expanding the integral, and 
- The end result is that you have only odd frequencies, and 
- ❓Another way to look at the same thing is you're adding an infinite number of boxcar functions together (with alternating signs) - what can we learn from that
- You can also make a square wave from adding two sawtooth waves with a phase shift. Does that make either this definition or the one for sawtooth easier?
- Connections: audio:
    - it has a "woody" sound. This is found in closed-pipe instruments (e.g. clarinet)
    - Also if you pluck a guitar string exactly in the center you get a similar sound
    - Not exactly the same spectrum, but on an FM synth, a C:M ratio of 2 creates every other harmonic
    - On a drawbar organ, you can approximate this by setting every other stop

## Triangle

TODO: I haven't worked out this one yet

- I know it's like a square wave in that only odd frequencies are present
- The amplitudes fall off with $1/k^2$

## Sawtooth

TODO: I'm still working out the details

- I know every frequency is presnet
- String fixed on both ends, open-pipe instruments
- The amplitudes fall off with $1/k$

## Pulse Wave

TODO: Still figuring out the details

- Similar setup to the square wave, but now the positive and negative parts
are unequal in time
- Result is going to involve sinc functions

## More Complex Waves

- [Oscillator Sync](./osc-sync.md) - A waveform that restarts before it completes a cycle
- [Pulse Width Modulation](./pulse-width.md) - Most often used with square waves, by squishing a cycle into a partial cycle and filling the rest of the cycle with zeros

## Other Notes

- I found [this paper](https://arxiv.org/pdf/0806.0150v2) about some properties of the sinc function, maybe it will come in handy