# Task 09 – Vector Lorentz Force on a Proton

## Problem Statement

A proton moves with velocity

$$
\vec{v} = (2\hat{i} - 4\hat{j} + \hat{k})\,\mathrm{m/s}
$$

in a region where the magnetic field is

$$
\vec{B} = (\hat{i} + 2\hat{j} - \hat{k})\,\mathrm{T}
$$

Find the magnitude of the magnetic force experienced by the proton.

## Theory

The magnetic force on a charged particle is

$$
\vec{F} = q\,\vec{v} \times \vec{B}
$$

Thus the magnitude is

$$
|\vec{F}| = q\,|\vec{v} \times \vec{B}|
$$

For a proton,

$$
q = e = 1.60 \times 10^{-19}\,\mathrm{C}
$$

## Step-by-Step Solution

### Compute the Cross Product

Write the determinant:

$$
\vec{v} \times \vec{B}
=
\begin{vmatrix}
\hat{i} & \hat{j} & \hat{k} \\
2 & -4 & 1 \\
1 & 2 & -1
\end{vmatrix}
$$

Expand:

$$
\vec{v} \times \vec{B}
=
\hat{i}\left[(-4)(-1) - (1)(2)\right]
-
\hat{j}\left[(2)(-1) - (1)(1)\right]
+
\hat{k}\left[(2)(2) - (-4)(1)\right]
$$

$$
\vec{v} \times \vec{B}
=
\hat{i}(4-2)
-
\hat{j}(-2-1)
+
\hat{k}(4+4)
$$

$$
\vec{v} \times \vec{B}
=
2\hat{i} + 3\hat{j} + 8\hat{k}
$$

### Magnitude of the Cross Product

$$
|\vec{v} \times \vec{B}| =
\sqrt{2^2 + 3^2 + 8^2}
$$

$$
|\vec{v} \times \vec{B}| =
\sqrt{4+9+64}
= \sqrt{77}
$$

### Magnetic Force Magnitude

$$
|\vec{F}| = e\sqrt{77}
$$

Substitute $e = 1.60 \times 10^{-19}\,\mathrm{C}$:

$$
|\vec{F}| \approx 1.40 \times 10^{-18}\,\mathrm{N}
$$

## Final Result

$$
|\vec{F}| \approx 1.41 \times 10^{-18}\,\mathrm{N}
$$

## Interpretation

The force depends on the component of velocity perpendicular to the magnetic field, captured by the cross product. The result is extremely small because the proton charge is very small and the given speed is only a few meters per second.
