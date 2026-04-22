# Task 03 – Biot–Savart Law for a Short Current Segment

## Problem Statement

A small segment of a line wire of length $0.1\ \mathrm{m}$ carries a current of $3\ \mathrm{A}$. The segment is located at a distance of $0.2\ \mathrm{m}$ from a point $P$. Calculate the magnetic field at point $P$ due to this current segment, assuming the segment is perpendicular to the line connecting it to point $P$.

## Theory

For a small current element, the Biot–Savart law gives the magnetic field magnitude as

$$
dB = \frac{\mu_0}{4\pi} \frac{I \, d\ell \sin\theta}{r^2}
$$

where:

- $\mu_0 = 4\pi \times 10^{-7}\ \mathrm{T \cdot m/A}$
- $I$ is the current
- $d\ell$ is the length of the small segment
- $r$ is the distance from the segment to the observation point
- $\theta$ is the angle between the current segment and the line from the segment to the point

Because the segment is perpendicular to the line connecting it to point $P$,

$$
\theta = 90^\circ
$$

and therefore

$$
\sin\theta = 1
$$

## Step-by-Step Solution

Given:

$$
I = 3\ \mathrm{A}
$$

$$
d\ell = 0.1\ \mathrm{m}
$$

$$
r = 0.2\ \mathrm{m}
$$

Using the Biot–Savart law,

$$
dB = \frac{\mu_0}{4\pi} \frac{I \, d\ell}{r^2}
$$

Substituting the values,

$$
dB = 10^{-7} \cdot \frac{(3)(0.1)}{(0.2)^2}
$$

First compute the denominator:

$$
(0.2)^2 = 0.04
$$

Then the numerator:

$$
(3)(0.1) = 0.3
$$

So,

$$
dB = 10^{-7} \cdot \frac{0.3}{0.04}
$$

$$
dB = 10^{-7} \cdot 7.5
$$

$$
dB = 7.5 \times 10^{-7}\ \mathrm{T}
$$

The direction is found from the right-hand rule: it is perpendicular to both the current direction and the position vector from the segment to point $P$.

## Final Result

$$
B = 7.5 \times 10^{-7}\ \mathrm{T}
$$

Direction: given by the right-hand rule.

## Interpretation

The magnetic field produced by a short current segment is much smaller than the field produced by an infinite wire because only a finite portion of current contributes. The field decreases with the square of the distance, so increasing the observation distance rapidly weakens the magnetic effect.
