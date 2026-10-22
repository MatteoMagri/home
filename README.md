# magri.me

Real-time partially coherent optical beam simulator and multi-wavelength wave superposition engine.

Live website: **[https://magri.me](https://magri.me)**

---

## Directory Structure

```
home/
├── assets/
│   ├── js/
│   │   └── beam_data.js        # 30-component metadata & pre-calibrated parameters
│   └── textures/
│       ├── tex0.png            # 15 packed RGBA uint8 textures (2 complex wavefields per texture)
│       ├── ...
│       └── tex14.png
├── CNAME                       # magri.me custom domain
├── index.html                  # Core WebGL 2.0 application
└── README.md                   # This documentation
```

---

## Features
- **Real-Time WebGL 2.0 Engine**: Renders 30 spectral beam components distributed symmetrically around carrier $k=1.000$ with relative energy bandwidth $\Delta E/E \le 15.0\%$.
- **Texture Packing**: Single `TEXTURE_2D_ARRAY` on `TEXTURE0` with GPU $\mathcal{C}^2$-continuous bicubic B-spline interpolation, achieving rock-solid 60 FPS across desktop and mobile.
- **Top Information Bar**: Displays live $\Delta E/E$ ($0.0\%$ to $15.0\%$), Coherence fraction ($1.0\%$ to $100\%$), Transversal coherence length ($35.4/\text{divScale}$), and fixed $100\lambda$ scale bar.
- **Multiple Optical Visualizations**:
  - **Amplitude Modulus**: Perceptually uniform *Inferno* colormap.
  - **Phase Color Wheel**: Optical phase as cyclic hue, amplitude as brightness.
  - **Real Part (Bipolar)**: Optical carrier oscillation ($20$ cycles/loop) with Red crests, Blue troughs, and Black nodes.
- **Dynamic Mode Waist Expansion**: Gaussian waist smoothly expands between single fundamental speckle ($35.4\text{ px}$) and macroscopic multi-mode cloud ($2600\text{ px}$).
- **Zero Dependencies**: Pure HTML5 and GLSL ES 3.0 shaders with zero external runtime libraries.

---

## Controls

| Key / Action | Function | Details |
| :---: | :--- | :--- |
| **Click / Tap** | Re-randomize | Generates fresh relative modal phases and spatial orientation. |
| **Double Click** | Fullscreen | Toggles browser fullscreen mode. |
| <kbd>A</kbd> | Amplitude Mode | Switches to field modulus (Inferno colormap). |
| <kbd>P</kbd> | Phase Mode | Switches to Phase Color Wheel. |
| <kbd>R</kbd> | Real Part Mode | Switches to Bipolar Red & Blue optical carrier oscillation. |
| <kbd>C</kbd> | Cycle Colormaps | Cycles Amplitude $\to$ Phase $\to$ Real Part. |
| <kbd>T</kbd> | Toggle Top Bar | Shows/hides live metrics header. |
| <kbd>←</kbd> | Expand Modes | Expands beam waist towards macroscopic speckle cloud ($2600\text{ px}$). |
| <kbd>→</kbd> | Contract Modes | Narrows beam waist down to single speckle ($35.4\text{ px}$). |
| <kbd>Ctrl+←</kbd> | Increase Divergence | Scales angular divergence up (widens beam). |
| <kbd>Ctrl+→</kbd> | Decrease Divergence | Scales angular divergence down (narrows beam). |
| <kbd>↑</kbd> | Increase Bandwidth | Widens spectral bandwidth smoothly up to $\Delta E/E = 15.0\%$. |
| <kbd>↓</kbd> | Decrease Bandwidth | Narrows spectral bandwidth down to monochromatic $0.0\%$ at $k = 1.000$. |
| <kbd>N</kbd> | Cycle Noise | Cycles analog sensor noise ($0\% \to 3\% \to 6\% \to 10\%$). |
| <kbd>Space</kbd> | Re-randomize | Generates fresh random parameters. |
