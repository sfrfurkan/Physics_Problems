# Task 09 – Damped Harmonic Oscillator

## Problem Statement

For the damped oscillator equation

$$
m\frac{d^2 x}{dt^2} + b\frac{dx}{dt} + kx = 0
$$

prepare an interactive HTML animation with a slider for the damping parameter $b$ to visualize underdamped, critically damped, and overdamped motion. Include:

- the general solution,
- classification of damping cases,
- numerical solution using RK4,
- graph of $x(t)$,
- phase portrait.

## Theory

The damped oscillator equation is

$$
m\ddot{x} + b\dot{x} + kx = 0
$$

Dividing by $m$ gives

$$
\ddot{x} + \frac{b}{m}\dot{x} + \frac{k}{m}x = 0
$$

The characteristic equation is

$$
mr^2 + br + k = 0
$$

with roots

$$
r_{1,2} = \frac{-b \pm \sqrt{b^2 - 4mk}}{2m}
$$

The behavior depends on the discriminant

$$
\Delta = b^2 - 4mk
$$

### Underdamped case

If

$$
b^2 < 4mk
$$

the roots are complex:

$$
r = -\frac{b}{2m} \pm i\omega_d
$$

where

$$
\omega_d = \sqrt{\frac{k}{m} - \frac{b^2}{4m^2}}
$$

The solution is

$$
x(t) = e^{-bt/(2m)}\left(C_1 \cos(\omega_d t) + C_2 \sin(\omega_d t)\right)
$$

### Critically damped case

If

$$
b^2 = 4mk
$$

there is a repeated root

$$
r = -\frac{b}{2m}
$$

and the solution is

$$
x(t) = (C_1 + C_2 t)e^{-bt/(2m)}
$$

### Overdamped case

If

$$
b^2 > 4mk
$$

there are two distinct real roots

$$
r_{1,2} = \frac{-b \pm \sqrt{b^2 - 4mk}}{2m}
$$

and the solution is

$$
x(t) = C_1 e^{r_1 t} + C_2 e^{r_2 t}
$$

## Step-by-Step Solution

To solve numerically, rewrite the second-order equation as a first-order system. Define

$$
v = \dot{x}
$$

Then

$$
\dot{x} = v
$$

$$
\dot{v} = -\frac{b}{m}v - \frac{k}{m}x
$$

This system is integrated with the fourth-order Runge–Kutta method.

The critical damping value is

$$
b_c = 2\sqrt{mk}
$$

For fixed $m$ and $k$:

- $b < b_c$ corresponds to underdamped motion,
- $b = b_c$ corresponds to critical damping,
- $b > b_c$ corresponds to overdamped motion.

The interactive notebook code below visualizes these regimes.

## Final Result

The following HTML file implements the requested simulation.

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Damped Harmonic Oscillator</title>
<style>
  body {
    font-family: Arial, sans-serif;
    margin: 20px;
    background: #f4f4f4;
    color: #222;
  }
  h1, h2 {
    margin-bottom: 8px;
  }
  .controls, .info {
    background: white;
    padding: 12px;
    border-radius: 10px;
    margin-bottom: 16px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.08);
  }
  .row {
    display: flex;
    gap: 16px;
    flex-wrap: wrap;
  }
  canvas {
    background: white;
    border-radius: 10px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.08);
  }
  label {
    display: block;
    margin: 8px 0;
  }
  .small {
    font-size: 0.95rem;
    color: #444;
  }
</style>
</head>
<body>
  <h1>Damped Harmonic Oscillator</h1>

  <div class="controls">
    <label>
      Damping coefficient b:
      <input type="range" id="bSlider" min="0" max="20" step="0.01" value="1">
      <span id="bValue">1.00</span>
    </label>

    <label>
      Mass m:
      <input type="range" id="mSlider" min="0.5" max="5" step="0.1" value="1">
      <span id="mValue">1.0</span>
    </label>

    <label>
      Spring constant k:
      <input type="range" id="kSlider" min="0.5" max="20" step="0.1" value="10">
      <span id="kValue">10.0</span>
    </label>

    <label>
      Initial position x(0):
      <input type="range" id="x0Slider" min="-2" max="2" step="0.01" value="1">
      <span id="x0Value">1.00</span>
    </label>

    <label>
      Initial velocity v(0):
      <input type="range" id="v0Slider" min="-5" max="5" step="0.01" value="0">
      <span id="v0Value">0.00</span>
    </label>
  </div>

  <div class="info">
    <div><strong>Critical damping:</strong> <span id="bcValue"></span></div>
    <div><strong>Classification:</strong> <span id="classValue"></span></div>
    <div class="small">
      Equation solved numerically:
      m x'' + b x' + k x = 0
    </div>
  </div>

  <div class="row">
    <canvas id="motionCanvas" width="420" height="220"></canvas>
    <canvas id="xtCanvas" width="420" height="220"></canvas>
    <canvas id="phaseCanvas" width="420" height="220"></canvas>
  </div>

