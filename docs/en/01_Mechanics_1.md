# Task 01 – Projectile Motion

## Problem Statement

A projectile is fired from the ground with initial speed $v_0 = 100 \text{ m/s}$ at angle $\theta = 37^\circ$ above the horizontal. Air resistance is neglected.

Required:

- derive the differential equations of motion in the horizontal and vertical directions,
- determine the time of flight,
- determine the maximum height,
- determine the range.

## Theory

For ideal projectile motion, the only force acting on the projectile is gravity. Therefore the acceleration is constant and directed downward.

Using Cartesian coordinates:

- $x$ is the horizontal coordinate,
- $y$ is the vertical coordinate.

The acceleration vector is

$$
\vec a = (0,-g)
$$

with $g \approx 9.81 \text{ m/s}^2$.

The initial velocity components are

$$
v_{0x} = v_0 \cos\theta
$$

and

$$
v_{0y} = v_0 \sin\theta
$$

The position functions are obtained by integrating the acceleration.

## Step-by-Step Solution

### 1. Differential equations of motion

In the horizontal direction no force acts, so

$$
m \ddot x = 0
$$

Hence

$$
\ddot x = 0
$$

In the vertical direction gravity acts downward, so

$$
m \ddot y = -mg
$$

Hence

$$
\ddot y = -g
$$

These are the differential equations of motion.

---

### 2. Velocity functions

Integrating once gives the velocity components:

$$
\dot x(t) = v_{0x} = v_0 \cos\theta
$$

$$
\dot y(t) = v_{0y} - gt = v_0 \sin\theta - gt
$$

With $v_0 = 100$ and $\theta = 37^\circ$,

$$
v_{0x} = 100 \cos 37^\circ \approx 79.86 \text{ m/s}
$$

$$
v_{0y} = 100 \sin 37^\circ \approx 60.18 \text{ m/s}
$$

---

### 3. Position functions

Assuming the projectile starts from the origin,

$$
x(0)=0, \qquad y(0)=0
$$

Integrating again gives

$$
x(t) = v_0 \cos\theta \, t
$$

$$
y(t) = v_0 \sin\theta \, t - \frac{1}{2}gt^2
$$

So here

$$
x(t) = 100 \cos 37^\circ \, t
$$

$$
y(t) = 100 \sin 37^\circ \, t - \frac{1}{2}(9.81)t^2
$$

---

### 4. Time of flight

The projectile returns to the ground when $y(t)=0$.

Thus

$$
v_0 \sin\theta \, t - \frac{1}{2}gt^2 = 0
$$

Factor out $t$:

$$
t \left( v_0 \sin\theta - \frac{1}{2}gt \right)=0
$$

One solution is $t=0$, the launch instant. The nontrivial solution is

$$
t_f = \frac{2v_0 \sin\theta}{g}
$$

Substituting the values:

$$
t_f = \frac{2(100)\sin 37^\circ}{9.81}
$$

$$
t_f \approx \frac{200(0.6018)}{9.81}
\approx 12.27 \text{ s}
$$

---

### 5. Maximum height

At the highest point the vertical velocity is zero:

$$
\dot y(t) = v_0 \sin\theta - gt = 0
$$

Thus the time to reach the highest point is

$$
t_h = \frac{v_0 \sin\theta}{g}
$$

Substituting into $y(t)$ gives the maximum height:

$$
H_{\max} = v_0 \sin\theta \left( \frac{v_0 \sin\theta}{g} \right) - \frac{1}{2}g \left( \frac{v_0 \sin\theta}{g} \right)^2
$$

After simplification,

$$
H_{\max} = \frac{v_0^2 \sin^2\theta}{2g}
$$

Now substitute the data:

$$
H_{\max} = \frac{100^2 \sin^2 37^\circ}{2(9.81)}
$$

$$
H_{\max} \approx \frac{10000(0.6018)^2}{19.62}
\approx 1846 \text{ m}
$$

---

### 6. Range

The range is the horizontal distance traveled during the total flight time:

$$
R = x(t_f)
$$

Therefore

$$
R = v_0 \cos\theta \cdot \frac{2v_0 \sin\theta}{g}
$$

Using $2\sin\theta\cos\theta = \sin 2\theta$:

$$
R = \frac{v_0^2 \sin 2\theta}{g}
$$

Substituting the values:

$$
R = \frac{100^2 \sin 74^\circ}{9.81}
$$

$$
R \approx \frac{10000(0.9613)}{9.81}
\approx 9799 \text{ m}
$$

## Final Result

The differential equations of motion are

$$
\ddot x = 0, \qquad \ddot y = -g
$$

The time of flight is

$$
t_f \approx 12.27 \text{ s}
$$

The maximum height is

$$
H_{\max} \approx 1.85 \times 10^3 \text{ m}
$$

The range is

$$
R \approx 9.80 \times 10^3 \text{ m}
$$

## Interpretation

The horizontal motion is uniform because there is no horizontal acceleration. The vertical motion is uniformly accelerated downward due to gravity. The trajectory is a parabola. A large initial speed combined with a moderate launch angle produces both a long flight time and a large range.
