# Task 11 – Dynamics with a Time-Dependent Force

## Problem Statement

A particle of mass

$$
m = 3 \text{ kg}
$$

moves under the time-dependent force

$$
\vec{F}(t) = (15t,\; 3t - 12,\; -6t^2) \text{ N}
$$

with initial conditions

$$
\vec{r}(0) = (5,\; 2,\; -3) \text{ m}
$$

$$
\vec{v}(0) = (2,\; 0,\; 1) \text{ m/s}
$$

Determine the position vector $\vec{r}(t)$ and the velocity vector $\vec{v}(t)$.

## Theory

Newton's second law in vector form is

$$
\vec{F}(t) = m\vec{a}(t)
$$

Hence,

$$
\vec{a}(t) = \frac{\vec{F}(t)}{m}
$$

The velocity is obtained by integrating acceleration:

$$
\vec{v}(t) = \vec{v}(0) + \int_0^t \vec{a}(s)\,ds
$$

The position is obtained by integrating velocity:

$$
\vec{r}(t) = \vec{r}(0) + \int_0^t \vec{v}(s)\,ds
$$

## Step-by-Step Solution

### Acceleration

Since $m = 3 \text{ kg}$,

$$
\vec{a}(t) = \frac{1}{3}(15t,\; 3t - 12,\; -6t^2)
$$

Thus,

$$
\vec{a}(t) = (5t,\; t - 4,\; -2t^2)
$$

### Velocity

Integrate each component and apply the initial condition.

#### $x$-component

$$
a_x(t) = 5t
$$

Integrate:

$$
v_x(t) = \int 5t\,dt = \frac{5}{2}t^2 + C_x
$$

Since $v_x(0) = 2$,

$$
C_x = 2
$$

Thus,

$$
v_x(t) = \frac{5}{2}t^2 + 2
$$

#### $y$-component

$$
a_y(t) = t - 4
$$

Integrate:

$$
v_y(t) = \int (t - 4)\,dt = \frac{1}{2}t^2 - 4t + C_y
$$

Since $v_y(0) = 0$,

$$
C_y = 0
$$

Thus,

$$
v_y(t) = \frac{1}{2}t^2 - 4t
$$

#### $z$-component

$$
a_z(t) = -2t^2
$$

Integrate:

$$
v_z(t) = \int -2t^2\,dt = -\frac{2}{3}t^3 + C_z
$$

Since $v_z(0) = 1$,

$$
C_z = 1
$$

Thus,

$$
v_z(t) = 1 - \frac{2}{3}t^3
$$

Therefore,

$$
\vec{v}(t) = \left(\frac{5}{2}t^2 + 2,\; \frac{1}{2}t^2 - 4t,\; 1 - \frac{2}{3}t^3\right)
$$

### Position

Integrate the velocity components and apply the initial position.

#### $x$-component

$$
x(t) = \int \left(\frac{5}{2}t^2 + 2\right)dt
$$

$$
x(t) = \frac{5}{6}t^3 + 2t + C_1
$$

Since $x(0) = 5$,

$$
C_1 = 5
$$

Thus,

$$
x(t) = \frac{5}{6}t^3 + 2t + 5
$$

#### $y$-component

$$
y(t) = \int \left(\frac{1}{2}t^2 - 4t\right)dt
$$

$$
y(t) = \frac{1}{6}t^3 - 2t^2 + C_2
$$

Since $y(0) = 2$,

$$
C_2 = 2
$$

Thus,

$$
y(t) = \frac{1}{6}t^3 - 2t^2 + 2
$$

#### $z$-component

$$
z(t) = \int \left(1 - \frac{2}{3}t^3\right)dt
$$

$$
z(t) = t - \frac{1}{6}t^4 + C_3
$$

Since $z(0) = -3$,

$$
C_3 = -3
$$

Thus,

$$
z(t) = t - \frac{1}{6}t^4 - 3
$$

Hence,

$$
\vec{r}(t) = \left(\frac{5}{6}t^3 + 2t + 5,\; \frac{1}{6}t^3 - 2t^2 + 2,\; t - \frac{1}{6}t^4 - 3\right)
$$

## Final Result

The velocity is

$$
\vec{v}(t) = \left(\frac{5}{2}t^2 + 2,\; \frac{1}{2}t^2 - 4t,\; 1 - \frac{2}{3}t^3\right)
$$

The position is

$$
\vec{r}(t) = \left(\frac{5}{6}t^3 + 2t + 5,\; \frac{1}{6}t^3 - 2t^2 + 2,\; t - \frac{1}{6}t^4 - 3\right)
$$

## Interpretation

Because the force depends explicitly on time, the acceleration is also time-dependent. Integrating once gives a polynomial velocity, and integrating again gives a polynomial position. This is a standard example of motion under a prescribed non-constant force.
