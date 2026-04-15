# Task 06 – Electric Field of Two Charges

## Problem Statement

Two point charges are located at

- $+q$ at $(-a,0)$
- $+2q$ at $(a,0)$

Determine:

1. the field vector $\vec{E}(0,y)$
2. the field vector $\vec{E}(x,0)$
3. the general field vector $\vec{E}(x,y)$
4. the conditions for $E_x = 0$, $E_y = 0$, and $\vec{E} = 0$
5. the numerical value for

$$
a = 0.2\,\mathrm{m}, \quad y = 0.3\,\mathrm{m}, \quad q = 2\,\mu\mathrm{C}
$$

6. the limit $y \gg a$

## Theory

For a point charge $Q$ located at $\vec{r}_0$, the electric field at $\vec{r}$ is

$$
\vec{E}(\vec{r}) = kQ \frac{\vec{r}-\vec{r}_0}{|\vec{r}-\vec{r}_0|^3}
$$

The total field is the vector sum of the fields from both charges.

## Step-by-Step Solution

### General Expression for $\vec{E}(x,y)$

For the charge $+q$ at $(-a,0)$, the displacement vector to the point $(x,y)$ is

$$
\vec{r}_1 = (x+a)\,\hat{i} + y\,\hat{j}
$$

with magnitude

$$
r_1 = \sqrt{(x+a)^2 + y^2}
$$

For the charge $+2q$ at $(a,0)$, the displacement vector is

$$
\vec{r}_2 = (x-a)\,\hat{i} + y\,\hat{j}
$$

with magnitude

$$
r_2 = \sqrt{(x-a)^2 + y^2}
$$

Therefore,

$$
\vec{E}(x,y) =
kq \frac{(x+a)\,\hat{i} + y\,\hat{j}}{\left[(x+a)^2+y^2\right]^{3/2}}
+
k(2q) \frac{(x-a)\,\hat{i} + y\,\hat{j}}{\left[(x-a)^2+y^2\right]^{3/2}}
$$

Hence the components are

$$
E_x =
kq \frac{x+a}{\left[(x+a)^2+y^2\right]^{3/2}}
+
2kq \frac{x-a}{\left[(x-a)^2+y^2\right]^{3/2}}
$$

$$
E_y =
kq \frac{y}{\left[(x+a)^2+y^2\right]^{3/2}}
+
2kq \frac{y}{\left[(x-a)^2+y^2\right]^{3/2}}
$$

### Field on the $y$-Axis: $\vec{E}(0,y)$

Set $x=0$. Then both distances are equal:

$$
R = \sqrt{a^2+y^2}
$$

Thus

$$
\vec{E}(0,y) =
kq \frac{a\,\hat{i} + y\,\hat{j}}{R^3}
+
2kq \frac{-a\,\hat{i} + y\,\hat{j}}{R^3}
$$

Combine terms:

$$
\vec{E}(0,y) =
\frac{kq}{R^3}
\left[
(a-2a)\hat{i} + (y+2y)\hat{j}
\right]
$$

$$
\vec{E}(0,y) =
\frac{kq}{(a^2+y^2)^{3/2}}
\left(
-a\,\hat{i} + 3y\,\hat{j}
\right)
$$

Therefore,

$$
E_x(0,y) = -\,\frac{kqa}{(a^2+y^2)^{3/2}}
$$

$$
E_y(0,y) = \frac{3kqy}{(a^2+y^2)^{3/2}}
$$

### Field on the $x$-Axis: $\vec{E}(x,0)$

Set $y=0$. Then the field is purely horizontal:

$$
E_y(x,0)=0
$$

and

$$
E_x(x,0) =
kq \frac{x+a}{|x+a|^3}
+
2kq \frac{x-a}{|x-a|^3}
$$

So

$$
\vec{E}(x,0)=
\left[
kq \frac{x+a}{|x+a|^3}
+
2kq \frac{x-a}{|x-a|^3}
\right]\hat{i}
$$

### Condition for $E_y = 0$

From the general expression,

$$
E_y =
kq\,y\left[
\frac{1}{\left[(x+a)^2+y^2\right]^{3/2}}
+
\frac{2}{\left[(x-a)^2+y^2\right]^{3/2}}
\right]
$$

The bracket is always positive, so

$$
E_y = 0 \quad \Longrightarrow \quad y = 0
$$

Thus the field can be horizontal only on the $x$-axis.

### Condition for $E_x = 0$

Set

$$
kq \frac{x+a}{\left[(x+a)^2+y^2\right]^{3/2}}
+
2kq \frac{x-a}{\left[(x-a)^2+y^2\right]^{3/2}} = 0
$$

Cancel $kq$:

$$
\frac{x+a}{\left[(x+a)^2+y^2\right]^{3/2}}
+
2 \frac{x-a}{\left[(x-a)^2+y^2\right]^{3/2}} = 0
$$

