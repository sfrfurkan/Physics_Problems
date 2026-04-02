# Task 08 – Work of a Variable Force for $F(x) = -kx$

## Problem Statement

Given the one-dimensional force

$$
F(x) = -kx
$$

perform the following tasks:

1. Write down the equation of motion and solve it.
2. Calculate the work done during the displacement from $0$ to $x_0$.
3. Interpret the result as potential energy.
4. Verify the relation

$$
F = -\frac{dU}{dx}
$$

5. Draw the graphs of $F(x)$ and $U(x)$.

## Theory

The force

$$
F(x) = -kx
$$

is the restoring force of a harmonic oscillator. According to Newton's second law,

$$
m\frac{d^2x}{dt^2} = -kx
$$

This leads to simple harmonic motion.

The work done by a force over a displacement is

$$
W = \int_{x_i}^{x_f} F(x)\,dx
$$

Potential energy is defined so that

$$
F(x) = -\frac{dU}{dx}
$$

## Step-by-Step Solution

### Equation of Motion

Newton's second law gives

$$
m\ddot{x} = -kx
$$

or

$$
\ddot{x} + \frac{k}{m}x = 0
$$

Define

$$
\omega = \sqrt{\frac{k}{m}}
$$

Then the equation becomes

$$
\ddot{x} + \omega^2 x = 0
$$

This is the standard harmonic oscillator equation.

### General Solution

The general solution is

$$
x(t) = A \cos(\omega t) + B \sin(\omega t)
$$

It may also be written as

$$
x(t) = C \cos(\omega t + \phi)
$$

where $A$, $B$, or equivalently $C$, $\phi$ are determined by initial conditions.

### Work Done from $0$ to $x_0$

The work done by the force is

$$
W_{0 \to x_0} = \int_0^{x_0} (-kx)\,dx
$$

Compute the integral:

$$
W_{0 \to x_0} = -k \int_0^{x_0} x\,dx
$$

$$
W_{0 \to x_0} = -k \left[\frac{x^2}{2}\right]_0^{x_0}
$$

$$
W_{0 \to x_0} = -\frac{1}{2}k x_0^2
$$

### Interpretation as Potential Energy

The change in potential energy is the negative of the work done by the force:

$$
\Delta U = -W
$$

If the reference point is chosen so that

$$
U(0) = 0
$$

then

$$
U(x_0) = \frac{1}{2}k x_0^2
$$

Hence the potential energy function is

$$
U(x) = \frac{1}{2}kx^2
$$

### Verification of $F = -dU/dx$

Differentiate the potential energy:

$$
\frac{dU}{dx} = \frac{d}{dx}\left(\frac{1}{2}kx^2\right)
$$

$$
\frac{dU}{dx} = kx
$$

Therefore,

$$
-\frac{dU}{dx} = -kx
$$

which agrees with the original force law:

$$
F(x) = -kx
$$

### Graphs of $F(x)$ and $U(x)$

The force is a straight line through the origin with negative slope:

$$
F(x) = -kx
$$

The potential energy is an upward-opening parabola:

$$
U(x) = \frac{1}{2}kx^2
$$

A simple schematic representation is:

#### Force graph

$$
\begin{align}
x > 0 &\Rightarrow F(x) < 0 \\
x = 0 &\Rightarrow F(x) = 0 \\
x < 0 &\Rightarrow F(x) > 0
\end{align}
$$

#### Potential graph

$$
U(x) \ge 0
$$

with minimum at

$$
x = 0
$$

## Final Result

The equation of motion is

$$
m\ddot{x} + kx = 0
$$

Its general solution is

$$
x(t) = A \cos\left(\sqrt{\frac{k}{m}}\,t\right) + B \sin\left(\sqrt{\frac{k}{m}}\,t\right)
$$

The work done by the force from $0$ to $x_0$ is

$$
W_{0 \to x_0} = -\frac{1}{2}k x_0^2
$$

The corresponding potential energy is

$$
U(x) = \frac{1}{2}kx^2
$$

and it satisfies

$$
F(x) = -\frac{dU}{dx}
$$

## Interpretation

The force always points toward the equilibrium position $x = 0$, which is why it is called a restoring force. The potential energy has its minimum at the equilibrium point, so the particle oscillates around this minimum. This is the central model of simple harmonic motion.
