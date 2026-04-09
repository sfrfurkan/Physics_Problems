# Task 10 – Animation: Wave Sources

## Problem Statement

Write an HTML animation in which the user can place dots that act as sources of waves of the form

$$
u(\vec{r},t) = A |\vec{r} - \vec{r}_0|^{\alpha} \sin\left(k|\vec{r} - \vec{r}_0| - \omega t\right)
$$

where $\vec{r}_0$ is the source position and $\alpha \in [0,2]$. The animation must show the superposition of waves from all dots.

## Theory

If there are multiple sources located at positions $\vec{r}_{0,i}$, then by the superposition principle the total field is

$$
u_{\text{tot}}(\vec{r},t) = \sum_i A |\vec{r} - \vec{r}_{0,i}|^{\alpha} \sin\left(k|\vec{r} - \vec{r}_{0,i}| - \omega t\right)
$$

The animation samples this field on a two-dimensional grid and maps the wave amplitude to color.

## Step-by-Step Solution

The following HTML program allows the user to click on the canvas to add sources. It includes controls for:

- amplitude $A$,
- wavelength $\lambda$,
- angular frequency $\omega$,
- exponent $\alpha$.

The displayed field is the sum of contributions from all sources.

## Final Result

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Wave Sources Superposition</title>
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
    cursor: crosshair;
    box-shadow: 0 2px 8px rgba(0,0,0,0.08);
  }
  label {
    display: block;
    margin: 8px 0;
  }
  button {
    margin-right: 8px;
  }
</style>
</head>
<body>
  <h1>Wave Sources Superposition</h1>

  <div class="panel">
    <label>
      Amplitude A:
      <input type="range" id="aSlider" min="0.1" max="5" step="0.1" value="1">
      <span id="aValue">1.0</span>
    </label>

    <label>
      Wavelength λ:
      <input type="range" id="lambdaSlider" min="10" max="120" step="1" value="40">
      <span id="lambdaValue">40</span>
    </label>

    <label>
      Angular frequency ω:
      <input type="range" id="omegaSlider" min="0.5" max="12" step="0.1" value="4">
      <span id="omegaValue">4.0</span>
    </label>

    <label>
      Exponent α:
      <input type="range" id="alphaSlider" min="0" max="2" step="0.01" value="0">
      <span id="alphaValue">0.00</span>
    </label>

    <button id="clearBtn">Clear sources</button>
    <span>Click on the canvas to add wave sources.</span>
  </div>

  <canvas id="canvas" width="700" height="500"></canvas>

<script>
const canvas = document.getElementById("canvas");
const ctx = canvas.getContext("2d");
const width = canvas.width;
const height = canvas.height;

const aSlider = document.getElementById("aSlider");
const lambdaSlider = document.getElementById("lambdaSlider");
const omegaSlider = document.getElementById("omegaSlider");
const alphaSlider = document.getElementById("alphaSlider");

const aValue = document.getElementById("aValue");
const lambdaValue = document.getElementById("lambdaValue");
const omegaValue = document.getElementById("omegaValue");
const alphaValue = document.getElementById("alphaValue");

const clearBtn = document.getElementById("clearBtn");

let sources = [];
let time = 0;
const gridStep = 4;

function updateLabels() {
  aValue.textContent = parseFloat(aSlider.value).toFixed(1);
  lambdaValue.textContent = lambdaSlider.value;
  omegaValue.textContent = parseFloat(omegaSlider.value).toFixed(1);
  alphaValue.textContent = parseFloat(alphaSlider.value).toFixed(2);
}

canvas.addEventListener("click", (e) => {
  const rect = canvas.getBoundingClientRect();
  const x = e.clientX - rect.left;
  const y = e.clientY - rect.top;
  sources.push({x, y});
});

clearBtn.addEventListener("click", () => {
  sources = [];
});

function colorMap(value) {
  const c = Math.max(-1, Math.min(1, value));
  const r = c > 0 ? Math.floor(255 * c) : 0;
  const b = c < 0 ? Math.floor(-255 * c) : 0;
  const g = 40;
  return `rgb(${r},${g},${b})`;
}

function drawField() {
  const A = parseFloat(aSlider.value);
  const lambda = parseFloat(lambdaSlider.value);
  const omega = parseFloat(omegaSlider.value);
  const alpha = parseFloat(alphaSlider.value);
  const k = 2 * Math.PI / lambda;

  for (let y = 0; y < height; y += gridStep) {
    for (let x = 0; x < width; x += gridStep) {
      let u = 0;

      for (const s of sources) {
        const dx = x - s.x;
        const dy = y - s.y;
        let r = Math.sqrt(dx*dx + dy*dy);
        if (r < 1) r = 1;
        u += A * Math.pow(r, alpha) * Math.sin(k * r - omega * time);
      }

      const scaled = Math.tanh(u / 20);
      ctx.fillStyle = colorMap(scaled);
      ctx.fillRect(x, y, gridStep, gridStep);
    }
  }

  for (const s of sources) {
    ctx.beginPath();
    ctx.arc(s.x, s.y, 5, 0, 2*Math.PI);
    ctx.fillStyle = "white";
    ctx.fill();
  }
}

function animate() {
  updateLabels();
  drawField();
  time += 0.03;
  requestAnimationFrame(animate);
}

updateLabels();
animate();
</script>
</body>
</html>
~~~

## Interpretation

The total field is a sum of all partial waves. As more sources are added, constructive and destructive interference patterns emerge. The exponent $\alpha$ modifies how strongly the amplitude changes with distance from each source.

---
