# Task 11 – Animation: Two-Slit Interference

## Problem Statement

Write an HTML animation simulating Young's double-slit experiment. Two slits act as coherent point sources with displacement

$$
u(\vec{r},t) =
A |\vec{r} - \vec{r}_1| \sin\left(k|\vec{r} - \vec{r}_1| - \omega t\right)
+
A |\vec{r} - \vec{r}_2| \sin\left(k|\vec{r} - \vec{r}_2| - \omega t\right)
$$

The user should be able to change slit separation

$$
d = |\vec{r}_1 - \vec{r}_2|
$$

and wavelength $\lambda$, while the interference pattern is shown in real time.

## Theory

Two coherent sources emit waves with the same frequency and a fixed phase relation. The total field is the sum of the two waves. The interference pattern depends on the path difference

$$
\Delta r = |\vec{r} - \vec{r}_1| - |\vec{r} - \vec{r}_2|
$$

Constructive interference occurs when

$$
\Delta r = n\lambda
$$

and destructive interference occurs when

$$
\Delta r = \left(n+\frac{1}{2}\right)\lambda
$$

for integer $n$.

## Step-by-Step Solution

The following HTML program places two coherent sources at adjustable separation. The wavelength can be changed with a slider. The intensity pattern is updated continuously.

## Final Result

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Young Double-Slit Interference</title>
<style>
  body {
    font-family: Arial, sans-serif;
    margin: 20px;
    background: #f4f4f4;
    color: #222;
  }
  .panel {
    background: white;
    padding: 12px;
    border-radius: 10px;
    margin-bottom: 14px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.08);
  }
  canvas {
    background: black;
    border-radius: 10px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.08);
  }
  label {
    display: block;
    margin: 8px 0;
  }
</style>
</head>
<body>
  <h1>Young Double-Slit Interference</h1>

  <div class="panel">
    <label>
      Slit separation d:
      <input type="range" id="dSlider" min="10" max="250" step="1" value="80">
      <span id="dValue">80</span>
    </label>

    <label>
      Wavelength λ:
      <input type="range" id="lambdaSlider" min="10" max="120" step="1" value="40">
      <span id="lambdaValue">40</span>
    </label>

    <label>
      Amplitude A:
      <input type="range" id="aSlider" min="0.1" max="3" step="0.1" value="1">
      <span id="aValue">1.0</span>
    </label>

    <label>
      Angular frequency ω:
      <input type="range" id="omegaSlider" min="0.5" max="12" step="0.1" value="5">
      <span id="omegaValue">5.0</span>
    </label>
  </div>

  <canvas id="canvas" width="760" height="520"></canvas>

<script>
const canvas = document.getElementById("canvas");
const ctx = canvas.getContext("2d");
const width = canvas.width;
const height = canvas.height;

const dSlider = document.getElementById("dSlider");
const lambdaSlider = document.getElementById("lambdaSlider");
const aSlider = document.getElementById("aSlider");
const omegaSlider = document.getElementById("omegaSlider");

const dValue = document.getElementById("dValue");
const lambdaValue = document.getElementById("lambdaValue");
const aValue = document.getElementById("aValue");
const omegaValue = document.getElementById("omegaValue");

let time = 0;
const gridStep = 4;

function updateLabels() {
  dValue.textContent = dSlider.value;
  lambdaValue.textContent = lambdaSlider.value;
  aValue.textContent = parseFloat(aSlider.value).toFixed(1);
  omegaValue.textContent = parseFloat(omegaSlider.value).toFixed(1);
}

function colorMap(value) {
  const c = Math.max(-1, Math.min(1, value));
  const r = c > 0 ? Math.floor(255 * c) : 0;
  const b = c < 0 ? Math.floor(-255 * c) : 0;
  const g = Math.floor(80 + 120 * (1 - Math.abs(c)));
  return `rgb(${r},${g},${b})`;
}

function draw() {
  updateLabels();

  const d = parseFloat(dSlider.value);
  const lambda = parseFloat(lambdaSlider.value);
  const A = parseFloat(aSlider.value);
  const omega = parseFloat(omegaSlider.value);
  const k = 2 * Math.PI / lambda;

  const x0 = 120;
  const yMid = height / 2;

  const r1 = {x: x0, y: yMid - d/2};
  const r2 = {x: x0, y: yMid + d/2};

  for (let y = 0; y < height; y += gridStep) {
    for (let x = 0; x < width; x += gridStep) {
      let dx1 = x - r1.x;
      let dy1 = y - r1.y;
      let dx2 = x - r2.x;
      let dy2 = y - r2.y;

      let dist1 = Math.sqrt(dx1*dx1 + dy1*dy1);
      let dist2 = Math.sqrt(dx2*dx2 + dy2*dy2);

      if (dist1 < 1) dist1 = 1;
      if (dist2 < 1) dist2 = 1;

      const u =
        A * dist1 * Math.sin(k * dist1 - omega * time) +
        A * dist2 * Math.sin(k * dist2 - omega * time);

      const scaled = Math.tanh(u / 80);
      ctx.fillStyle = colorMap(scaled);
      ctx.fillRect(x, y, gridStep, gridStep);
    }
  }

  ctx.fillStyle = "white";
  ctx.fillRect(x0 - 6, 0, 12, height);

  ctx.fillStyle = "black";
  ctx.fillRect(x0 - 6, 0, 12, r1.y - 8);
  ctx.fillRect(x0 - 6, r1.y + 8, 12, r2.y - r1.y - 16);
  ctx.fillRect(x0 - 6, r2.y + 8, 12, height - (r2.y + 8));

  ctx.fillStyle = "yellow";
  ctx.beginPath();
  ctx.arc(r1.x, r1.y, 5, 0, 2*Math.PI);
  ctx.fill();

  ctx.beginPath();
  ctx.arc(r2.x, r2.y, 5, 0, 2*Math.PI);
  ctx.fill();

  time += 0.03;
  requestAnimationFrame(draw);
}

draw();
</script>
</body>
</html>
~~~

## Interpretation

As the slit separation $d$ changes, the spacing of the interference fringes changes. Increasing the wavelength $\lambda$ generally broadens the fringe pattern, while decreasing $\lambda$ produces more closely spaced fringes.

---

# Summary

## Key Results

1. Wave in air:

$$
\lambda_{\text{air}} \approx 0.78 \,\text{m}
$$

2. Wave in water:

$$
\lambda_{\text{water}} \approx 3.37 \,\text{m}
$$

3. Wave speed on string:

$$
v = 422.4 \,\text{m/s}
$$

4. Standing wave from superposition:

$$
y(x,t) = 2A\sin(kx)\cos(\omega t)
$$

with nodes at

$$
x_n = \frac{n\lambda}{2}
$$

5. Phase difference for separation $\lambda/3$:

$$
\Delta \phi = \frac{2\pi}{3}
$$

6. Echo distance:

$$
d = 171.5 \,\text{m}
$$

7. For $y(x,t)=0.05\sin(2\pi x - 50\pi t)$:

$$
A = 0.05 \,\text{m}, \quad \lambda = 1 \,\text{m}, \quad f = 25 \,\text{Hz}, \quad v = 25 \,\text{m/s}
$$

8. Standing wave with four antinodes on $L=0.80 \,\text{m}$:

$$
\lambda = 0.40 \,\text{m}
$$

9. Traveling-wave functions among the proposed forms:

$$
A(x-vt)^2
$$

and

$$
A\log(x+vt)
$$

The three HTML simulations provide interactive visualizations for damped motion, multiple wave sources, and two-slit interference.
