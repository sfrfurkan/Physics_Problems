# Task 09 – Vertical Throw with Linear Drag

## Problem Statement

The motion is governed by

$$
m\frac{dv}{dt} = -mg - kv
$$

with initial conditions

$$
v(0) = v_0, \quad x(0) = 10
$$

Perform the following tasks:

1. Solve the equation analytically.
2. Determine the maximum height.
3. Compare the result with the case without drag.
4. Provide a numerical simulation in Python.

## Theory

The differential equation

$$
m\frac{dv}{dt} = -mg - kv
$$

describes vertical motion under gravity with linear air resistance proportional to velocity.

It can be written as

$$
\frac{dv}{dt} + \frac{k}{m}v = -g
$$

This is a first-order linear differential equation.

The position is obtained from

$$
\frac{dx}{dt} = v(t)
$$

## Step-by-Step Solution

### Analytical Solution for the Velocity

Start from

$$
\frac{dv}{dt} + \frac{k}{m}v = -g
$$

Let

$$
\lambda = \frac{k}{m}
$$

Then

$$
\frac{dv}{dt} + \lambda v = -g
$$

The integrating factor is

$$
\mu(t) = e^{\lambda t}
$$

Multiplying the equation by $e^{\lambda t}$ gives

$$
e^{\lambda t}\frac{dv}{dt} + \lambda e^{\lambda t} v = -g e^{\lambda t}
$$

Thus,

$$
\frac{d}{dt}\left(e^{\lambda t}v\right) = -g e^{\lambda t}
$$

Integrate:

$$
e^{\lambda t}v = -g \int e^{\lambda t}\,dt + C
$$

$$
e^{\lambda t}v = -g \cdot \frac{1}{\lambda} e^{\lambda t} + C
$$

Therefore,

$$
v(t) = -\frac{g}{\lambda} + Ce^{-\lambda t}
$$

Apply the initial condition $v(0) = v_0$:

$$
v_0 = -\frac{g}{\lambda} + C
$$

so

$$
C = v_0 + \frac{g}{\lambda}
$$

Hence,

$$
v(t) = -\frac{g}{\lambda} + \left(v_0 + \frac{g}{\lambda}\right)e^{-\lambda t}
$$

Replacing $\lambda = k/m$ yields

$$
v(t) = -\frac{mg}{k} + \left(v_0 + \frac{mg}{k}\right)e^{-kt/m}
$$

### Analytical Solution for the Position

Since

$$
\frac{dx}{dt} = v(t)
$$

integrate:

$$
x(t) = x(0) + \int_0^t v(s)\,ds
$$

Substitute the expression for $v(s)$:

$$
x(t) = 10 + \int_0^t \left[-\frac{mg}{k} + \left(v_0 + \frac{mg}{k}\right)e^{-ks/m}\right] ds
$$

Compute each term separately:

$$
x(t) = 10 - \frac{mg}{k} t + \left(v_0 + \frac{mg}{k}\right)\int_0^t e^{-ks/m}\,ds
$$

Since

$$
\int_0^t e^{-ks/m}\,ds = \frac{m}{k}\left(1 - e^{-kt/m}\right)
$$

we obtain

$$
x(t) = 10 - \frac{mg}{k} t + \frac{m}{k}\left(v_0 + \frac{mg}{k}\right)\left(1 - e^{-kt/m}\right)
$$

### Maximum Height

The maximum height occurs when

$$
v(t_{\max}) = 0
$$

Using the velocity formula,

$$
0 = -\frac{mg}{k} + \left(v_0 + \frac{mg}{k}\right)e^{-kt_{\max}/m}
$$

Thus,

$$
\left(v_0 + \frac{mg}{k}\right)e^{-kt_{\max}/m} = \frac{mg}{k}
$$

so

$$
e^{-kt_{\max}/m} = \frac{mg/k}{v_0 + mg/k}
$$

Therefore,

$$
t_{\max} = \frac{m}{k}\ln\left(\frac{v_0 + mg/k}{mg/k}\right)
$$

This can be simplified to

$$
t_{\max} = \frac{m}{k}\ln\left(1 + \frac{kv_0}{mg}\right)
$$

The maximum height is then

$$
x_{\max} = x(t_{\max})
$$

with $x(t)$ from the previous section.

### Comparison with the Case Without Drag

Without drag, the equation of motion is

$$
m\frac{dv}{dt} = -mg
$$

so

$$
v(t) = v_0 - gt
$$

and

$$
x(t) = 10 + v_0 t - \frac{1}{2}gt^2
$$

The maximum height occurs for

$$
v = 0 \Rightarrow t_{\max}^{(0)} = \frac{v_0}{g}
$$

Then

$$
x_{\max}^{(0)} = 10 + \frac{v_0^2}{2g}
$$

Because drag always opposes the upward motion, the dragged trajectory has:

- a smaller ascent time,
- a smaller maximum height,
- a non-symmetric ascent and descent.

## Final Result

The analytical velocity is

$$
v(t) = -\frac{mg}{k} + \left(v_0 + \frac{mg}{k}\right)e^{-kt/m}
$$

The analytical position is

$$
x(t) = 10 - \frac{mg}{k} t + \frac{m}{k}\left(v_0 + \frac{mg}{k}\right)\left(1 - e^{-kt/m}\right)
$$

The time of maximum height is

$$
t_{\max} = \frac{m}{k}\ln\left(1 + \frac{kv_0}{mg}\right)
$$

The maximum height is obtained by substituting $t_{\max}$ into $x(t)$.

Without drag, the maximum height would be

$$
x_{\max}^{(0)} = 10 + \frac{v_0^2}{2g}
$$

which is always larger than the dragged case.

## Interpretation

Linear drag reduces the upward speed more strongly than gravity alone. As a result, the projectile reaches a lower maximum height and loses the time-reversal symmetry characteristic of ideal projectile motion.

## Numerical Simulation (Python)

```python
import numpy as np
import matplotlib.pyplot as plt

m = 1.0
k = 0.4
g = 9.81
v0 = 20.0
x0 = 10.0

dt = 0.001
t_max = 5.0

t = np.arange(0, t_max + dt, dt)
v = np.zeros_like(t)
x = np.zeros_like(t)

v[0] = v0
x[0] = x0

for i in range(len(t) - 1):
    a = -g - (k/m) * v[i]
    v[i + 1] = v[i] + a * dt
    x[i + 1] = x[i] + v[i] * dt

plt.figure(figsize=(8, 5))
plt.plot(t, x)
plt.xlabel("t [s]")
plt.ylabel("x(t) [m]")
plt.title("Vertical motion with linear drag")
plt.grid(True)
plt.show()

plt.figure(figsize=(8, 5))
plt.plot(t, v)
plt.xlabel("t [s]")
plt.ylabel("v(t) [m/s]")
plt.title("Velocity with linear drag")
plt.grid(True)
plt.show()