<script>
const motionCanvas = document.getElementById("motionCanvas");
const xtCanvas = document.getElementById("xtCanvas");
const phaseCanvas = document.getElementById("phaseCanvas");

const motionCtx = motionCanvas.getContext("2d");
const xtCtx = xtCanvas.getContext("2d");
const phaseCtx = phaseCanvas.getContext("2d");

const bSlider = document.getElementById("bSlider");
const mSlider = document.getElementById("mSlider");
const kSlider = document.getElementById("kSlider");
const x0Slider = document.getElementById("x0Slider");
const v0Slider = document.getElementById("v0Slider");

const bValue = document.getElementById("bValue");
const mValue = document.getElementById("mValue");
const kValue = document.getElementById("kValue");
const x0Value = document.getElementById("x0Value");
const v0Value = document.getElementById("v0Value");
const bcValue = document.getElementById("bcValue");
const classValue = document.getElementById("classValue");

let solution = [];
let timeIndex = 0;
let lastTime = 0;
const dt = 0.01;
const TMAX = 20;

function deriv(state, params) {
  const [x, v] = state;
  const {m, b, k} = params;
  return [v, -(b/m) * v - (k/m) * x];
}

function rk4Step(state, h, params) {
  const k1 = deriv(state, params);
  const s2 = [state[0] + 0.5*h*k1[0], state[1] + 0.5*h*k1[1]];
  const k2 = deriv(s2, params);
  const s3 = [state[0] + 0.5*h*k2[0], state[1] + 0.5*h*k2[1]];
  const k3 = deriv(s3, params);
  const s4 = [state[0] + h*k3[0], state[1] + h*k3[1]];
  const k4 = deriv(s4, params);

  return [
    state[0] + (h/6)*(k1[0] + 2*k2[0] + 2*k3[0] + k4[0]),
    state[1] + (h/6)*(k1[1] + 2*k2[1] + 2*k3[1] + k4[1])
  ];
}

function computeSolution() {
  const m = parseFloat(mSlider.value);
  const b = parseFloat(bSlider.value);
  const k = parseFloat(kSlider.value);
  const x0 = parseFloat(x0Slider.value);
  const v0 = parseFloat(v0Slider.value);

  solution = [];
  let state = [x0, v0];
  for (let t = 0; t <= TMAX; t += dt) {
    solution.push({t, x: state[0], v: state[1]});
    state = rk4Step(state, dt, {m, b, k});
  }
  timeIndex = 0;

  const bc = 2 * Math.sqrt(m * k);
  bcValue.textContent = bc.toFixed(3);

  let classification = "";
  const eps = 1e-3;
  if (Math.abs(b - bc) < eps) {
    classification = "Critically damped";
  } else if (b < bc) {
    classification = "Underdamped";
  } else {
    classification = "Overdamped";
  }
  classValue.textContent = classification;
}

function clearCanvas(ctx, canvas, title) {
  ctx.clearRect(0, 0, canvas.width, canvas.height);
  ctx.fillStyle = "#111";
  ctx.font = "16px Arial";
  ctx.fillText(title, 10, 20);
}

function drawMotion() {
  clearCanvas(motionCtx, motionCanvas, "Mass-spring motion");
  const midY = motionCanvas.height / 2;

  motionCtx.strokeStyle = "#666";
  motionCtx.beginPath();
  motionCtx.moveTo(40, midY);
  motionCtx.lineTo(380, midY);
  motionCtx.stroke();

  const x = solution[Math.min(timeIndex, solution.length - 1)].x;
  const px = 210 + x * 80;

  motionCtx.beginPath();
  motionCtx.moveTo(40, midY);
  for (let i = 0; i < 18; i++) {
    const sx = 40 + i * (px - 40) / 18;
    const sy = midY + (i % 2 === 0 ? -12 : 12);
    motionCtx.lineTo(sx, sy);
  }
  motionCtx.lineTo(px, midY);
  motionCtx.strokeStyle = "#333";
  motionCtx.stroke();

  motionCtx.fillStyle = "#2b6cb0";
  motionCtx.fillRect(px, midY - 20, 40, 40);
}

