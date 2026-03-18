# Task 03 – Path Intersection

## Problem Statement

Alice: $A(t) = (2+t, 8-3t)$  
Bob: $B(t) = (2t-1, 2t+2)$

---

## Step-by-Step Solution

Solve:

$$
2 + t = 2t - 1
$$

$$
t = 3
$$

Check second coordinate:

$$
8 - 3t = 2t + 2
$$

$$
8 - 9 = 6 + 2
$$

$$
-1 \ne 8
$$

No collision.

---

### Distance

$$
D^2 = (3 - t)^2 + (6 - 5t)^2
$$

Minimize:

$$
\frac{d}{dt} D^2 = 52t - 66 = 0
$$

$$
t = \frac{33}{26}
$$

---

## Final Result

- No intersection
- Closest approach at $t = \frac{33}{26}$

---

## Interpretation

Paths cross geometrically but not at the same time.
