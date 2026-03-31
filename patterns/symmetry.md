# Pattern: Symmetry

There are multiple definitions for symmetry
in math depending on the context. All are related to each other.

At a high level, symmetry might be defined as a relationship where applying an operation to an object (a point, set, function, etc.) that leaves it unchanged. What exactly this means depends on the context.

For example, if you rotate an (unmarked) square by 90 degrees, the end result is indistinguishable from the original.

IMG: rotation symmetry of the square

However, for functions there's a more general notion of symmetry. I would describe it as "applying this operation to the input is the same as applying that operation to the output"

To continue the example of the square: now suppose we painted the square with a checkerboard pattern. Rotating the shape 90 degrees is the same as swapping the colors (`red <-> black`).

IMG: (rotate, swap) symmetry of a checkered square


## Identity, the strictest symmetry

IMG: Two identical objects side-by-side

Let's start with the most strictest symmetry:
The **identity function**, $I(x) = x$, a function that simply returns its input unchanged. In other words, it's a "no-op" or "do nothing" function.

I consider this the strictest form of symmetry
because it preserves anything you throw at it.

IMG: diagram of fixing points, sets and functions

- $I(x) = x$ - $I$ preserves any individual value.
- $I(S) = \{I(x) | x \in S\} = \{x | x \in S\} = S$ - $I$ also preserves any _set_ of values
- $f \circ I = f = I \circ f$ - when composed with some other function, it leaves the function unchanged.

<details>
<summary>I'm being informal here...</summary>

Technically speaking, there's a different identity function for each domain under consideration. For example, if the sets $X, Y$
are your domains, then you have functions $I_X: X \to X, I_Y: Y \to Y$.

In the function composition example, if $f: X \to Y$, the symmetry rule would be more accurately: $$f I_X = f = I_Yf$$ since the
domain and codomain are different sets.

So when I write $I$ without a subscript, I mean
"the identity function for the appropriate domain".
</details>

## Symmetry as fixing points

TODO

## Symmetry as fixing sets

TODO

## Symmetry as fixing functions

TODO

## Generalized symmetry

TODO