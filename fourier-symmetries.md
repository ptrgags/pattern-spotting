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

### Recipe: Conditions for symmetry

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

### Meta pattern

There's a meta- pattern to the above. If we take transformation $Z$
it transforms a point $(x, y) \to (A(x), B(y))$

- $Z(x, f(x)) = (A(x), Bf(x))$
    - This point must correspond to $(A(x), fA(x))$ by definition of $\text{graph}(f)$
    - For this to be true, $Bf(x) = fA(x)$ for all $x$
    - So in this sense, $(A, B)$ is a symmetry of $f$
    - This corresponds to $Z$ being a symmetry of $\text{graph}(f)$
    - These are different, yet related notions of symmetry. 
        - $Z$ is a transformation of 2D points and fixes a set. 
        - $A$ transforms the domain of $f$.
        - $B$ transforms the codomain of $f$
        - Individually, $A$, $B$ aren't required to fix any points or sets
        - however, $A, B$ work together to fix the graph
    - More interpretations for $fA = Bf$
        - If you want to commute $A$ to the left, $f$ transmutes it into $B$
        - If you want to commute $B$ to the right, $f$ transmutes it into $A$

IMG: Diagram of this pattern

## Circle Functions

Let $C_n(t) = e^{i 2 \pi n t}$ be the circle function. It rep

Some handy properties of this function:

- $C_aC_b = C_{a + b}$ 
    - $\exp(i 2 \pi a t)\exp(i 2 \pi b t) = \exp(i 2 \pi (a + b) t) = C_{a + b}$
- $C_n(t) = C_t(n)$
    - Since multiplication is commutative, $nt = tn$ so we can swap the variables
    - This means there are really 2 interpretations of the complex exponential!
    - a point spinning around the unit circle in time at constant frequency $n$
    - Sampling the $n$-th point around the unit circle when moving with constant step size $2\pi t$
- $\overline{C_n} = C_{-n}$
    - This is because $\overline{e^{i\theta}} = e^{-i\theta}$
- $|C_n| = 1$
    - We're walking around the unit circle so the radius stays constant
    - You could also take Euler's Formula and take the magnitude of that which reduces to $\sin^2 + \cos^2 = 1$

IMG: Diagram of the two interpretations

