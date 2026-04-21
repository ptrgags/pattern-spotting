# Trochoids

🚧 Outline for now

- [Hypotrochoid (wiki)](https://en.wikipedia.org/wiki/Hypotrochoid)
    - Outer circle radius $R$
    - Inner circle radius $r$
    - So the center of the moving gear is at radius $R - r$ and just rotates around the origin.
    - The drawing arm is a distance $d$ from the center of the moving gear, and rotates in the opposite direction
    - the drawing arm's frequency is the ratio $(R - r)/r$ (TODO: why was this?)
    - so in terms of [circular motion](./circular-motion.html) we have $((R - r)C_n + dC_{n(R-r)/r})C_1$
- [Epicycloid (wiki)](https://en.wikipedia.org/wiki/Epicycloid)
    - Stationary gear has radius $R$
    - Moving gear's center is at radius $R + r$
    - this time the ratio is $(R + r)/r$
    - So we have $((R + r)C_n - dC_{n(R+r)/r})C_1$
        - TODO: Why the negative sign? maybe a starting phase?

## More Details

- TODO: Is there a way to connect the two into one formula?
- TODO: Are there choices of $R, r, d$ that produce [rose curves](./rose-curves.html) or [lissajous curves](./lissajous.html) curves?
- [My past Drawing Machines](https://ptrgags.dev/drawing-machines/) project made use of these trochoids