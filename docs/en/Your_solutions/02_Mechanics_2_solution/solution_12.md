# Task 12 – Work and Energy with a Constant Force

## Problem Statement

A constant force acts on a body of mass

$$
m = 2 \text{ kg}
$$

with

$$
\vec{F} = (6,\; 2) \text{ N}
$$

The body starts with initial velocity

$$
\vec{v}(0) = (1,\; -1) \text{ m/s}
$$

from the point

$$
\vec{r}(0) = (0,\; 0) \text{ m}
$$

Determine:

1. $\vec{a}(t)$,
2. $\vec{v}(t)$,
3. $\vec{r}(t)$,
4. the trajectory,
5. the work done by the force at $t = 3 \text{ s}$,
6. the consistency with the work-energy theorem.

## Theory

For a constant force,

$$
\vec{a} = \frac{\vec{F}}{m}
$$

Then

$$
\vec{v}(t) = \vec{v}_0 + \vec{a}t
$$

and

$$
\vec{r}(t) = \vec{r}_0 + \vec{v}_0 t + \frac{1}{2}\vec{a}t^2
$$

The work done by a constant force over displacement $\Delta \vec{r}$ is

$$
W = \vec{F} \cdot \Delta \vec{r}
$$

The work-energy theorem states

$$
W = \Delta K
$$

## Step-by-Step Solution

### Acceleration

Given

$$
\vec{F} = (6,\; 2) \text{ N}
$$

and

$$
m = 2 \text{ kg}
$$

the acceleration is

$$
\vec{a} = \frac{\vec{F}}{m} = \left(\frac{6}{2},\; \frac{2}{2}\right)
$$

Thus,

$$
\vec{a}(t) = (3,\; 1) \text{ m/s}^2
$$

This is constant in time.

### Velocity

Using

$$
\vec{v}(t) = \vec{v}_0 + \vec{a}t
$$

with

$$
\vec{v}_0 = (1,\; -1)
$$

gives

$$
\vec{v}(t) = (1,\; -1) + (3,\; 1)t
$$

Therefore,

$$
\vec{v}(t) = (1 + 3t,\; -1 + t)
$$

### Position

Using

$$
\vec{r}(t) = \vec{r}_0 + \vec{v}_0 t + \frac{1}{2}\vec{a}t^2
$$

with $\vec{r}_0 = (0,\; 0)$:

$$
\vec{r}(t) = (1,\; -1)t + \frac{1}{2}(3,\; 1)t^2
$$

Thus,

$$
\vec{r}(t) = \left(t + \frac{3}{2}t^2,\; -t + \frac{1}{2}t^2\right)
$$

So the coordinate equations are

$$
x(t) = t + \frac{3}{2}t^2
$$

$$
y(t) = -t + \frac{1}{2}t^2
$$

### Trajectory

To eliminate $t$, use the equation for $x$:

$$
x = t + \frac{3}{2}t^2
$$

This is a quadratic relation between $x$ and $t$, so the trajectory in the plane is a parabola. A fully explicit expression $y(x)$ can be obtained by solving the quadratic for $t$, but the parametric form is usually the cleanest representation:

$$
\begin{cases}
x(t) = t + \frac{3}{2}t^2 \\
y(t) = -t + \frac{1}{2}t^2
\end{cases}
$$

### Work Done by the Force at $t = 3 \text{ s}$

First compute the displacement from $t = 0$ to $t = 3$:

$$
\vec{r}(3) = \left(3 + \frac{3}{2}\cdot 9,\; -3 + \frac{1}{2}\cdot 9\right)
$$

$$
\vec{r}(3) = (3 + 13.5,\; -3 + 4.5)
$$

$$
\vec{r}(3) = (16.5,\; 1.5)
$$

Since $\vec{r}(0) = (0,0)$, the displacement is

$$
\Delta \vec{r} = (16.5,\; 1.5)
$$

The work is

$$
W = \vec{F} \cdot \Delta \vec{r}
$$

$$
W = (6,\; 2)\cdot(16.5,\; 1.5)
$$

$$
W = 6 \cdot 16.5 + 2 \cdot 1.5
$$

$$
W = 99 + 3 = 102 \text{ J}
$$

### Check with the Work-Energy Theorem

Initial kinetic energy:

$$
K_0 = \frac{1}{2}m v_0^2
$$

The initial speed magnitude satisfies

$$
v_0^2 = 1^2 + (-1)^2 = 2
$$

Thus,

$$
K_0 = \frac{1}{2}\cdot 2 \cdot 2 = 2 \text{ J}
$$

Now compute the velocity at $t = 3$:

$$
\vec{v}(3) = (1 + 3\cdot 3,\; -1 + 3) = (10,\; 2)
$$

Therefore,

$$
v(3)^2 = 10^2 + 2^2 = 104
$$

Final kinetic energy:

$$
K_3 = \frac{1}{2} \cdot 2 \cdot 104 = 104 \text{ J}
$$

Hence,

$$
\Delta K = K_3 - K_0 = 104 - 2 = 102 \text{ J}
$$

This matches the work found above:

$$
W = \Delta K = 102 \text{ J}
$$

## Final Result

The acceleration is

$$
\vec{a}(t) = (3,\; 1) \text{ m/s}^2
$$

The velocity is

$$
\vec{v}(t) = (1 + 3t,\; -1 + t)
$$

The position is

$$
\vec{r}(t) = \left(t + \frac{3}{2}t^2,\; -t + \frac{1}{2}t^2\right)
$$

The trajectory is a parabola given parametrically by

$$
\begin{cases}
x(t) = t + \frac{3}{2}t^2 \\
y(t) = -t + \frac{1}{2}t^2
\end{cases}
$$

The work done by the force up to $t = 3 \text{ s}$ is

$$
W = 102 \text{ J}
$$

The work-energy theorem is satisfied:

$$
W = \Delta K = 102 \text{ J}
$$

## Interpretation

A constant force produces constant acceleration, so the motion is uniformly accelerated in each coordinate direction. Because the acceleration vector is not parallel to the initial velocity, the path is curved rather than straight. The equality between work and kinetic energy change confirms the consistency of the solution.
