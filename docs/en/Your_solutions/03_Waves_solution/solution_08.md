# Task 08 – Which Functions Describe Traveling Waves?

## Problem Statement

Determine which of the following functions satisfy the wave equation

$$
\frac{\partial^2 y}{\partial x^2} = \frac{1}{v^2}\frac{\partial^2 y}{\partial t^2}
$$

### a)

$$
y(x,t) = A \cos(kx^2 - \omega t)
$$

### b)

$$
y(x,t) = A(x - vt)^2
$$

### c)

$$
y(x,t) = A \log(x + vt)
$$

## Theory

Any twice differentiable function of the form

$$
y(x,t) = f(x-vt)
$$

or

$$
y(x,t) = g(x+vt)
$$

is a traveling wave and satisfies the one-dimensional wave equation.

Therefore, one may test the given functions either by direct substitution into the wave equation or by checking whether they depend only on $x-vt$ or $x+vt$.

## Step-by-Step Solution

### a) Function $y(x,t) = A \cos(kx^2 - \omega t)$

The argument contains $x^2$, not a linear combination of $x$ and $t$ of the form $x \pm vt$. This already suggests it is not a standard traveling wave.

A direct check confirms this. Let

$$
\phi = kx^2 - \omega t
$$

Then

$$
\frac{\partial y}{\partial x} = -A \sin(\phi)\cdot 2kx
$$

and the second derivative with respect to $x$ contains terms proportional to both $\sin(\phi)$ and $\cos(\phi)$ with explicit factors of $x$. Meanwhile,

$$
\frac{\partial^2 y}{\partial t^2} = -A\omega^2 \cos(\phi)
$$

The two sides cannot be matched for all $x$ and $t$ by a single constant $v$.

Therefore, this function does not satisfy the wave equation.

### b) Function $y(x,t) = A(x-vt)^2$

This has the form

$$
y(x,t) = f(x-vt)
$$

with

$$
f(\xi) = A\xi^2
$$

Hence it should satisfy the wave equation. A direct check:

$$
\frac{\partial y}{\partial x} = 2A(x-vt)
$$

$$
\frac{\partial^2 y}{\partial x^2} = 2A
$$

Also,

$$
\frac{\partial y}{\partial t} = -2Av(x-vt)
$$

$$
\frac{\partial^2 y}{\partial t^2} = 2Av^2
$$

Then

$$
\frac{1}{v^2}\frac{\partial^2 y}{\partial t^2} = \frac{1}{v^2}(2Av^2) = 2A
$$

Thus,

$$
\frac{\partial^2 y}{\partial x^2} = \frac{1}{v^2}\frac{\partial^2 y}{\partial t^2}
$$

So this function does satisfy the wave equation.

### c) Function $y(x,t) = A \log(x+vt)$

This has the form

$$
y(x,t) = g(x+vt)
$$

with

$$
g(\eta) = A\log(\eta)
$$

Thus it should satisfy the wave equation wherever the logarithm is defined, that is, for

$$
x+vt > 0
$$

A direct check:

$$
\frac{\partial y}{\partial x} = \frac{A}{x+vt}
$$

$$
\frac{\partial^2 y}{\partial x^2} = -\frac{A}{(x+vt)^2}
$$

Also,

$$
\frac{\partial y}{\partial t} = \frac{Av}{x+vt}
$$

$$
\frac{\partial^2 y}{\partial t^2} = -\frac{Av^2}{(x+vt)^2}
$$

Therefore,

$$
\frac{1}{v^2}\frac{\partial^2 y}{\partial t^2} = -\frac{A}{(x+vt)^2}
$$

which is equal to $\partial^2 y/\partial x^2$.

So this function satisfies the wave equation on its domain.

## Final Result

The functions that describe traveling waves are:

$$
y(x,t) = A(x-vt)^2
$$

and

$$
y(x,t) = A \log(x+vt)
$$

The function

$$
y(x,t) = A \cos(kx^2 - \omega t)
$$

does not satisfy the wave equation.

## Interpretation

The essential feature of a one-dimensional traveling wave is dependence on the combination $x-vt$ or $x+vt$. The first function fails because its argument depends on $x^2$ rather than on a linear combination of space and time.

---