function drawXT() {
  clearCanvas(xtCtx, xtCanvas, "x(t)");
  const w = xtCanvas.width;
  const h = xtCanvas.height;

  xtCtx.strokeStyle = "#bbb";
  xtCtx.beginPath();
  xtCtx.moveTo(40, h/2);
  xtCtx.lineTo(w - 10, h/2);
  xtCtx.moveTo(40, 30);
  xtCtx.lineTo(40, h - 20);
  xtCtx.stroke();

  let maxAbsX = 1;
  for (const p of solution) {
    maxAbsX = Math.max(maxAbsX, Math.abs(p.x));
  }

  xtCtx.strokeStyle = "#c53030";
  xtCtx.beginPath();
  for (let i = 0; i < solution.length; i++) {
    const p = solution[i];
    const X = 40 + (p.t / TMAX) * (w - 50);
    const Y = h/2 - (p.x / maxAbsX) * (h/2 - 40);
    if (i === 0) xtCtx.moveTo(X, Y);
    else xtCtx.lineTo(X, Y);
  }
  xtCtx.stroke();

  const curr = solution[Math.min(timeIndex, solution.length - 1)];
  const cx = 40 + (curr.t / TMAX) * (w - 50);
  const cy = h/2 - (curr.x / maxAbsX) * (h/2 - 40);

  xtCtx.fillStyle = "#111";
  xtCtx.beginPath();
  xtCtx.arc(cx, cy, 4, 0, 2*Math.PI);
  xtCtx.fill();
}

function drawPhase() {
  clearCanvas(phaseCtx, phaseCanvas, "Phase portrait: v versus x");
  const w = phaseCanvas.width;
  const h = phaseCanvas.height;

  let maxAbsX = 1;
  let maxAbsV = 1;
  for (const p of solution) {
    maxAbsX = Math.max(maxAbsX, Math.abs(p.x));
    maxAbsV = Math.max(maxAbsV, Math.abs(p.v));
  }

  phaseCtx.strokeStyle = "#bbb";
  phaseCtx.beginPath();
  phaseCtx.moveTo(40, h/2);
  phaseCtx.lineTo(w - 10, h/2);
  phaseCtx.moveTo(w/2, 30);
  phaseCtx.lineTo(w/2, h - 20);
  phaseCtx.stroke();

  phaseCtx.strokeStyle = "#2f855a";
  phaseCtx.beginPath();
  for (let i = 0; i < solution.length; i++) {
    const p = solution[i];
    const X = w/2 + (p.x / maxAbsX) * (w/2 - 50);
    const Y = h/2 - (p.v / maxAbsV) * (h/2 - 40);
    if (i === 0) phaseCtx.moveTo(X, Y);
    else phaseCtx.lineTo(X, Y);
  }
  phaseCtx.stroke();

  const curr = solution[Math.min(timeIndex, solution.length - 1)];
  const cx = w/2 + (curr.x / maxAbsX) * (w/2 - 50);
  const cy = h/2 - (curr.v / maxAbsV) * (h/2 - 40);

  phaseCtx.fillStyle = "#111";
  phaseCtx.beginPath();
  phaseCtx.arc(cx, cy, 4, 0, 2*Math.PI);
  phaseCtx.fill();
}

function updateLabels() {
  bValue.textContent = parseFloat(bSlider.value).toFixed(2);
  mValue.textContent = parseFloat(mSlider.value).toFixed(1);
  kValue.textContent = parseFloat(kSlider.value).toFixed(1);
  x0Value.textContent = parseFloat(x0Slider.value).toFixed(2);
  v0Value.textContent = parseFloat(v0Slider.value).toFixed(2);
}

function rebuild() {
  updateLabels();
  computeSolution();
}

[bSlider, mSlider, kSlider, x0Slider, v0Slider].forEach(el => {
  el.addEventListener("input", rebuild);
});

function animate(timestamp) {
  if (!lastTime) lastTime = timestamp;
  const elapsed = timestamp - lastTime;
  if (elapsed > 25) {
    timeIndex = (timeIndex + 1) % solution.length;
    lastTime = timestamp;
  }

  drawMotion();
  drawXT();
  drawPhase();
  requestAnimationFrame(animate);
}

rebuild();
requestAnimationFrame(animate);
</script>
</body>
</html>
~~~

## Interpretation

The parameter $b$ controls how strongly energy is dissipated.

- For small $b$, the system oscillates while its amplitude decays.
- At the critical value $b_c = 2\sqrt{mk}$, the system returns to equilibrium as fast as possible without oscillating.
- For $b > b_c$, the motion becomes non-oscillatory and relaxes more slowly.

The phase portrait changes from a spiral (underdamped) to a degenerate critical curve and then to a non-spiraling overdamped approach to the origin.

---