This equation defines the locus where the horizontal component vanishes.

### Condition for Zero Field $\vec{E}=0$

For the total field to vanish, both components must be zero simultaneously.

Since $E_y=0$ requires $y=0$, the zero-field point must lie on the $x$-axis. There we solve

$$
kq \frac{x+a}{|x+a|^3}
+
2kq \frac{x-a}{|x-a|^3} = 0
$$

The cancellation is possible only between the charges, where $-a < x < a$.

In that interval,

$$
\frac{1}{(x+a)^2} = \frac{2}{(a-x)^2}
$$

Taking square roots gives

$$
\frac{1}{x+a} = \frac{\sqrt{2}}{a-x}
$$

Thus

$$
a - x = \sqrt{2}(x+a)
$$

$$
a - \sqrt{2}a = x + \sqrt{2}x
$$

$$
x = a \frac{1-\sqrt{2}}{1+\sqrt{2}}
$$

Rationalizing,

$$
x = a(2\sqrt{2}-3)
$$

Therefore,

$$
\vec{E}=0
$$

at

$$
(x,y) = \left(a(2\sqrt{2}-3),0\right)
$$

which lies between the two charges and closer to the smaller charge $+q$.

### Numerical Evaluation for $a=0.2\,\mathrm{m}$, $y=0.3\,\mathrm{m}$, $q=2\,\mu\mathrm{C}$

For the point $(0,y)$,

$$
R = \sqrt{a^2+y^2}
= \sqrt{0.2^2+0.3^2}
= \sqrt{0.13}
\approx 0.3606\,\mathrm{m}
$$

Use

$$
E_x = -\frac{kqa}{R^3}
$$

$$
E_y = \frac{3kqy}{R^3}
$$

with

$$
k = 8.99 \times 10^9\,\mathrm{N\,m^2/C^2}
$$

and

$$
q = 2 \times 10^{-6}\,\mathrm{C}
$$

This gives

$$
E_x \approx -7.67 \times 10^4\,\mathrm{N/C}
$$

$$
E_y \approx 3.45 \times 10^5\,\mathrm{N/C}
$$

So

$$
\vec{E}(0,0.3) \approx
\left(-7.67 \times 10^4\,\hat{i} + 3.45 \times 10^5\,\hat{j}\right)\,\mathrm{N/C}
$$

Its magnitude is

$$
|\vec{E}| = \sqrt{E_x^2 + E_y^2}
\approx 3.54 \times 10^5\,\mathrm{N/C}
$$

### Limit $y \gg a$

For large $y$, one has

$$
(a^2+y^2)^{3/2} \approx y^3
$$

Therefore

$$
\vec{E}(0,y) \approx \frac{kq}{y^3}\left(-a\,\hat{i}+3y\,\hat{j}\right)
$$

or

$$
\vec{E}(0,y) \approx -\,\frac{kqa}{y^3}\,\hat{i} + \frac{3kq}{y^2}\,\hat{j}
$$

The dominant term is

$$
\vec{E}(0,y) \approx \frac{3kq}{y^2}\,\hat{j}
$$

which is the field of a total charge $3q$ seen from far away.

## Final Result

General field:

$$
\vec{E}(x,y) =
kq \frac{(x+a)\,\hat{i} + y\,\hat{j}}{\left[(x+a)^2+y^2\right]^{3/2}}
+
2kq \frac{(x-a)\,\hat{i} + y\,\hat{j}}{\left[(x-a)^2+y^2\right]^{3/2}}
$$

On the $y$-axis:

$$
\vec{E}(0,y)=
\frac{kq}{(a^2+y^2)^{3/2}}
\left(-a\,\hat{i}+3y\,\hat{j}\right)
$$

On the $x$-axis:

$$
\vec{E}(x,0)=
\left[
kq \frac{x+a}{|x+a|^3}
+
2kq \frac{x-a}{|x-a|^3}
\right]\hat{i}
$$

Conditions:

$$
E_y = 0 \Longrightarrow y=0
$$

$$
E_x = 0 \Longrightarrow
\frac{x+a}{\left[(x+a)^2+y^2\right]^{3/2}}
+
2 \frac{x-a}{\left[(x-a)^2+y^2\right]^{3/2}} = 0
$$

Zero field:

$$
\vec{E}=0 \quad \text{at} \quad
(x,y)=\left(a(2\sqrt{2}-3),0\right)
$$

Numerical value at $(0,0.3\,\mathrm{m})$:

$$
\vec{E} \approx
\left(-7.67 \times 10^4\,\hat{i}+3.45 \times 10^5\,\hat{j}\right)\,\mathrm{N/C}
$$

## Interpretation

Near the system, the unequal charges produce both horizontal and vertical components. Far away, the field behaves like that of a single charge $3q$ located near the origin, with small corrections caused by the charge asymmetry.
