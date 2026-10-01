# Module 2 — Wave Physics and Receive Beamforming

This module covers fundamental ultrasound wave physics and a basic
delay-and-sum receive beamforming implementation in MATLAB.

## Contents

### Exercise 1 — Wave fundamentals

`code/exercise-1-wave-fundamentals.m`

Topics covered:

- Sound speed in soft tissue, water, and bone
- One-way and round-trip travel-time calculations
- Frequency, wavelength, and sound-speed relationships
- Resolution versus penetration-depth trade-off
- Effects of using an incorrect assumed sound speed during imaging

The relationship between sound speed $c$, frequency $f$, and wavelength
$\lambda$ is:

```math
c = f\lambda
```

For pulse-echo imaging, depth is calculated from measured round-trip time:

```math
d = \frac{ct}{2}
```

### Exercise 2 — Receive beamforming

`code/exercise-2-receive-beamforming.m`

This exercise uses simulated channel data from a linear ultrasound array and
reconstructs an image of a point scatterer.

The workflow includes:

1. Simulating received channel data using K-Wave.
2. Beamforming an image with USTB for comparison.
3. Implementing geometric receive delays for every pixel and receive element.
4. Interpolating each channel signal at its calculated delay.
5. Summing delayed signals using delay-and-sum beamforming.
6. Comparing data before and after delay compensation.

For a pixel at $(x, z)$ and an array element at $(x_\mathrm{element}, z_\mathrm{element})$,
the receive delay is calculated from the propagation distance:

```math
t_\mathrm{rx} =
\frac{
\sqrt{
(x - x_\mathrm{element})^2 +
(z - z_\mathrm{element})^2
}
}{c}
```

where $c$ is the assumed sound speed.

Applying the calculated delays aligns echoes from the same scatterer across
the array. The aligned signals add constructively when summed, resulting in a
more focused response than directly summing the undelayed channel data.

## Requirements

Exercise 2 requires:

- MATLAB
- [K-Wave](https://www.k-wave.org/)
- [UltraSound Toolbox (USTB)](https://www.ustb.no/)

The helper function `run_kwave_simulation` and the required toolbox setup must
be available on the MATLAB path.

## Figures

Selected output figures can be found in `figures/`.

Suggested figures:

- Comparison between the USTB reconstruction and the custom beamformer
- Channel data before and after delay compensation
- Sum of delayed versus undelayed channel signals

## Attribution

The assignment framework and starter code were provided as course material.
My work includes completing the calculations, implementing the geometric
receive-delay expression, selecting the point-scatterer location, and
interpreting the beamforming results.
