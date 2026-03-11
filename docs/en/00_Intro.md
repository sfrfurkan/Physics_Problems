# Problem Set 01 – Solutions

## Task 1

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

## Task 2

# Task 02 – Systems of Equations

## Problem Statement

Find the values of $x$ and $y$ that satisfy the system

$$
2x + 3y = 12
$$

and

$$
x - y = 1
$$

## Theory

A system of two linear equations in two unknowns can be solved by substitution or elimination. The goal is to reduce the system to one equation in one variable and then back-substitute.

## Step-by-Step Solution

From the second equation,

$$
x - y = 1
$$

solve for $x$:

$$
x = y + 1
$$

Substitute this expression into the first equation:

$$
2(y + 1) + 3y = 12
$$

Expand:

$$
2y + 2 + 3y = 12
$$

Combine like terms:

$$
5y + 2 = 12
$$

Subtract $2$ from both sides:

$$
5y = 10
$$

Divide by $5$:

$$
y = 2
$$

Now substitute into

$$
x = y + 1
$$

to obtain

$$
x = 2 + 1 = 3
$$

## Final Result

The solution is

$$
x = 3
$$

and

$$
y = 2
$$

## Interpretation

The pair $(3,2)$ satisfies both equations simultaneously. In coordinate geometry, this pair represents the intersection point of the two straight lines.

---

## Task 3

# Task 03 – Proportionality in Gravitation

## Problem Statement

The universal law of gravitation is

$$
F = G \frac{m_1 m_2}{r^2}
$$

Determine the factor by which the force $F$ changes if:

1. the distance $r$ is doubled,
2. both masses $m_1$ and $m_2$ are halved.

## Theory

When a quantity depends on variables through multiplication and powers, proportional reasoning can determine how the quantity changes under scaling.

Here,

$$
F \propto \frac{m_1 m_2}{r^2}
$$

This means:

- halving one mass multiplies the force by $\frac{1}{2}$,
- halving both masses multiplies the force by $\frac{1}{4}$,
- doubling the distance multiplies the force by $\frac{1}{2^2} = \frac{1}{4}$.

## Step-by-Step Solution

Let the original force be

$$
F = G \frac{m_1 m_2}{r^2}
$$

After the change:

$$
m_1' = \frac{m_1}{2}
$$

$$
m_2' = \frac{m_2}{2}
$$

$$
r' = 2r
$$

The new force is

$$
F' = G \frac{m_1' m_2'}{(r')^2}
$$

Substitute the modified quantities:

$$
F' = G \frac{\left(\frac{m_1}{2}\right)\left(\frac{m_2}{2}\right)}{(2r)^2}
$$

Simplify the numerator:

$$
F' = G \frac{\frac{m_1 m_2}{4}}{4r^2}
$$

$$
F' = G \frac{m_1 m_2}{16r^2}
$$

Compare with the original expression

$$
F = G \frac{m_1 m_2}{r^2}
$$

Therefore,

$$
F' = \frac{1}{16} F
$$

## Final Result

The gravitational force becomes

$$
F' = \frac{F}{16}
$$

So the force is reduced by a factor of $16$.

## Interpretation

The inverse-square dependence on distance is strong. Doubling the distance alone already reduces the force to one quarter. Halving both masses introduces another factor of one quarter, giving a total factor of

$$
\frac{1}{4} \cdot \frac{1}{4} = \frac{1}{16}
$$

---

## Task 4

# Task 04 – Rearranging the Pendulum Formula

## Problem Statement

The period of a simple pendulum is

$$
T = 2\pi \sqrt{\frac{L}{g}}
$$

Rearrange the formula to obtain an expression for $g$.

## Theory

Rearranging formulas requires isolating the desired variable by applying inverse operations in the correct order. Because $g$ appears inside a square root and in the denominator, squaring the equation is an essential step.

## Step-by-Step Solution

Start with

$$
T = 2\pi \sqrt{\frac{L}{g}}
$$

Divide both sides by $2\pi$:

$$
\frac{T}{2\pi} = \sqrt{\frac{L}{g}}
$$

Square both sides:

$$
\left(\frac{T}{2\pi}\right)^2 = \frac{L}{g}
$$

Rewrite the left-hand side:

$$
\frac{T^2}{4\pi^2} = \frac{L}{g}
$$

Multiply both sides by $g$:

$$
g \frac{T^2}{4\pi^2} = L
$$

Now multiply both sides by $\frac{4\pi^2}{T^2}$:

$$
g = \frac{4\pi^2 L}{T^2}
$$

## Final Result

The rearranged formula is

$$
g = \frac{4\pi^2 L}{T^2}
$$

## Interpretation

This expression shows that the gravitational acceleration can be determined experimentally by measuring the pendulum length $L$ and the period $T$. It is widely used in introductory laboratory experiments.

---

## Task 5

# Task 05 – Trigonometric Components of a Vector

## Problem Statement

A vector $\vec{A}$ has magnitude $15$ and makes an angle of $\theta = 60^\circ$ with the horizontal axis. Determine its horizontal and vertical components.

## Theory

For a vector of magnitude $A$ making an angle $\theta$ with the positive horizontal axis, the components are

