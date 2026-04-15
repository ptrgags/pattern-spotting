# Circular Motion

IMG: Diagram of Circle Function

Let $C_n(t)$ be counterclockwise motion around a circle at a constant rate of $n$ cycles/second (Hz), or $2\pi n$ radians/second.

This is a key building block in math, as it can be used to build periodic signals. It also plays a key role in the [Fourier Transform](./fourier-transform.md).

## Recipes

The circle function can be written in several different ways, depending on the mathematical context.

- As a 2D parametric equation: $$C_n(t) = (\cos(2\pi n t), \sin(2\pi nt))$$
- As a function of complex numbers (via Euler's Formula): $$C_n(t) = e^{i2\pi n t} = \cos(2\pi t) + i \sin(2 \pi t)$$
- As a rotor in 2D Geometric Algebra (and in many other flavors of GA): $$C_n(t) = e^{-2\pi n \mathbf{xy} / 2} = \cos(\pi t) - \sin(\pi t)\hat{B}$$ for unit bivector $\mathbf{xy}$. This is applied to geometric algebra objects as $C_n(t)vC_n(t)^\dagger$.
- As a 2D matrix transformation: $$C_n(t) = R_{2\pi t} = \begin{bmatrix}
\cos(2\pi t) & -\sin(2\pi t) \\ 
\sin(2\pi t) & \cos(2\pi t) \\
\end{bmatrix}$$

## Properties of Circular Motion

- When the frequency is 0, circular motion reduces to a constant position $$C_0(t) = (1, 0)$$

<details>
<summary>Two proofs of constant motion rule</summary>

In the parametric equation form, $\cos(0) = 1, \sin(0) = 0$ so the components are $(1, 0)$

With complex numbers, we have $e^0 = 1$, which is +1 unit on the real line and 0 on the imaginary line.
</details>

- A negative frequency (rotating CW instead of CCW) is equivalent to reversing time:$$C_{-n}(t) = C_n(-t)$$
- Composing two circular motions produces a new circular motion with the sum of the frequencies: $$C_aC_b = C_{a+b}$$

<details>
<summary>Proof of multiplication rule</summary> 

Using the complex number representation, we can use
the property of exponents.

$$e^{i 2\pi a t}e^{i 2\pi b t} = e^{i 2\pi (a + b) t}$$

This relies on the commutativity of complex numbers under multiplication.
</details>

- [Reflecting](./reflection.md) the circular motion in a mirror reverses its direction: $$\text{reflect} \circ C_n = C_{-n}$$

<details>
<summary>Proof of reflection rule</summary>

This is easiest to show in complex numbers, since complex conjugation $z \mapsto \bar{z}$ is a simple way to write a reflection over the horizontal axis.

$$\overline{C_n(t)} = \overline{e^{i 2 \pi n t}} = e^{-i 2\pi n t} = C_{-n}(t) $$

</details>