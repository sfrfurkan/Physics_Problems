# Task 01 – Projectile Motion

## Problem Statement

A projectile is fired with initial velocity $v_0 = 100 \text{ m/s}$ at angle $\theta = 37^\circ$. No air resistance.

Determine:
- equations of motion
- time of flight
- maximum height
- range

---

## Theory

Projectile motion decomposes into:

- Horizontal: constant velocity
- Vertical: constant acceleration $-g$

$$
\vec{a} = (0, -g)
$$

---

## Step-by-Step Solution

### Decomposition of velocity

$$
v_{0x} = v_0 \cos \theta, \quad v_{0y} = v_0 \sin \theta
$$

Using $\cos 37^\circ \approx 0.8$, $\sin 37^\circ \approx 0.6$:

$$
v_{0x} = 80 \text{ m/s}, \quad v_{0y} = 60 \text{ m/s}
$$

---

### Differential equations

$$
\frac{d^2 x}{dt^2} = 0
$$

$$
\frac{d^2 y}{dt^2} = -g
$$

---

### Time of flight

$$
T = \frac{2 v_{0y}}{g} = \frac{2 \cdot 60}{9.8} \approx 12.24 \text{ s}
$$

---

### Maximum height

$$
H = \frac{v_{0y}^2}{2g} = \frac{60^2}{2 \cdot 9.8} \approx 183.7 \text{ m}
$$

---

### Range

$$
R = v_{0x} \cdot T = 80 \cdot 12.24 \approx 979.2 \text{ m}
$$

---

## Final Result

- Time: $12.24 \text{ s}$
- Height: $183.7 \text{ m}$
- Range: $979.2 \text{ m}$

---

## Interpretation

Horizontal and vertical motions are independent. Gravity only affects vertical motion.