$$
A_x = A \cos\theta
$$

and

$$
A_y = A \sin\theta
$$

These relations follow from right-triangle trigonometry.

## Step-by-Step Solution

Given

$$
A = 15
$$

and

$$
\theta = 60^\circ
$$

### 1. Horizontal component

$$
A_x = 15 \cos 60^\circ
$$

Since

$$
\cos 60^\circ = \frac{1}{2}
$$

it follows that

$$
A_x = 15 \cdot \frac{1}{2}
$$

$$
A_x = 7.5
$$

### 2. Vertical component

$$
A_y = 15 \sin 60^\circ
$$

Since

$$
\sin 60^\circ = \frac{\sqrt{3}}{2}
$$

it follows that

$$
A_y = 15 \cdot \frac{\sqrt{3}}{2}
$$

$$
A_y = \frac{15\sqrt{3}}{2}
$$

Numerically,

$$
A_y \approx 12.99
$$

## Final Result

The components are

$$
A_x = 7.5
$$

and

$$
A_y = \frac{15\sqrt{3}}{2} \approx 12.99
$$

## Interpretation

The vector points upward and to the right. Because the angle is larger than $45^\circ$, the vertical component is greater than the horizontal component.

---

## Task 6

# Task 06 – Function Analysis

## Problem Statement

Consider the function

$$
f(x) = 3x^2 - 12x + 7
$$

Identify any local maxima or minima.

## Theory

A quadratic function of the form

$$
f(x) = ax^2 + bx + c
$$

has a vertex at

$$
x = -\frac{b}{2a}
$$

If $a > 0$, the parabola opens upward and the vertex is a minimum. If $a < 0$, it opens downward and the vertex is a maximum.

The same conclusion can be reached using derivatives. Critical points occur where

$$
f'(x) = 0
$$

## Step-by-Step Solution

For

$$
f(x) = 3x^2 - 12x + 7
$$

the derivative is

$$
f'(x) = 6x - 12
$$

Set the derivative equal to zero:

$$
6x - 12 = 0
$$

$$
6x = 12
$$

$$
x = 2
$$

Now evaluate the function at $x = 2$:

$$
f(2) = 3(2)^2 - 12(2) + 7
$$

$$
f(2) = 12 - 24 + 7
$$

$$
f(2) = -5
$$

To determine whether this is a minimum or maximum, consider the second derivative:

$$
f''(x) = 6
$$

Since

$$
f''(x) > 0
$$

the critical point is a local minimum.

## Final Result

The function has a local minimum at

$$
x = 2
$$

with value

$$
f(2) = -5
$$

There is no local maximum.

## Interpretation

Because the coefficient of $x^2$ is positive, the parabola opens upward. Therefore, the vertex is the lowest point of the graph and represents the unique minimum.

---

## Task 7

# Task 07 – Logic and Series: Bicycle, Wall, and Fly

## Problem Statement

A bicycle is $10 \text{ m}$ from a wall and moves toward it at a constant speed of $1 \text{ m/s}$. A fly starts from the bicycle's front wheel and flies toward the wall at $2 \text{ m/s}$. Whenever it reaches the wall, it instantly turns back and flies to the bicycle, repeating this motion until the bicycle reaches the wall.

Determine the total distance traveled by the fly before it is crushed.

## Theory

Although the fly changes direction infinitely many times, its speed remains constant. The key idea is to determine the total time available before the bicycle reaches the wall. Then the total distance traveled by the fly is simply speed multiplied by time.

## Step-by-Step Solution

### 1. Time until the bicycle reaches the wall

The bicycle starts $10 \text{ m}$ away from the wall and moves at

$$
v_{\text{bike}} = 1 \text{ m/s}
$$

Therefore, the travel time is

$$
t = \frac{d}{v} = \frac{10}{1}
$$

$$
t = 10 \text{ s}
$$

### 2. Distance traveled by the fly

The fly moves continuously for the same total time of $10 \text{ s}$ at speed

$$
v_{\text{fly}} = 2 \text{ m/s}
$$

Thus,

$$
d_{\text{fly}} = v_{\text{fly}} t
$$

$$
d_{\text{fly}} = 2 \cdot 10
$$

$$
d_{\text{fly}} = 20 \text{ m}
$$

## Final Result

The fly travels a total distance of

$$
20 \text{ m}
$$

## Interpretation

The problem appears to require summing an infinite series of shorter and shorter trips. However, the motion is more easily analyzed through total time. The infinite number of direction changes does not affect the fact that the fly flies for exactly $10$ seconds at constant speed.

---

## Task 8

# Task 08 – Definite Integral of $\sin x$

## Problem Statement

Calculate the area under the curve

$$
f(x) = \sin x
$$

from $x = 0$ to $x = \pi$.

## Theory

The area under a curve on an interval is given by a definite integral:

$$
A = \int_a^b f(x)\,dx
$$

An antiderivative of $\sin x$ is

$$
\int \sin x\,dx = -\cos x + C
$$

## Step-by-Step Solution

The required area is

$$
A = \int_0^\pi \sin x\,dx
$$

Use the antiderivative:

