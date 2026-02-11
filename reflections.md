# Reflections

Page Status: OUTLINE

## Basic properties

- Something that works like looking in a mirror
    - Points "parallel" to the mirror stay in place (e.g. the glass of the mirror)
    - Points "orthogonal" to the mirror flip over to the other side (e.g. you and your mirror image swap places)
- The "distance" between the original point to the mirror is the same as the distance from the mirror to the image
- It's an "involution" - a transformation that when you repeat it twice, it cancels out
- Terms above in quotes have some interesting generalizations

COMIC IDEA: "upon further reflection, I ended up back where I started"

## Digital Images

- The transformation `image[i, j] = image[(rows - 1) - i, j]` flips an image horizontally
    - In a shader, the equivalent is `(u, v) = ((1 - u), v)`
- The transformation `image[i, j] = image[i, (cols - 1) - j]` flips an image vertically
    - In a shader, the equivalent 1is `(u, v) = (u, - v)`
- If you do both at once, you get not a reflection, but a rotation (by 180 degrees)
- The transformations (identity, horizontal flip, vertical flip, horizontal and vertical flip) form a group, isomorphic to the Klein 4-group
- The transformation `rgb = 255 - rgb` inverts the color
    - It's like flipping a linear gradient backwards
    - In a shader, this would be `color = 1 - color`

## Music

- Playing a melody backwards is called retrograde. You can think of this as
a reflection in time.
    - More specifically, it's a reflection in the halfway point in the piece's progression
- Flipping the pitches of a melody over a central pitch is called an inversion
    - you can also define it in terms of inverting intervals, so steps up become steps down
- You can do both at once, a retrograde inversion (a 180 degree reflection)
- The transformations (identity, retrograde, inversion, retrograde inversion) form a group, isomorphic to the Klein 4-group
- Sample editing equivalents:
    - retrograde: Playing an audio sample backwards (like reverse cymbals)
    - inversion: Flipping the samples so positive values become negative and vice-versa
        - This usually sounds the same as the original audio
        - However, if you play audio and its inverse together, they cancel out! this is the principle behind active noice canceling headphones
    - retrograde inversion
        - combines the effects
        - For a sine wave (which already has rotation symmetry), the end result is _identical_ to the original wave!
- Digital filters
    - a lowpass filter is the mirror image of a high-pass image (❓Is it exactly? or just approximately?)
    - Meanwhile bandpass and notch filters look the same (albeit the cutoff frequency gets swapped)

## Wordplay

- sentence a in words the reverse can You
- uoY nac esrever eht srettel fo a ecnatnes

## Arts and Crafts

- If you fold a piece of paper in half and cut or puncture both parts of the paper, you can produce the mirror image
- Using a vertical pane of glass/plastic, you can trace a mirror image (what do you call that drafting tool?)

## Complex Plane

- The complex conjuage operation, $\overline{z} = x - yi$ is a reflection in the real line
- To reflect in the imaginary line, you do $-\overline{z} = -x + yi$

## In Geometric Algebra

The fundamental operation in geometric algebra is the reflection. A vector $v$
represents a reflection, and is applied to other objects via the formula
$v(-x)v$. The interpretation of this depends on the flavor of GA.

### Vectorspace GA

In $G(n)$, a vector represents a reflection in a (hyper)plane that always
goes through the origin

- 1D: Reflection in a point (0-plane) through the origin
- 2D: Reflection in a line (1-plane) through the origin
- 3D: Reflection in a plane (2-plane) through the origin
- 4D: Reflection in a 3-plane through the origin
- ...
- ND: Reflection in a (n-1)-plane through the origin

### Projective GA

in $G(n, 0, 1)$, we can interpret a vector in either the $(n + 1)$-d base
space, or the $n$-d projected space.

In the base space, we have

- 2D: Generalized reflection in a line through the origin
- 3D: Generalized reflection in a plane through the origin
- 4D: Generalized reflection in a 3-plane through the origin
- ...
- ND: Generalized reflection in a (n-1)-plane through the origin

TODO: Explain that reflections here include Euclidean, but also some unusual
ones using mixed vectors
TODO: Caveat about null vectors

However, if we stand at the origin and look along the null axis (projection/homogeneity),
what do we see in the $n$-d space?

- 1D: Reflection in some point (not necessarily the origin!)
- 2D: Reflection in some line
- 3D: Reflection in some plane
- 4D: Reflection in some 3-plane
- ...
- ND: Reflection in some (n-1)-plane

### Conformal GA

In $G(n + 1, 1)$, we have three different ways to interpret vectors. The complete
$(n + 2)$-d space, the $(n + 1)$-d projected "Klein Disk" space (similar to PGA), and 
the $n$-d conformal space under a second projection

In the base space, we have:

- 3D: Generalzied reflection in a plane through the origin
- 4D: Generalized reflection in a 3-plane through the origin
- 5D: Generalized reflection in a 4-plane through the origin
- ...
- ND: Generalized reflection in a (n-1)-plane through the origin

TODO: explain what I mean by generalized reflection
- reflections look different in Euclidean, hyperbolic, or parabolic transformations. The distance to the mirror is the same on both sides of the mirror, but the direction doesn't always look orthogonal. You can also define these in terms of rotating through an angle, the mirror is at the halfway point.
- Though does this generalize to more than 2 dimensions?

TODO: caveat about null vectors

In the projected "Klein" space, we have:

- 2D: Hyperbolic reflection in a line
- 3D: Hyperbolic reflection in a plane
- 4D: Hyperbolic reflection in a 3-plane

TODO: Explain Hyperbolic reflection (polarity)
TODO: How to explain it for higher dimensions?
TODO: Caveat about duals
TODO: Caveat about null vectors

In the doubly-projected conformal space, we have:

- 1D: Inversion in a generalized point pair
- 2D: Inversion in a generalized circle
- 3D: Inversion in a generalized sphere

TODO: Explain these generalized shapes
TODO: Caveats about duals

## Other Involutions

- Matrix transpose
- Permutations like $(1 2)$ that swap two elements
- Negation $-x$
- Reflect in a point
    - Interestingly in 2D it's the same as a 180 degree rotation about the same point
- swap between two colors from a palette (checkerboard style)
- Logical NOT operation
- Set complement
- Dual $x$ in geometric algebra (well, sometimes. Other times you have a dual and an anti-dual)
- Inverse $x^{-1}$
- Reversing a sequence of steps requires reversing 
    - $(ab)^{-1} = b^{-1}a^{-1}$
    - ❓Wait a sec... is this at all related to 
        - De Morgan's laws, like $\neg (a\wedge b) = \neg a \vee \neg b$
        - $\star^{-1}(a \vee b) = \star a \wedge \star b$ in geometric algebra? (NOTE: I'm a bit rusty, do I have the dual and antidual swapped?)
- when knitting, flipping over the work simultaneously swaps visible knits (v) and purls(-) and reverses the order of stitches horizontally



## Other ideas for reflections

- I've mostly limited myself to describing reflections as an operation
    - but then there's patterns that have bilateral symmetry, that could be its own page
    - What about patterns where you juxtapose mirror images? e.g. balanced brackets []
- even functions in math
- real life mirrors/kaleidoscopes
- interpolation uses (1-t, t) which are reflections of each other
- sawtooth vs ramp wave is just a matter of reflection
- light rays reflect through the normal
- real life mirrors flip z coordinate
- in shaders, absolute value is used to fold space
- I haven't mentioned chirality!