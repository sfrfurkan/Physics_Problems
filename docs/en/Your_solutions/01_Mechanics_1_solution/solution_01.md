# Task 01 – Gravitational Dependence of a Simple Pendulum

## Problem Statement

A simple pendulum has a period of $4 \text{ s}$ on Earth.

1. Determine its period on the Moon, where the gravitational acceleration is about $\frac{1}{6}$ of Earth's.
2. Determine the length required for a simple pendulum to have a period of exactly $1 \text{ s}$ on Earth.

## Theory

For small oscillations, the period of a simple pendulum is

$$
T = 2\pi \sqrt{\frac{L}{g}}
$$

where:

- $T$ is the period,
- $L$ is the pendulum length,
- $g$ is the gravitational acceleration.

For a fixed length, the period is proportional to $1/\sqrt{g}$.

## Step-by-Step Solution

### Part 1: Period on the Moon

For the same pendulum length,

$$
T \propto \frac{1}{\sqrt{g}}
$$

Therefore,

$$
\frac{T_{\text{Moon}}}{T_{\text{Earth}}} = \sqrt{\frac{g_{\text{Earth}}}{g_{\text{Moon}}}}
$$

Since

$$
g_{\text{Moon}} = \frac{1}{6} g_{\text{Earth}}
$$

it follows that

$$
\frac{T_{\text{Moon}}}{T_{\text{Earth}}} = \sqrt{\frac{g_{\text{Earth}}}{g_{\text{Earth}}/6}} = \sqrt{6}
$$

Thus,

$$
T_{\text{Moon}} = T_{\text{Earth}} \sqrt{6}
$$

Substituting $T_{\text{Earth}} = 4 \text{ s}$,

$$
T_{\text{Moon}} = 4\sqrt{6} \text{ s}
$$

Numerically,

$$
T_{\text{Moon}} \approx 4 \cdot 2.449 = 9.80 \text{ s}
$$

### Part 2: Length for a Period of 1 Second on Earth

Starting from

$$
T = 2\pi \sqrt{\frac{L}{g}}
$$

solve for $L$:

$$
\frac{T}{2\pi} = \sqrt{\frac{L}{g}}
$$

Squaring both sides gives

$$
\left(\frac{T}{2\pi}\right)^2 = \frac{L}{g}
$$

Therefore,

$$
L = g\left(\frac{T}{2\pi}\right)^2
$$

Using $T = 1 \text{ s}$ and $g = 9.81 \text{ m/s}^2$,

$$
L = 9.81 \left(\frac{1}{2\pi}\right)^2
$$

$$
L = 9.81 \cdot \frac{1}{4\pi^2}
$$

Since

$$
4\pi^2 \approx 39.48
$$

then

$$
L \approx \frac{9.81}{39.48} \approx 0.248 \text{ m}
$$

## Final Result

1. Period on the Moon:

$$
T_{\text{Moon}} = 4\sqrt{6} \text{ s} \approx 9.80 \text{ s}
$$

2. Required length for $T = 1 \text{ s}$ on Earth:

$$
L \approx 0.248 \text{ m}
$$

## Interpretation

The pendulum swings more slowly on the Moon because the gravitational acceleration is weaker. A weaker restoring force leads to a longer period. The second result shows that a pendulum with a period of $1 \text{ s}$ must be relatively short, about $25 \text{ cm}$.
