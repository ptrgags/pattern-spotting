## Trigonometry Patterns

## Memorizing Sine and Cosine Values

- When first learning trigonometry, there's a handful of values of sine/cosine to memorize
- These are for special angles: $0, \pi/6, \pi/4, \pi/3, \pi/2$
    - These angles are related to special right triangles: 45-45-90 and 30-60-90
    - Why not other angles? that's a complicated story... (this should go on a separate page):
        - You can find exact trig values by applying the half-angle and double angle formulas... but you quickly get nested square roots
        - Not every angle can be represented this way (I need to find my notes on this, it had something to do with constructible numbers iirc)
        - There are other tricks for getting an exact value.
- Use symmetry to memorize less!
    - IMG: make diagrams of symmetries
    - Cosine values are positive on the right half-plane, and negative on the left half-plane
    - Sine values are positive in the upper half plane, and negative on the lower half-plane
    - over the diagonal $y = x$, cosine and sine values swap
    - All this together means we can examine just one of the trig values (I'm going to pick cosine) and recover the other trig function
    - IMG: from $\cos(\theta)$, show how to recover the other values
- It's as easy as 0, 1, 2, 3, 4 (kinda)
    - let's look at cosine values for the special values in order.
    - $0, 1/2, \sqrt{2}/2, \sqrt{3}/2, 1$
    - THe pattern is kinda hidden. Let's make the fractions look more like each other.
    - First, notice that the denominators are usually 2. We can rewrite $0 \to 0/2, 1 \to 2/2$
    - Second, all the numerators are square roots! $0 = \sqrt{0}, 1 = \sqrt{1}, 2 = \sqrt{4}$.
    - so now we have $\sqrt{[0, 1, 2, 3, 4]}/2$. But since $2 = \sqrt{4}$, we can have $\sqrt{[0/4, 1/4, 2/4, 3/4, 4/4]}$ -- that's a much easier pattern to remember!
- why the square root?
    - points on the unit circle must obey $x^2 + y^2 = 1$
    - If we want two numbers that add to 1, we could choose $x, (1-x)$ so that $x + 1 - x = 1$.
        - This is used in linear interpolation!
    - however, for a circle, that gives you $x^2 + (1 - x)^2 = x^2 + 1 -2x +x^2 \ne 1$
    - But what if we took the square root of each number to cancel out the squares?
        - $\sqrt{x}, \sqrt{1 - x}$
        - $\sqrt{x}^2 + \sqrt{1 - x}^2 = x + 1 - x = 1$, perfect!
    - Related - distance metrics. $x, 1-x$ is to Manhattan distance as $\sqrt{x}, \sqrt{1 -x}$ is to Euclidean distance
    - This could be generalized to other distance metrics to find points on superellipses!


## Sine, Cosine, or Tangent? 

IMG: fishing rod, crocodile, flagpole diagram

- On the unit circle, cosine is in the x-direction, and sine is in the y-direction
- However, this is assuming that angles are measured from the x-axis towards the y-axis
- This isn't always the case! there are places where the axes might be oriented a different way!
    - in physics, when you examine a block sliding on an incline, the axes are rotated, and this leads to situations where the angles are measured from the y-axis. In that case, cosine and sine swap!
    - In 2D graphics, the y-axis is downwards, so your sine values are negated, but not the cosine values!
    - in 3D, the axes may be oriented in many different ways.
- So it's more helpful to learn the _shapes_ of each ratio, and then mentally rotate the shape to match the situation.
- visual mnemnoic I came up with in high school
    - My math teacher pointed out that cosine looks like a crocodile's jaws
    - I thought the setup for sine looks like a fishing rod
    - And I remembered a math problem where tangent is used to calculate the height of a flagpole, so tangents make me think flagpoles