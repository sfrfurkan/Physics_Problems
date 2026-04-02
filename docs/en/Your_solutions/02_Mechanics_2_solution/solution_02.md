# Task 02 – Harmonic Motion of a Mass-Spring System

## Problem Statement

A mass of $10 \text{ kg}$ is attached to a spring and oscillates according to

$$
x(t) = 0.2 \cos(10\pi t)
$$

where $x$ is measured in meters.

Determine:

1. The spring constant $k$.
2. The total mechanical energy of the system.

## Theory

For simple harmonic motion of a mass-spring system,

$$
x(t) = A \cos(\omega t + \phi)
$$

where:

- $A$ is the amplitude,
- $\omega$ is the angular frequency,
- $\phi$ is the phase.

The angular frequency is related to the spring constant by

$$
\omega = \sqrt{\frac{k}{m}}
$$

Hence,

$$
k = m\omega^2
$$

The total mechanical energy in simple harmonic motion is constant and equals

$$
E = \frac{1}{2} k A^2
$$

## Step-by-Step Solution

### Identify the Parameters

Given

$$
x(t) = 0.2 \cos(10\pi t)
$$

comparison with the standard form gives:

- amplitude

$$
A = 0.2 \text{ m}
$$

- angular frequency

$$
\omega = 10\pi \text{ rad/s}
$$

- mass

$$
m = 10 \text{ kg}
$$

### Part 1: Spring Constant

Using

$$
k = m\omega^2
$$

substitute the known values:

$$
k = 10(10\pi)^2
$$

$$
k = 10 \cdot 100\pi^2
$$

$$
k = 1000\pi^2 \text{ N/m}
$$

Numerically,

$$
k \approx 1000 \cdot 9.87 = 9869.6 \text{ N/m}
$$

### Part 2: Total Mechanical Energy

The total energy is

$$
E = \frac{1}{2} k A^2
$$

Substitute $k = 1000\pi^2$ and $A = 0.2$:

$$
E = \frac{1}{2}(1000\pi^2)(0.2)^2
$$

$$
E = \frac{1}{2}(1000\pi^2)(0.04)
$$

$$
E = 20\pi^2 \text{ J}
$$

Numerically,

$$
E \approx 20 \cdot 9.87 = 197.4 \text{ J}
$$

## Final Result

The spring constant is

$$
k = 1000\pi^2 \text{ N/m} \approx 9.87 \times 10^3 \text{ N/m}
$$

The total mechanical energy is

$$
E = 20\pi^2 \text{ J} \approx 197.4 \text{ J}
$$

## Interpretation

The oscillation frequency is high because the effective stiffness of the spring is large. The total mechanical energy depends on both the stiffness and the square of the amplitude. Since there is no damping in the model, this energy remains constant during the motion.
