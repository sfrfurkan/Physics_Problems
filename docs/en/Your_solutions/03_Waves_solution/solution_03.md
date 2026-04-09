# Task 03 – Superposition Principle

## Problem Statement

Two waves are given by

$$
y_1(x,t) = A \sin(kx - \omega t)
$$

and

$$
y_2(x,t) = A \sin(kx + \omega t)
$$

Find the equation of the resulting standing wave and identify the node positions.

## Theory

The superposition principle states that the resultant displacement is the sum of the individual displacements:

$$
y(x,t) = y_1(x,t) + y_2(x,t)
$$

A useful trigonometric identity is

$$
\sin \alpha + \sin \beta = 2 \sin \left( \frac{\alpha+\beta}{2} \right)\cos \left( \frac{\alpha-\beta}{2} \right)
$$

## Step-by-Step Solution

Add the two waves:

$$
y(x,t) = A \sin(kx - \omega t) + A \sin(kx + \omega t)
$$

Factor out $A$:

$$
y(x,t) = A \left[\sin(kx - \omega t) + \sin(kx + \omega t)\right]
$$

Using the identity with

$$
\alpha = kx - \omega t
$$

and

$$
\beta = kx + \omega t
$$

gives

$$
y(x,t) = 2A \sin(kx)\cos(\omega t)
$$

This is the equation of a standing wave.

Nodes are points where the displacement is always zero for all time, so the spatial factor must vanish:

$$
\sin(kx) = 0
$$

Thus,

$$
kx = n\pi
$$

where $n = 0,1,2,\dots$

Since

$$
k = \frac{2\pi}{\lambda}
$$

the node positions are

$$
x_n = \frac{n\pi}{k} = \frac{n\lambda}{2}
$$

## Final Result

The standing wave is

$$
y(x,t) = 2A \sin(kx)\cos(\omega t)
$$

The nodes are located at

$$
x_n = \frac{n\lambda}{2}
$$

for $n = 0,1,2,\dots$

## Interpretation

The two traveling waves have the same amplitude and frequency but move in opposite directions. Their interference produces a standing wave with fixed nodes and oscillating antinodes.

---
