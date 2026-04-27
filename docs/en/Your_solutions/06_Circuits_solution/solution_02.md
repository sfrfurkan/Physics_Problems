# Task 02 – Combining Three 1Ω Resistors

## Problem Statement

Using exactly three resistors of $1 \, \Omega$, find all unique equivalent resistances.

---

## Theory

Possible combinations:

- All series
- All parallel
- Mixed (series + parallel)

---

## Step-by-Step Solution

### 1. All in Series

$$
R = 1 + 1 + 1 = 3 \, \Omega
$$

---

### 2. All in Parallel

$$
\frac{1}{R} = 1 + 1 + 1 = 3
$$

$$
R = \frac{1}{3} \, \Omega
$$

---

### 3. Two in Parallel, One in Series

Parallel pair:

$$
R = \frac{1 \cdot 1}{1 + 1} = \frac{1}{2}
$$

Add third resistor:

$$
R = \frac{1}{2} + 1 = \frac{3}{2} \, \Omega
$$

---

### 4. Two in Series, One in Parallel

Series pair:

$$
R = 2
$$

Parallel with third:

$$
R = \frac{2 \cdot 1}{2 + 1} = \frac{2}{3} \, \Omega
$$

---

## Final Result

All unique values:

$$
\left\{
3,\;
\frac{3}{2},\;
\frac{2}{3},\;
\frac{1}{3}
\right\} \, \Omega
$$

---

## Interpretation

Even with identical resistors, different configurations produce a wide range of equivalent resistances.
