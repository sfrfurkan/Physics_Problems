# Task 01 – Vector Algebra

## Problem Statement

Given two vectors in 3D space:

$$
\vec{a} = \begin{pmatrix} 2 \\ 1 \\ -3 \end{pmatrix}
$$

and

$$
\vec{b} = \begin{pmatrix} 4 \\ -2 \\ 1 \end{pmatrix}
$$

Determine:

1. the magnitude of each vector,
2. the dot product $\vec{a} \cdot \vec{b}$,
3. the cross product $\vec{a} \times \vec{b}$,
4. the angle between $\vec{a}$ and $\vec{b}$.

## Theory

For a vector $\vec{v} = (v_x, v_y, v_z)$, the magnitude is

$$
|\vec{v}| = \sqrt{v_x^2 + v_y^2 + v_z^2}
$$

The dot product of two vectors is

$$
\vec{a} \cdot \vec{b} = a_x b_x + a_y b_y + a_z b_z
$$

It is also related to the angle $\theta$ between the vectors by

$$
\vec{a} \cdot \vec{b} = |\vec{a}| |\vec{b}| \cos\theta
$$

The cross product in component form is

$$
\vec{a} \times \vec{b} =
\begin{pmatrix}
a_y b_z - a_z b_y \\
a_z b_x - a_x b_z \\
a_x b_y - a_y b_x
\end{pmatrix}
$$

## Step-by-Step Solution

### 1. Magnitude of $\vec{a}$

For $\vec{a} = (2,1,-3)$,

$$
|\vec{a}| = \sqrt{2^2 + 1^2 + (-3)^2}
$$

$$
|\vec{a}| = \sqrt{4 + 1 + 9}
$$

$$
|\vec{a}| = \sqrt{14}
$$

### 2. Magnitude of $\vec{b}$

For $\vec{b} = (4,-2,1)$,

$$
|\vec{b}| = \sqrt{4^2 + (-2)^2 + 1^2}
$$

$$
|\vec{b}| = \sqrt{16 + 4 + 1}
$$

$$
|\vec{b}| = \sqrt{21}
$$

### 3. Dot product

Using the component formula,

$$
\vec{a} \cdot \vec{b} = (2)(4) + (1)(-2) + (-3)(1)
$$

$$
\vec{a} \cdot \vec{b} = 8 - 2 - 3
$$

$$
\vec{a} \cdot \vec{b} = 3
$$

### 4. Cross product

Using

$$
\vec{a} \times \vec{b} =
\begin{pmatrix}
a_y b_z - a_z b_y \\
a_z b_x - a_x b_z \\
a_x b_y - a_y b_x
\end{pmatrix}
$$

Substitute the components:

$$
\vec{a} \times \vec{b} =
\begin{pmatrix}
(1)(1) - (-3)(-2) \\
(-3)(4) - (2)(1) \\
(2)(-2) - (1)(4)
\end{pmatrix}
$$

$$
\vec{a} \times \vec{b} =
\begin{pmatrix}
1 - 6 \\
-12 - 2 \\
-4 - 4
\end{pmatrix}
$$

$$
\vec{a} \times \vec{b} =
\begin{pmatrix}
-5 \\
-14 \\
-8
\end{pmatrix}
$$

### 5. Angle between the vectors

Use the relation

$$
\cos\theta = \frac{\vec{a} \cdot \vec{b}}{|\vec{a}| |\vec{b}|}
$$

Substitute the values:

$$
\cos\theta = \frac{3}{\sqrt{14}\sqrt{21}}
$$

$$
\cos\theta = \frac{3}{\sqrt{294}}
$$

Therefore,

$$
\theta = \cos^{-1}\left(\frac{3}{\sqrt{294}}\right)
$$

Numerically,

$$
\theta \approx 79.9^\circ
$$

## Final Result

The results are

$$
|\vec{a}| = \sqrt{14}
$$

$$
|\vec{b}| = \sqrt{21}
$$

$$
\vec{a} \cdot \vec{b} = 3
$$

$$
\vec{a} \times \vec{b} =
\begin{pmatrix}
-5 \\
-14 \\
-8
\end{pmatrix}
$$

$$
\theta = \cos^{-1}\left(\frac{3}{\sqrt{294}}\right) \approx 79.9^\circ
$$

## Interpretation

The dot product is positive, so the angle between the vectors is less than $90^\circ$. Since the dot product is small compared with the product of the magnitudes, the vectors are close to perpendicular, but not exactly orthogonal. The nonzero cross product confirms that the vectors are not parallel.

---
