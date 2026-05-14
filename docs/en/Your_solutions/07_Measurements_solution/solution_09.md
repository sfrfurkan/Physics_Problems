# Task 09 – Pendulum Measurements

## Problem Statement

Create a simple pendulum simulator in HTML equipped with a stopwatch for manual timing.

Assume the string length is exact. Perform $10$ measurements of the time taken for $10$ complete oscillations.

Use the results to calculate:

- mean period
- standard deviation
- acceleration due to gravity
- uncertainty in the result

## Theory

For a simple pendulum with small oscillations, the period is

$$
T = 2\pi \sqrt{\frac{L}{g}}
$$

Solving for $g$ gives

$$
g = \frac{4\pi^2 L}{T^2}
$$

If the length has zero uncertainty, the uncertainty in $g$ comes from the uncertainty in $T$.

Since

$$
g \propto T^{-2}
$$

the relative uncertainty is

$$
\frac{\Delta g}{g} = 2\frac{\Delta T}{T}
$$

Thus,

$$
\Delta g = g\left(2\frac{\Delta T}{T}\right)
$$

The mean period is

$$
\bar{T} = \frac{1}{N}\sum_{i=1}^{N}T_i
$$

The sample standard deviation is

$$
\sigma_T = \sqrt{\frac{1}{N-1}\sum_{i=1}^{N}(T_i-\bar{T})^2}
$$

The uncertainty in the mean period is

$$
\Delta T = \frac{\sigma_T}{\sqrt{N}}
$$

## HTML Simulator

Save the following code as `pendulum_simulator.html`.

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Simple Pendulum Simulator</title>
<style>
body {
    font-family: Arial, sans-serif;
    text-align: center;
    background: #f4f4f4;
}
canvas {
    background: white;
    border: 1px solid #333;
    margin-top: 20px;
}
button {
    margin: 8px;
    padding: 8px 16px;
    font-size: 16px;
}
input {
    padding: 5px;
    width: 80px;
}
</style>
</head>
<body>

<h1>Simple Pendulum Simulator</h1>

<p>Length: <input id="length" type="number" value="1.00" step="0.01"> m</p>

<button onclick="startSimulation()">Start Simulation</button>
<button onclick="stopwatchStart()">Start Stopwatch</button>
<button onclick="stopwatchStop()">Stop Stopwatch</button>
<button onclick="resetStopwatch()">Reset Stopwatch</button>

<p>Stopwatch Time: <span id="timeDisplay">0.00</span> s</p>

<canvas id="canvas" width="500" height="500"></canvas>

<script>
const canvas = document.getElementById("canvas");
const ctx = canvas.getContext("2d");

let running = false;
let startTime;
let stopwatchStartTime;
let stopwatchRunning = false;
let stopwatchElapsed = 0;

function animate(timestamp) {
    if (!running) return;

    const L = parseFloat(document.getElementById("length").value);
    const g = 9.81;
    const omega = Math.sqrt(g / L);

    if (!startTime) startTime = timestamp;
    const t = (timestamp - startTime) / 1000;

    const thetaMax = 0.25;
    const theta = thetaMax * Math.cos(omega * t);

    const pivotX = 250;
    const pivotY = 80;
    const scale = 300;
    const stringLength = L * scale;

    const bobX = pivotX + stringLength * Math.sin(theta);
    const bobY = pivotY + stringLength * Math.cos(theta);

    ctx.clearRect(0, 0, canvas.width, canvas.height);

    ctx.beginPath();
    ctx.arc(pivotX, pivotY, 5, 0, 2 * Math.PI);
    ctx.fill();

    ctx.beginPath();
    ctx.moveTo(pivotX, pivotY);
    ctx.lineTo(bobX, bobY);
    ctx.stroke();

    ctx.beginPath();
    ctx.arc(bobX, bobY, 20, 0, 2 * Math.PI);
    ctx.fillStyle = "gray";
    ctx.fill();

    ctx.fillStyle = "black";
    ctx.fillText("Count 10 complete oscillations manually", 140, 470);

    requestAnimationFrame(animate);
}

function startSimulation() {
    running = true;
    startTime = null;
    requestAnimationFrame(animate);
}

function stopwatchStart() {
    if (!stopwatchRunning) {
        stopwatchRunning = true;
        stopwatchStartTime = Date.now() - stopwatchElapsed;
        updateStopwatch();
    }
}

function stopwatchStop() {
    stopwatchRunning = false;
    stopwatchElapsed = Date.now() - stopwatchStartTime;
}

function resetStopwatch() {
    stopwatchRunning = false;
    stopwatchElapsed = 0;
    document.getElementById("timeDisplay").textContent = "0.00";
}

function updateStopwatch() {
    if (stopwatchRunning) {
        stopwatchElapsed = Date.now() - stopwatchStartTime;
        document.getElementById("timeDisplay").textContent = (stopwatchElapsed / 1000).toFixed(2);
        requestAnimationFrame(updateStopwatch);
    }
}
</script>

</body>
</html>
```

## Step-by-Step Solution

Assume the pendulum length is

$$
L = 1.00\ \mathrm{m}
$$

Example measured times for $10$ complete oscillations are:

$$
20.05,\ 20.12,\ 20.01,\ 20.08,\ 20.10,\ 20.04,\ 20.06,\ 20.11,\ 20.03,\ 20.09\ \mathrm{s}
$$

Each period is

$$
T_i = \frac{t_i}{10}
$$

The periods are

$$
2.005,\ 2.012,\ 2.001,\ 2.008,\ 2.010,\ 2.004,\ 2.006,\ 2.011,\ 2.003,\ 2.009\ \mathrm{s}
$$

The mean period is

$$
\bar{T} = 2.0069\ \mathrm{s}
$$

The sample standard deviation is

$$
\sigma_T = 0.00366\ \mathrm{s}
$$

The uncertainty in the mean period is

$$
\Delta T = \frac{0.00366}{\sqrt{10}}
$$

$$
\Delta T = 0.00116\ \mathrm{s}
$$

The acceleration due to gravity is

$$
g = \frac{4\pi^2 L}{\bar{T}^2}
$$

$$
g = \frac{4\pi^2(1.00)}{(2.0069)^2}
$$

$$
g = 9.80\ \mathrm{m/s^2}
$$

The uncertainty is

$$
\Delta g = g\left(2\frac{\Delta T}{\bar{T}}\right)
$$

$$
\Delta g = 9.80\left(2\frac{0.00116}{2.0069}\right)
$$

$$
\Delta g = 0.011\ \mathrm{m/s^2}
$$

## Final Result

$$
\bar{T} = (2.0069 \pm 0.0012)\ \mathrm{s}
$$

$$
g = (9.80 \pm 0.01)\ \mathrm{m/s^2}
$$

## Interpretation

The calculated value of $g$ is close to the accepted value of approximately $9.81\ \mathrm{m/s^2}$. The uncertainty is small because the timing was repeated several times and averaged.

For a real-life experiment, the same procedure can be used. The measured string length should be recorded, and the period should be calculated from repeated measurements of $10$ complete oscillations.
