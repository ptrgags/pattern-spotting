# Patterns in Space and Time

## Functions of Space

- static image: a function from space to a color

## Functions of Time

- parametric equations
    - explicit function of time
    - stateless, so you can animate forwards, backwards, jump to specific time
    - Special cases:
        - inbetweens - makes it easier to express piecewise functions, but ultimately are just fancy parametric equations.
        - periodic functions are handy for looping animations
        - splines for interpolating points
- Audio

## Functions of Space and Time

- Animation
- cellular automatons
    - Function of both space and time in general
    - rules may examine a neighborhood in space
    - Often time is in discrete steps
    - in some cases, cellular automatons are discrete approximations of a differential equation (e.g. some elementary CAs are like a simpler model of seashell pattern) 
    - but rules can be anything, does not necessarily have to be differentiable
- Differential equations
    - Function of both space and time in general
    - theoretically, continuous in space and time
    - in practice, need to use discrete approximations
- L-systems
    - each iteration is like a step in time
    - context-sensitivity examines neighbors in space
    - production rules link previous generation to next generation in _time_
    - time-based L-systems express more in-between parameters
    - recursive sequencies
    - e.g. fibonacci sequence
    - Digital signal processing: recursive filters
    - like a discrete function of 
- Differential growth
    - Can be done as a cellular automaton or differential equation
    - However, the output space can grow!
        - e.g. leaves curl up at the edges
        - brains curl up as they grow
        - algorithms might represent a curve/surface, where you can add points from one iteration to the next
    - Crocheting is great for exploring this since fabric can bend into shapes only possible in hyperbolic geometry
    - 3D meshes? though might need a fabric sim to get the resulting shape
    - curiosity: relationship between this and L-systems?

## Spacetime as Geometry

- 4D space time
    - in physics, treats time and space as a unified geometry (with some quirks due to the metric)
    - This view is a little different, instead of an animation, you have a higher dimensional shape since time is converted to a spatial dimension
    - more concrete example: imagine taking the frames of a video and plotting them along a third axis, connecting correponding points. Each curve through the stack is a world line, and surfaces would be world sheets(is that the right term?)
- Things that grow, depositing a history
    - shells of mollusks
    - coral skeletons
    - fingernails
    - knitting a scarf
    - log files