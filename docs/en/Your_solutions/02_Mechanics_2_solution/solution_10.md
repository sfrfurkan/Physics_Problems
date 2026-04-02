
FILE: task_10.md

```markdown
# Task 10 – Force Field and Power from a Given Trajectory

## Problem Statement

A particle of mass

$$
m = 0.5 \text{ kg}
$$

moves according to

$$
x(t) = 5t^2 - t
$$

$$
y(t) = 2t^3
$$

$$
z(t) = -3t + 2
$$

Determine the time dependence of:

1. the velocity,
2. the momentum,
3. the acceleration,
4. the force,
5. the power transferred by the field.

## Theory

For a position vector

$$
\vec{r}(t) = \bigl(x(t), y(t), z(t)\bigr)
$$

the main kinematic and dynamic quantities are:

- velocity

$$
\vec{v}(t) = \frac{d\vec{r}}{dt}
$$

- acceleration

$$
\vec{a}(t) = \frac{d\vec{v}}{dt}
$$

- momentum

$$
\vec{p}(t) = m\vec{v}(t)
$$

- force

$$
\vec{F}(t) = m\vec{a}(t)
$$

- instantaneous power

$$
P(t) = \vec{F}(t) \cdot \vec{v}(t)
$$

## Step-by-Step Solution

### Position Vector

The trajectory is

$$
\vec{r}(t) = \bigl(5t^2 - t,\; 2t^3,\; -3t + 2\bigr)
$$

### Velocity

Differentiate each coordinate with respect to time:

$$
v_x(t) = \frac{d}{dt}(5t^2 - t) = 10t - 1
$$

$$
v_y(t) = \frac{d}{dt}(2t^3) = 6t^2
$$

$$
v_z(t) = \frac{d}{dt}(-3t + 2) = -3
$$

Thus,

$$
\vec{v}(t) = (10t - 1,\; 6t^2,\; -3)
$$

### Momentum

Since $m = 0.5 \text{ kg}$,

$$
\vec{p}(t) = 0.5 \vec{v}(t)
$$

Therefore,

$$
\vec{p}(t) = \left(5t - 0.5,\; 3t^2,\; -1.5\right)
$$

### Acceleration

Differentiate the velocity components:

$$
a_x(t) = \frac{d}{dt}(10t - 1) = 10
$$

$$
a_y(t) = \frac{d}{dt}(6t^2) = 12t
$$

$$
a_z(t) = \frac{d}{dt}(-3) = 0
$$

Thus,

$$
\vec{a}(t) = (10,\; 12t,\; 0)
$$

### Force

Using

$$
\vec{F}(t) = m\vec{a}(t)
$$

gives

$$
\vec{F}(t) = 0.5(10,\; 12t,\; 0)
$$

Hence,

$$
\vec{F}(t) = (5,\; 6t,\; 0)
$$

### Power

The power is the dot product

$$
P(t) = \vec{F}(t) \cdot \vec{v}(t)
$$

Substitute the expressions:

$$
P(t) = (5,\; 6t,\; 0)\cdot(10t - 1,\; 6t^2,\; -3)
$$

Compute term by term:

$$
P(t) = 5(10t - 1) + 6t(6t^2) + 0(-3)
$$

$$
P(t) = 50t - 5 + 36t^3
$$

Thus,

$$
P(t) = 36t^3 + 50t - 5
$$

## Final Result

The velocity is

$$
\vec{v}(t) = (10t - 1,\; 6t^2,\; -3)
$$

The momentum is

$$
\vec{p}(t) = \left(5t - 0.5,\; 3t^2,\; -1.5\right)
$$

The acceleration is

$$
\vec{a}(t) = (10,\; 12t,\; 0)
$$

The force is

$$
\vec{F}(t) = (5,\; 6t,\; 0)
$$

The power is

$$
P(t) = 36t^3 + 50t - 5
$$

## Interpretation

The motion is non-uniform because the acceleration is not zero. The force changes with time through its $y$-component, while the $x$-component remains constant. The power also varies with time, meaning that the rate at which the force field transfers energy to the particle is not constant.
