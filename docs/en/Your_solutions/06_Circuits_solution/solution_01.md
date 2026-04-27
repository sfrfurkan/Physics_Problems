# Task 01 – Series and Parallel Circuits

## Problem Statement

Three resistors:

- $R_1 = 15 \, \Omega$
- $R_2 = 30 \, \Omega$
- $R_3 = 50 \, \Omega$

Battery voltage:

- $V = 12 \, \text{V}$

Find:

1. Equivalent resistance (series and parallel)
2. Total current in each case

---

## Theory

### Series Combination

$$
R_{\text{eq}} = R_1 + R_2 + R_3
$$

### Parallel Combination

$$
\frac{1}{R_{\text{eq}}} =
\frac{1}{R_1} + \frac{1}{R_2} + \frac{1}{R_3}
$$

### Ohm’s Law

$$
I = \frac{V}{R}
$$

---

## Step-by-Step Solution

### Series Case

$$
R_{\text{eq}} = 15 + 30 + 50 = 95 \, \Omega
$$

$$
I = \frac{12}{95} \approx 0.126 \, \text{A}
$$

---

### Parallel Case

$$
\frac{1}{R_{\text{eq}}} =
\frac{1}{15} + \frac{1}{30} + \frac{1}{50}
$$

Common denominator $150$:

$$
= \frac{10 + 5 + 3}{150} = \frac{18}{150} = 0.12
$$

$$
R_{\text{eq}} = \frac{1}{0.12} \approx 8.33 \, \Omega
$$

$$
I = \frac{12}{8.33} \approx 1.44 \, \text{A}
$$

---

## Final Result

- Series:
  - $R_{\text{eq}} = 95 \, \Omega$
  - $I \approx 0.126 \, \text{A}$

- Parallel:
  - $R_{\text{eq}} \approx 8.33 \, \Omega$
  - $I \approx 1.44 \, \text{A}$

---

## Interpretation

Parallel circuits drastically reduce resistance, resulting in much higher current compared to series circuits.
