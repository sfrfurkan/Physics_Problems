# Task 06 – Electromagnetic Wave Analysis

## Problem Statement

An electromagnetic wave has its electric field component described by

$$
E_y(x,t) = 100 \sin(10^7 x - \omega t)\ \mathrm{V/m}
$$

Determine:

1. the direction of propagation
2. the wavelength $\lambda$
3. the angular frequency $\omega$
4. the equation for the magnetic field component

## Theory

A plane electromagnetic wave traveling in the positive $x$ direction has the general form

$$
E(x,t) = E_0 \sin(kx - \omega t)
$$

where:

- $E_0$ is the amplitude
- $k$ is the wave number
- $\omega$ is the angular frequency

The wave number and wavelength are related by

$$
k = \frac{2\pi}{\lambda}
$$

For an electromagnetic wave in vacuum,

$$
\omega = ck
$$

where

$$
c = 3.00 \times 10^8\ \mathrm{m/s}
$$

The electric and magnetic field amplitudes satisfy

$$
E_0 = c B_0
$$

so that

$$
B_0 = \frac{E_0}{c}
$$

The electric field, magnetic field, and direction of propagation are mutually perpendicular.

## Step-by-Step Solution

### Direction of Propagation

The electric field is given by

$$
E_y(x,t) = 100 \sin(10^7 x - \omega t)
$$

A wave of the form

$$
\sin(kx - \omega t)
$$

travels in the positive $x$ direction.

Therefore, the wave propagates along

$$
+x
$$

### Wavelength

From the given expression,

$$
k = 10^7\ \mathrm{rad/m}
$$

Using

$$
\lambda = \frac{2\pi}{k}
$$

Substitute the value of $k$:

$$
\lambda = \frac{2\pi}{10^7}
$$

$$
\lambda \approx 6.28 \times 10^{-7}\ \mathrm{m}
$$

Thus,

$$
\lambda \approx 628\ \mathrm{nm}
$$

### Angular Frequency

In vacuum,

$$
\omega = ck
$$

Substitute the values:

$$
\omega = (3.00 \times 10^8)(10^7)
$$

$$
\omega = 3.00 \times 10^{15}\ \mathrm{rad/s}
$$

### Magnetic Field Component

The electric field is along the $y$ direction. The wave travels along the $+x$ direction. Therefore, the magnetic field must point along the $z$ direction so that

$$
\vec{E} \times \vec{B}
$$

points in the $+x$ direction.

The magnetic field amplitude is

$$
B_0 = \frac{E_0}{c}
$$

Substitute the values:

$$
B_0 = \frac{100}{3.00 \times 10^8}
$$

$$
B_0 = 3.33 \times 10^{-7}\ \mathrm{T}
$$

Thus the magnetic field component can be written as

$$
B_z(x,t) = 3.33 \times 10^{-7} \sin(10^7 x - \omega t)\ \mathrm{T}
$$

## Final Result

Direction of propagation:

$$
+x
$$

Wavelength:

$$
\lambda = 6.28 \times 10^{-7}\ \mathrm{m} = 628\ \mathrm{nm}
$$

Angular frequency:

$$
\omega = 3.00 \times 10^{15}\ \mathrm{rad/s}
$$

Magnetic field component:

$$
B_z(x,t) = 3.33 \times 10^{-7} \sin(10^7 x - \omega t)\ \mathrm{T}
$$

## Interpretation

The wave propagates in the positive $x$ direction because of the phase combination $kx - \omega t$. Its wavelength lies in the visible range, specifically near orange-red light. The magnetic field oscillates in phase with the electric field and has a much smaller amplitude because electromagnetic waves satisfy $E_0 = cB_0$.
