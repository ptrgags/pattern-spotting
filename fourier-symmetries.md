# Fourier Transform Symmetries

How do symmetries of functions in the time domain correspond
to symmetries in the frequency domain?

## Symmetries of Sinusoids

Let's look at the graph of $\sin(t)$. What operations can we
perform on this graph to make it look the same?

IMG: Sine wave with symmetries labeled

- $I$: Identity, i.e. do nothing.
- $T_{2\pi}$: If we translate the graph to the right by $2\pi$ radians, we get the same shape.
- $R_2$: 2-fold rotation (half turn) around the origin. 
- $\gamma_{\pi} = T_{\pi}Y$: Glide reflection - flip the graph in the y-direction ($Y$) and then shift it over by $\pi$ radians. Notice that the individual transformations are _not_ symmetries here, only the composite
- All Compositions of the above transformations
- Honorable mention: There's a mirror reflection at $\pi/2$, but this can be built from a combination of rotation and glide reflection.

IMG: $X_{\pi/2}$ is made up of other transformations.

What about $\cos(t)$?

IMG: $\cos(t)$ with symmetries labeled

- $I$
- $T_{2\pi}$
- $\gamma_{\pi}$
- $X$ - reflection in the origin
- All Compositions of the above
- Honorable mention: There's a 2-fold rotation at $\pi/2$, but this can be built from a reflection and glide reflection

IMG: rotation is glide * reflection

### Recipe: Graph symmetries

In the previous section we defined the symmetry operations by visual inspection of the graph. A graph is the set of points $(x, f(x))$ for all $x$ in the domain. So one possible realization is a set of functions that map $\mathbb{R}^2 \to \mathbb{R}^2$:

- $I(x, y) = (x, y)$
- $X(x, y) = (-x, y)$
- $R_2(x, y) = (-x, -y)$
- $T_d(x, y) = (x + d, y)$ where $d$ is the translation amount
- $\gamma_d(x, y) = (x + d, -y)$

In this context, for one of the above transformations $Z$ to be a symmetry of the graph of $f$, we're saying that

$Z(\text{graph}(f)) = \text{graph}(f)$

Note that this is an equation on _sets_. So $Z$ can scramble the arrangement of points within a set, but overall the shape must
be exactly he same.

### Recipe: Function symmetries

How are these transformations related to the function itself?
We can transform a point $(x, f(x)) \in \text{graph}(f)$ and see
what must be true for the end result to produce the same set.

- Identity: $I(x, f(x)) = (x, f(x))$
    - The output is the same as the input, so we've fixed not only the graph, but _every point_ within!
    - This relationship holds for _any_ function $f$
- Horizontal reflection: $X(x, f(x)) = (-x, f(x))$ 
    - By the definition of graph, the point corresponding to $-x$ is $(-x, f(-x))$. 
    - For both of these relationships to be hold, we need $f(x) = f(-x)$. 
    - In other words, $f$ must be an even function.
    - Since $\cos$ is even, but $\sin$ is not, only $\cos$ has this symmetry
- 2-fold rotation: $R_2(x, f(x)) = (-x, -f(x))$
    - By the definition of graph, this must equal the point $(-x, f(-x))$
    - For both of these to be true, $-f(x) = f(-x)$
    - In other words, $f$ must be an odd function
    - Since $\sin$ is odd, but $\cos$ is not, only $\sin$ has this symetry.
- Translations: $T_d(x, f(x)) = (x + d, f(x))$
    - The corresponding point in the graph is $(x + d, f(x + d))$
    - So we require $f(x + d) = f(x)$
    - For both $\sin$ and $\cos$, this is true when $d = 2\pi k$ for some integer $k$. 
    - So $T_{2\pi k} = T_{2\pi}^k$ are symmetries of both sinusoids
- Glide reflations: $\gamma_d(x, f(x)) = (x + d, -f(x))$
    - The corresponding point in the graph is $(x + d, f(x + d))$
    - so the symmetry condition is $f(x + d) = -f(x)$
    - For both $\sin, \cos$, we have this symmetry when $d = \pi + 2 \pi k$. 
    - So $\gamma_{(2k + 1)\pi} = \gamma_{\pi}^{2k + 1}$ are symmetries of both sinusoids
    - Why only odd powers? well, $\gamma_d^2(x, y) = (x + 2d, (-1)^2y) = (x + 2d, y) = T_{2d}(x, y)$. So even powers fall under translation symmetry above.