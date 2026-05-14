# Task 01 – Propagation of Error I

## Problem Statement

The radius of a sphere is measured as

$$
r = (6.20 \pm 0.05)\ \mathrm{cm}
$$

Calculate the volume of the sphere and its associated uncertainty.

## Theory

The volume of a sphere is

$$
V = \frac{4}{3}\pi r^3
$$

For a quantity that depends on one measured variable, the uncertainty is found using propagation of error:

$$
\Delta V = \left|\frac{dV}{dr}\right|\Delta r
$$

Since

$$
\frac{dV}{dr} = 4\pi r^2
$$

the uncertainty becomes

$$
\Delta V = 4\pi r^2 \Delta r
$$

## Step-by-Step Solution

Given values:

$$
r = 6.20\ \mathrm{cm}
$$

$$
\Delta r = 0.05\ \mathrm{cm}
$$

The volume is

$$
V = \frac{4}{3}\pi (6.20)^3
$$

$$
V = 997.39\ \mathrm{cm^3}
$$

The uncertainty is

$$
\Delta V = 4\pi (6.20)^2(0.05)
$$

$$
\Delta V = 24.15\ \mathrm{cm^3}
$$

Rounded appropriately,

$$
V = 997\ \mathrm{cm^3}
$$

$$
\Delta V = 24\ \mathrm{cm^3}
$$

## Final Result

$$
V = (997 \pm 24)\ \mathrm{cm^3}
$$

## Interpretation

The measured radius has a small absolute uncertainty, but the volume depends on the cube of the radius. Therefore, the uncertainty in the volume is amplified compared with the uncertainty in the radius.