$$
A = \left[-\cos x\right]_0^\pi
$$

Evaluate at the bounds:

$$
A = -\cos(\pi) - \left(-\cos(0)\right)
$$

Since

$$
\cos(\pi) = -1
$$

and

$$
\cos(0) = 1
$$

it follows that

$$
A = -(-1) - (-1)
$$

$$
A = 1 + 1
$$

$$
A = 2
$$

## Final Result

The area under the curve is

$$
2
$$

## Interpretation

On the interval from $0$ to $\pi$, the function $\sin x$ is nonnegative, so the definite integral is equal to the geometric area. The total enclosed area is $2$ square units.

---

## Task 9

# Task 09 – Optimization of a Rectangle Under a Curve

## Problem Statement

A rectangle is inscribed under the curve

$$
y = 3 - x^2
$$

in the first quadrant. Determine the dimensions of the rectangle with maximum area.

## Theory

If the upper-right corner of the rectangle lies on the curve, then its width and height can be expressed in terms of one variable. The area then becomes a function of that variable, and the maximum can be found using calculus.

Because the rectangle lies in the first quadrant with sides along the axes:

- width is $x$,
- height is $y = 3 - x^2$.

Thus the area is

$$
A(x) = x(3 - x^2)
$$

## Step-by-Step Solution

### 1. Area function

The area is

$$
A(x) = x(3 - x^2)
$$

Expand:

$$
A(x) = 3x - x^3
$$

### 2. Differentiate the area

$$
A'(x) = 3 - 3x^2
$$

Set the derivative equal to zero:

$$
3 - 3x^2 = 0
$$

$$
1 - x^2 = 0
$$

$$
x^2 = 1
$$

Since the rectangle is in the first quadrant, $x > 0$, so

$$
x = 1
$$

### 3. Determine the corresponding height

Substitute $x = 1$ into the curve equation:

$$
y = 3 - x^2
$$

$$
y = 3 - 1^2
$$

$$
y = 2
$$

### 4. Verify that this gives a maximum

The second derivative is

$$
A''(x) = -6x
$$

At $x = 1$,

$$
A''(1) = -6 < 0
$$

so the area is maximized there.

## Final Result

The rectangle of maximum area has dimensions

$$
\text{width} = 1
$$

and

$$
\text{height} = 2
$$

Its maximum area is

$$
A_{\max} = 1 \cdot 2 = 2
$$

## Interpretation

As the rectangle becomes wider, its height decreases because the top-right corner must remain on the parabola. The optimal rectangle balances these two competing effects, producing the maximum area at $(x,y) = (1,2)$.

---

## Task 10

# Task 10 – Infinite Series and Final Position of an Ant

## Problem Statement

An ant starts at the origin and moves according to the pattern:

- $1$ m east,
- $\frac{1}{2}$ m north,
- $\frac{1}{3}$ m west,
- $\frac{1}{4}$ m south,
- $\frac{1}{5}$ m east,

and continues in this way indefinitely.

Determine the final position of the ant.

## Theory

The motion separates naturally into horizontal and vertical components.

- Horizontal displacements occur on odd-numbered steps:
  $1, \frac{1}{3}, \frac{1}{5}, \frac{1}{7}, \dots$
- Vertical displacements occur on even-numbered steps:
  $\frac{1}{2}, \frac{1}{4}, \frac{1}{6}, \frac{1}{8}, \dots$

The directions alternate:

- horizontally: east, west, east, west, $\dots$
- vertically: north, south, north, south, $\dots$

Therefore, the final coordinates are determined by two alternating series.

A standard result is

$$
1 - \frac{1}{3} + \frac{1}{5} - \frac{1}{7} + \cdots = \frac{\pi}{4}
$$

and

$$
\frac{1}{2} - \frac{1}{4} + \frac{1}{6} - \frac{1}{8} + \cdots = \frac{1}{2}\ln 2
$$

## Step-by-Step Solution

### 1. Horizontal displacement

The horizontal motion is

$$
x = 1 - \frac{1}{3} + \frac{1}{5} - \frac{1}{7} + \cdots
$$

This is the Leibniz series for $\frac{\pi}{4}$, so

$$
x = \frac{\pi}{4}
$$

### 2. Vertical displacement

The vertical motion is

$$
y = \frac{1}{2} - \frac{1}{4} + \frac{1}{6} - \frac{1}{8} + \cdots
$$

Factor out $\frac{1}{2}$:

$$
y = \frac{1}{2}\left(1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \cdots \right)
$$

The alternating harmonic series satisfies

$$
1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \cdots = \ln 2
$$

Therefore,

$$
y = \frac{1}{2}\ln 2
$$

## Final Result

The final position of the ant is

$$
\left(\frac{\pi}{4}, \frac{1}{2}\ln 2\right)
$$

Numerically,

$$
\left(\frac{\pi}{4}, \frac{1}{2}\ln 2\right) \approx (0.785,\ 0.347)
$$

## Interpretation

The infinite motion converges to a finite point because both coordinate sums are convergent alternating series. Even though the ant keeps moving forever, the cumulative displacement approaches a fixed limit in the plane.
