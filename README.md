# magri.me

Real-time multi-wavelength wave superposition and optical phase vortex simulator.

Live website: [https://magri.me](https://magri.me)

## Features
- **Real-Time WebGL 2.0 Engine**: Renders 30,906 Hermite-Gaussian modes ($N=100$) across 6 wavelengths in real time at 60–120 FPS.
- **Edge-to-Edge Fullscreen**: Aspect-ratio-preserving cover mode with smooth boundary taper.
- **Live Randomization**: Generates a unique physical parameter set (spatial orientation, relative spectral phases, amplitude weights, and static sensor noise) on each load or click.
- **Zero Dependencies**: Pure HTML5 and WebGL2 shader with zero external libraries or frameworks.

## Controls
- **Click / Tap**: Generate a fresh randomized wavefield.
- **Double Click**: Toggle fullscreen.
- **C**: Toggle color mode between **Phase Color Wheel** (phase as cyclic hue, amplitude as brightness) and **Single Gradient** (Inferno).
- **Arrow Up / Down**: Increase / decrease multi-wavelength spectral participation.
- **Arrow Left / Right**: Decrease / increase higher-order spatial mode variance.
- **Ctrl + Arrow Up / Down**: Increase / decrease dynamic sensor noise.
- **Ctrl + Arrow Left / Right**: Decrease / increase beam divergence scale.
- **N**: Cycle sensor noise presets (0% &rarr; 3% &rarr; 6% &rarr; 10%).
- **Space**: Re-randomize wavefield parameters.
