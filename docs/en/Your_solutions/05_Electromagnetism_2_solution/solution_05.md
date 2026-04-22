# Task 05 – Parallel-Plate Capacitor: Capacitance, Energy, Field, and Force

## Problem Statement

A parallel-plate capacitor has the following parameters:

- plate area $S = 0.02\ \mathrm{m^2}$
- plate separation $d = 5\ \mathrm{mm}$
- voltage $U = 500\ \mathrm{V}$

Determine:

1. the capacitance $C$
2. the energy stored in the capacitor
3. the electric field intensity $E$ between the plates
4. the force of attraction $F$ between the plates

## Theory

For an ideal parallel-plate capacitor in vacuum or air, the capacitance is

$$
C = \varepsilon_0 \frac{S}{d}
$$

The energy stored in a capacitor is

$$
W = \frac{1}{2} C U^2
$$

The electric field between the plates is approximately uniform and given by

$$
E = \frac{U}{d}
$$

The attractive force between the plates can be found from the electric pressure on the plates:

$$
p = \frac{1}{2} \varepsilon_0 E^2
$$

Since force equals pressure times area,

$$
F = pS = \frac{1}{2} \varepsilon_0 E^2 S
$$

## Step-by-Step Solution

### Capacitance

Given:

$$
S = 0.02\ \mathrm{m^2}
$$

$$
d = 5\ \mathrm{mm} = 5 \times 10^{-3}\ \mathrm{m}
$$

Using

$$
C = \varepsilon_0 \frac{S}{d}
$$

Substitute the values:

$$
C = 8.854 \times 10^{-12} \cdot \frac{0.02}{5 \times 10^{-3}}
$$

First compute the ratio:

$$
\frac{0.02}{5 \times 10^{-3}} = 4
$$

Thus,

$$
C = 8.854 \times 10^{-12} \times 4
$$

$$
C = 3.54 \times 10^{-11}\ \mathrm{F}
$$

### Energy Stored

Using

$$
W = \frac{1}{2} C U^2
$$

with

$$
U = 500\ \mathrm{V}
$$

Substitute:

$$
W = \frac{1}{2} \times 3.54 \times 10^{-11} \times (500)^2
$$

Compute the square:

$$
(500)^2 = 2.5 \times 10^5
$$

Then,

$$
W = \frac{1}{2} \times 3.54 \times 10^{-11} \times 2.5 \times 10^5
$$

$$
W = 4.43 \times 10^{-6}\ \mathrm{J}
$$

### Electric Field Intensity

Using

$$
E = \frac{U}{d}
$$

Substitute:

$$
E = \frac{500}{5 \times 10^{-3}}
$$

$$
E = 1.0 \times 10^5\ \mathrm{V/m}
$$

### Force of Attraction

Using

$$
F = \frac{1}{2} \varepsilon_0 E^2 S
$$

Substitute the values:

$$
F = \frac{1}{2} \times 8.854 \times 10^{-12} \times (1.0 \times 10^5)^2 \times 0.02
$$

Compute the field squared:

$$
(1.0 \times 10^5)^2 = 1.0 \times 10^{10}
$$

Thus,

$$
F = \frac{1}{2} \times 8.854 \times 10^{-12} \times 1.0 \times 10^{10} \times 0.02
$$

$$
F = \frac{1}{2} \times 8.854 \times 10^{-2} \times 0.02
$$

$$
F = 8.85 \times 10^{-4}\ \mathrm{N}
$$

## Final Result

Capacitance:

$$
C = 3.54 \times 10^{-11}\ \mathrm{F}
$$

Stored energy:

$$
W = 4.43 \times 10^{-6}\ \mathrm{J}
$$

Electric field intensity:

$$
E = 1.0 \times 10^5\ \mathrm{V/m}
$$

Force of attraction:

$$
F = 8.85 \times 10^{-4}\ \mathrm{N}
$$

## Interpretation

The capacitor has a very small capacitance because the plate area is moderate while the separation is still several millimeters. Even at $500\ \mathrm{V}$, the stored energy remains in the microjoule range because the capacitance is small. The electric field is strong, but the attractive force between the plates is still quite small because the plate area is limited and vacuum permittivity is very small.
