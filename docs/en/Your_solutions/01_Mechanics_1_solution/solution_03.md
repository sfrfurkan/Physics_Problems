# Task 03 – Conservation of Energy for a Pendulum

## Problem Statement

A pendulum of length $1.0 \text{ m}$ is released from an initial angle of $15^\circ$.

Determine the speed of the pendulum bob at the bottom of its swing.

## Theory

If air resistance and friction are neglected, the total mechanical energy is conserved.

The change in gravitational potential energy becomes kinetic energy:

$$
mgh = \frac{1}{2}mv^2
$$

The vertical height difference between the release point and the lowest point is

$$
h = L(1 - \cos\theta_0)
$$

where:

- $L$ is the pendulum length,
- $\theta_0$ is the initial angle.

## Step-by-Step Solution

### Height Difference

The pendulum length is

$$
L = 1.0 \text{ m}
$$

The initial angle is

$$
\theta_0 = 15^\circ
$$

The height difference is

$$
h = L(1 - \cos\theta_0)
$$

Substitute the values:

$$
h = 1.0(1 - \cos 15^\circ)
$$

Using

$$
\cos 15^\circ \approx 0.9659
$$

gives

$$
h = 1 - 0.9659 = 0.0341 \text{ m}
$$

### Apply Energy Conservation

At the release point, the bob has gravitational potential energy relative to the lowest point:

$$
E_i = mgh
$$

At the bottom, this becomes kinetic energy:

$$
E_f = \frac{1}{2}mv^2
$$

Thus,

$$
mgh = \frac{1}{2}mv^2
$$

Cancel $m$:

$$
gh = \frac{1}{2}v^2
$$

Solve for $v$:

$$
v = \sqrt{2gh}
$$

Substitute $g = 9.81 \text{ m/s}^2$ and $h = 0.0341 \text{ m}$:

$$
v = \sqrt{2 \cdot 9.81 \cdot 0.0341}
$$

$$
v = \sqrt{0.669}
$$

$$
v \approx 0.818 \text{ m/s}
$$

## Final Result

The speed of the pendulum bob at the bottom is

$$
v \approx 0.82 \text{ m/s}
$$

## Interpretation

The initial gravitational potential energy depends on how high the bob is above the equilibrium position. Since the initial angle is small, the height difference is also small, so the final speed is less than $1 \text{ m/s}$.
