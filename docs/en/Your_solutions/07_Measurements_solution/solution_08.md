# Task 08 – Mass-Spring Measurements

## Problem Statement

Generate a simulator of a mass suspended on a spring in HTML with a timing function.

Treat the mass as a given value with zero uncertainty. Perform a series of $10$ time measurements for $10$ complete oscillations.

Use the collected data to calculate:

- mean period
- standard deviation
- spring constant
- uncertainty in the spring constant

## Theory

For a mass attached to an ideal spring, the period of oscillation is

$$
T = 2\pi \sqrt{\frac{m}{k}}
$$

Solving for the spring constant gives

$$
k = \frac{4\pi^2 m}{T^2}
$$

If the mass has zero uncertainty, then the uncertainty in $k$ comes only from the uncertainty in $T$.

Since

$$
k \propto T^{-2}
$$

the relative uncertainty is

$$
\frac{\Delta k}{k} = 2\frac{\Delta T}{T}
$$

Thus,

$$
\Delta k = k\left(2\frac{\Delta T}{T}\right)
$$

If $10$ trials are performed, the mean period is

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

Save the following code as `mass_spring_simulator.html`.

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Mass-Spring Oscillation Simulator</title>
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

<h1>Mass-Spring Oscillation Simulator</h1>

<p>Mass: <input id="mass" type="number" value="0.50" step="0.01"> kg</p>
<p>Spring constant used by simulator: <input id="springK" type="number" value="20" step="1"> N/m</p>

<button onclick="startSimulation()">Start Simulation</button>
<button onclick="stopwatchStart()">Start Stopwatch</button>
<button onclick="stopwatchStop()">Stop Stopwatch</button>
<button onclick="resetStopwatch()">Reset Stopwatch</button>

<p>Stopwatch Time: <span id="timeDisplay">0.00</span> s</p>

<canvas id="canvas" width="400" height="500"></canvas>

<script>
const canvas = document.getElementById("canvas");
const ctx = canvas.getContext("2d");

let running = false;
let startTime;
let stopwatchStartTime;
let stopwatchRunning = false;
let stopwatchElapsed = 0;

function drawSpring(x, y0, y1) {
    const coils = 12;
    const width = 30;
    const length = y1 - y0;
    ctx.beginPath();
    ctx.moveTo(x, y0);
    for (let i = 0; i <= coils; i++) {
        let y = y0 + i * length / coils;
        let dx = i % 2 === 0 ? -width / 2 : width / 2;
        ctx.lineTo(x + dx, y);
    }
    ctx.lineTo(x, y1);
    ctx.stroke();
}

function animate(timestamp) {
    if (!running) return;

    const m = parseFloat(document.getElementById("mass").value);
    const k = parseFloat(document.getElementById("springK").value);
    const omega = Math.sqrt(k / m);

    if (!startTime) startTime = timestamp;
    const t = (timestamp - startTime) / 1000;

    const amplitude = 80;
    const equilibriumY = 250;
    const y = equilibriumY + amplitude * Math.cos(omega * t);

    ctx.clearRect(0, 0, canvas.width, canvas.height);

    ctx.lineWidth = 2;
    ctx.beginPath();
    ctx.moveTo(200, 30);
    ctx.lineTo(200, 60);
    ctx.stroke();

    drawSpring(200, 60, y - 30);

    ctx.fillStyle = "gray";
    ctx.fillRect(160, y - 30, 80, 60);

    ctx.fillStyle = "black";
    ctx.fillText("Count 10 complete oscillations manually", 90, 470);

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

Assume the mass is

$$
m = 0.50\ \mathrm{kg}
$$

Example measured times for $10$ complete oscillations are:

$$
4.98,\ 5.02,\ 5.01,\ 4.99,\ 5.04,\ 5.00,\ 4.97,\ 5.03,\ 5.01,\ 4.99\ \mathrm{s}
$$

Each measured time is for $10$ oscillations, so each period is

$$
T_i = \frac{t_i}{10}
$$

The periods are

$$
0.498,\ 0.502,\ 0.501,\ 0.499,\ 0.504,\ 0.500,\ 0.497,\ 0.503,\ 0.501,\ 0.499\ \mathrm{s}
$$

The mean period is

$$
\bar{T} = 0.5004\ \mathrm{s}
$$

The sample standard deviation is

$$
\sigma_T = 0.00217\ \mathrm{s}
$$

The uncertainty in the mean period is

$$
\Delta T = \frac{0.00217}{\sqrt{10}}
$$

$$
\Delta T = 0.00069\ \mathrm{s}
$$

The spring constant is

$$
k = \frac{4\pi^2 m}{\bar{T}^2}
$$

$$
k = \frac{4\pi^2(0.50)}{(0.5004)^2}
$$

$$
k = 78.83\ \mathrm{N/m}
$$

The uncertainty in $k$ is

$$
\Delta k = k\left(2\frac{\Delta T}{\bar{T}}\right)
$$

$$
\Delta k = 78.83\left(2\frac{0.00069}{0.5004}\right)
$$

$$
\Delta k = 0.22\ \mathrm{N/m}
$$

## Final Result

$$
\bar{T} = (0.5004 \pm 0.0007)\ \mathrm{s}
$$

$$
k = (78.83 \pm 0.22)\ \mathrm{N/m}
$$

## Interpretation

The spring constant is determined from the measured oscillation period. Because $k$ depends on $T^{-2}$, a small uncertainty in the period produces twice that relative uncertainty in the spring constant.
