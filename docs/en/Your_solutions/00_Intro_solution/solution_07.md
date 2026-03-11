# Task 07 – Logic and Series: Bicycle, Wall, and Fly

## Problem Statement

A bicycle is $10 \text{ m}$ from a wall and moves toward it at a constant speed of $1 \text{ m/s}$. A fly starts from the bicycle's front wheel and flies toward the wall at $2 \text{ m/s}$. Whenever it reaches the wall, it instantly turns back and flies to the bicycle, repeating this motion until the bicycle reaches the wall.

Determine the total distance traveled by the fly before it is crushed.

## Theory

Although the fly changes direction infinitely many times, its speed remains constant. The key idea is to determine the total time available before the bicycle reaches the wall. Then the total distance traveled by the fly is simply speed multiplied by time.

## Step-by-Step Solution

### 1. Time until the bicycle reaches the wall

The bicycle starts $10 \text{ m}$ away from the wall and moves at

$$
v_{\text{bike}} = 1 \text{ m/s}
$$

Therefore, the travel time is

$$
t = \frac{d}{v} = \frac{10}{1}
$$

$$
t = 10 \text{ s}
$$

### 2. Distance traveled by the fly

The fly moves continuously for the same total time of $10 \text{ s}$ at speed

$$
v_{\text{fly}} = 2 \text{ m/s}
$$

Thus,

$$
d_{\text{fly}} = v_{\text{fly}} t
$$

$$
d_{\text{fly}} = 2 \cdot 10
$$

$$
d_{\text{fly}} = 20 \text{ m}
$$

## Final Result

The fly travels a total distance of

$$
20 \text{ m}
$$

## Interpretation

The problem appears to require summing an infinite series of shorter and shorter trips. However, the motion is more easily analyzed through total time. The infinite number of direction changes does not affect the fact that the fly flies for exactly $10$ seconds at constant speed.

---
