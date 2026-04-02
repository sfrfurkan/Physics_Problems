# Task 07 – Dynamics with Friction for Two Blocks

## Problem Statement

A $5 \text{ kg}$ block is placed on top of a $10 \text{ kg}$ block. A horizontal force of $45 \text{ N}$ is applied to the $10 \text{ kg}$ block, while the $5 \text{ kg}$ block is tied to the wall. The coefficient of kinetic friction between all moving surfaces is $0.2$.

Determine the acceleration of the $10 \text{ kg}$ block.

## Theory

The lower block experiences two friction forces opposing its motion:

1. Friction with the ground.
2. Friction with the upper block.

Since the upper block is tied to the wall, the lower block slides relative to it, so the friction between the two blocks is kinetic.

Newton's second law for the lower block is

$$
\sum F_x = m a
$$

## Step-by-Step Solution

### Given Data

Lower block mass:

$$
m_1 = 10 \text{ kg}
$$

Upper block mass:

$$
m_2 = 5 \text{ kg}
$$

Applied force:

$$
F = 45 \text{ N}
$$

Coefficient of kinetic friction:

$$
\mu_k = 0.2
$$

Take

$$
g = 9.81 \text{ m/s}^2
$$

### Friction Between Lower Block and Ground

The ground supports both blocks, so the normal force from the ground is

$$
N_{\text{ground}} = (m_1 + m_2)g
$$

Thus,

$$
N_{\text{ground}} = (10 + 5)9.81 = 147.15 \text{ N}
$$

The kinetic friction with the ground is

$$
f_{\text{ground}} = \mu_k N_{\text{ground}}
$$

$$
f_{\text{ground}} = 0.2 \cdot 147.15 = 29.43 \text{ N}
$$

### Friction Between the Two Blocks

The upper block presses on the lower block with normal force

$$
N_{\text{top}} = m_2 g
$$

$$
N_{\text{top}} = 5 \cdot 9.81 = 49.05 \text{ N}
$$

So the kinetic friction between them is

$$
f_{\text{top}} = \mu_k N_{\text{top}}
$$

$$
f_{\text{top}} = 0.2 \cdot 49.05 = 9.81 \text{ N}
$$

This friction acts opposite the motion of the lower block.

### Net Force on the Lower Block

The net horizontal force on the $10 \text{ kg}$ block is

$$
F_{\text{net}} = F - f_{\text{ground}} - f_{\text{top}}
$$

$$
F_{\text{net}} = 45 - 29.43 - 9.81
$$

$$
F_{\text{net}} = 5.76 \text{ N}
$$

### Acceleration of the Lower Block

Apply Newton's second law to the lower block:

$$
F_{\text{net}} = m_1 a
$$

Thus,

$$
a = \frac{F_{\text{net}}}{m_1}
$$

$$
a = \frac{5.76}{10} = 0.576 \text{ m/s}^2
$$

## Final Result

The acceleration of the $10 \text{ kg}$ block is

$$
a \approx 0.58 \text{ m/s}^2
$$

## Interpretation

The applied force is largely balanced by the two friction forces. Because the upper block is tied to the wall, the lower block must slide under it, which adds an additional friction force and significantly reduces the acceleration.
