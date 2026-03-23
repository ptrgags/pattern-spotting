# Fourier Transforms from Scratch

Let's explore the Fourier transform in a more intuitive way
by making use of patterns wherever we go

First, some preliminaries

## Circle Functions

IMG: Diagram of the two interpretations... or maybe a Desmos graph?

Let $C_n(t) = e^{i 2 \pi n t}$ be the circle function with linear frequency $n$ over time $t$. As $t$
goes from $0 \to 1$, it traverses the unit circle counterclockwise $n$ times.

Some handy properties of this function:

- $C_0 = 1$
    - this is because $e^0 = 1$
- $C_n(t) = 1$ whenever $nt = k$ for some integer k
    - This is because $e^{i \theta} = 1$ when $\theta = 2 \pi k$
    - Here $\theta = 2\pi n t$ so $k = nt$
- $C_aC_b = C_{a + b}$ 
    - $\exp(i 2 \pi a t)\exp(i 2 \pi b t) = \exp(i 2 \pi (a + b) t) = C_{a + b}$
- $C_n(t) = C_t(n)$
    - Since multiplication is commutative, $nt = tn$ so we can swap the variables
    - This means there are really 2 interpretations of the complex exponential!
    - a point spinning around the unit circle in time at constant frequency $n$
    - Sampling the $n$-th point around the unit circle when moving with constant step size $2\pi t$
- $C_n(t + d) = C_n(t)C_n(d)$
    - Combine the previous two rules
- $\overline{C_n} = C_{-n}$
    - This is because $\overline{e^{i\theta}} = e^{-i\theta}$
- $|C_n| = 1$
    - We're walking around the unit circle so the radius stays constant
    - You could also take Euler's Formula and take the magnitude of that which reduces to $\sin^2 + \cos^2 = 1$

### Circle Function Basis

We can make a signal by taking linear combinations of circle functions:

$f(t) = \sum_n a_n C_n(t)$

## Dirac Delta

The [Dirac delta function](https://en.wikipedia.org/wiki/Dirac_delta_function) $\delta(x)$ is an unusual one. It's defined as $$\delta(x) = \begin{cases}\infty & x = 0 \\ 0 & x \ne 0\end{cases}$$

It's a spike at 0, and 0 everywhere else. If we want to put the
spike somewhere else, we can shift the function to the right by $k$ like any other function:

$$\delta_k(x) = \delta(x - k) = \begin{cases}\infty &x=k  \\ 0 &x \ne k\end{cases}$$

### Dirac Delta Basis

We can use linear combinations of deltas to create a collection of spikes with different amplitudes. This is most often seen
as the spiky-looking frequency spectrum

$$f(k) = \sum_n a_n \delta_n(k)$$

IMG: example spectrum

Some subtleties here:

- $a_n$ in general is a complex number, so most graphs you see plot the _magnitude_ $|a_n|$.
- The spikes in theory should be infinitely tall, so instead we plot just the _coefficients_ which are finite.


### Properties of the Dirac Delta

In later sections, we'll need some other properties of the
dirac delta. 

- $\int_{-\infty}^\infty f(t)\delta_k(t) dt = f(k)$ - the [sampling property](https://en.wikipedia.org/wiki/Dirac_delta_function#Translation)
- $f(k) = \sum_n a_n \delta_n(k) = a_k\delta_k(k)$ when fully expanded
    - This is because all of the other $\delta_n(k) = 0$ by definition 
- $\int_{-\infty}^\infty C_{-k}(t) dt = \delta(k)$
    - TODO: Why does this work? I don't fully understand it at present.
    - Nevertheless, this property can be found in [this table](https://en.wikipedia.org/wiki/Fourier_transform#Distributions,_one-dimensional), row 301

## Fourier Transform Definition

There are [several different definitions](https://en.wikipedia.org/wiki/Fourier_transform#Definition) of the transform, which mostly differ by some scale factors. I'll be
using the following definitions:

$$\mathscr{F}f(t) = \hat{f}(k) = \int_{-\infty}^\infty f(t) e^{-2 \pi k t} dt$$
$$\mathscr{F^{-1}}\hat{f}(k) = f(t) = \int_{-\infty}^\infty f(k) e^{2 \pi t k} dk$$

This is a lot of symbols on the page, let's make up some shorthand. Since the integration bounds will always be $\pm \infty$ and we defined the circle function $C_n$ earlier, let's
shorten this to 

$$\mathscr{F}f = \hat{f} = \int f C_{-k} dt$$
$$\mathscr{F^{-1}}\hat{f} = f = \int \hat{f}C_t dk$$

This alternate notation emphasises one subtletly about the
inverse transform: not only does the sign of the angle get
negated, but the roles of the time $t$ and the frequency $k$
reverse. 

## Fourier Transform is Linear

> ![TIP]
> You can distribute a Fourier transform over a linear combination of functions

Let's prove that $\mathscr{F}$ is linear. This is inherited from properties of integrals in general

- $\mathscr{F} (f + g) = \int(f + g) C_{-k} dt = \int f C_{-k} dt + \int g C_{-k} dt = \mathscr{F}f + \mathscr{F} g$
- $\mathscr{F} (\lambda f) = \int \lambda f C_{-k} dt = \lambda \int f C_{-k} dt = \lambda \mathscr{F} f$

The proof for $\mathscr{F}^{-1}$ follows the same logic.

The important thing here is now we can take the Fourier series
of a linear combination of functions by linearity:

$$\mathscr{F} (\sum_n a_n f_n) = \sum_n a_n \mathscr{F} f_n = \sum_n a_n \hat{f_n}$$

## Fourier Pair: 1 and Dirac Delta

> ![TIP]
> a constant function in time is equivalent to a spike at 0 in frequency space

- $\mathscr{F} 1 = \int 1 C_{-k} dt = \delta(k)$ - See the properties section for diract delta
- $\mathscr{F^{-1}} \delta(k) = \int \delta(k) C_t(k) dk = C_t(0) = 1$
- so $1 \leftrightarrow \delta$

## Fourier Pair: Circle function and Shifted Delta

> ![TIP]
> An oscillation in time at a constant frequency corresponds to a specific peak in the frequency spectrum

- $\mathscr{F}C_n = \int C_n C_{-k} dt = \int C_{n - k} dt = \int C_{-(k - n)}dt = \delta_n(k)$
- $\mathscr{F}^{-1}\delta_n = \int \delta_n C_t dk = C_t(n) = C_n(t) = C_n$
- So $C_n \leftrightarrow \delta_n$
- Also notice that since $C_0 = 1$ and $\delta_0 = \delta$, $1 \leftrightarrow \delta$ is a special case

## Fourier Pair: Circle Basis and Delta Basis

> ![TIP]
> A linear combination of oscillations in time corresponds to a collection of peaks in the frequency spectrum. Furthermore, the amplitudes match.


Let's combine the results from the previous section and
linearity of the fourier transform to see what happens to a complex signal:

- $\mathscr{F}f = \mathscr{F}\sum_n a_n C_n = \sum_n a_n \mathscr{F} C_n = \sum_n a_n \delta_n$
- $\mathscr{F}^{-1}f = \mathscr{F}^{-1}\sum_n a_n \delta_n = \sum_n a_n \mathscr{F}^{-1} \delta_n = \sum_n a_n C_n$
- So $\sum_n a_n C_n \leftrightarrow \sum_n a_n \delta_n$