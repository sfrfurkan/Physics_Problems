# Task 03 – Propagation of Error III

## Problem Statement

The resistance is calculated using Ohm's Law:

$$
R = \frac{V}{I}
$$

The measured voltage and current are

$$
V = (10.0 \pm 0.2)\ \mathrm{V}
$$

$$
I = (2.00 \pm 0.05)\ \mathrm{A}
$$

Calculate the resistance and its uncertainty.

## Theory

Ohm's Law gives

$$
R = \frac{V}{I}
$$

For division, fractional uncertainties add:

$$
\frac{\Delta R}{R} = \frac{\Delta V}{V} + \frac{\Delta I}{I}
$$

Thus,

$$
\Delta R = R\left(\frac{\Delta V}{V} + \frac{\Delta I}{I}\right)
$$

## Step-by-Step Solution

Given values:

$$
V = 10.0\ \mathrm{V}
$$

$$
I = 2.00\ \mathrm{A}
$$

$$
\Delta V = 0.2\ \mathrm{V}
$$

$$
\Delta I = 0.05\ \mathrm{A}
$$

The resistance is

$$
R = \frac{10.0}{2.00}
$$

$$
R = 5.00\ \Omega
$$

The fractional uncertainty is

$$
\frac{\Delta R}{R} = \frac{0.2}{10.0} + \frac{0.05}{2.00}
$$

$$
\frac{\Delta R}{R} = 0.020 + 0.025
$$

$$
\frac{\Delta R}{R} = 0.045
$$

The absolute uncertainty is

$$
\Delta R = 5.00(0.045)
$$

$$
\Delta R = 0.225\ \Omega
$$

Rounded appropriately,

$$
\Delta R = 0.23\ \Omega
$$

## Final Result

$$
R = (5.00 \pm 0.23)\ \Omega
$$

## Interpretation

The resistance depends on both voltage and current. Since resistance is calculated by division, the relative uncertainties of voltage and current both contribute to the final relative uncertainty of the resistance.
