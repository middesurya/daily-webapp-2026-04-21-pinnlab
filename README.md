# PINNLab — Interactive Physics-Informed Neural Networks Laboratory

[![MIT License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Daily Webapp](https://img.shields.io/badge/daily--webapp-ai--built-blueviolet)](https://github.com/middesurya)
[![Claude Code](https://img.shields.io/badge/built%20with-claude--code-orange)](https://claude.com/claude-code)

**The world's first interactive, in-browser Physics-Informed Neural Networks playground.**

Train neural networks that obey the laws of physics — right in your browser. No installation, no backend, no GPU required.

## What are PINNs?

Physics-Informed Neural Networks (PINNs) embed physical laws (PDEs) directly into the neural network's loss function. Instead of just fitting data, the network must simultaneously satisfy:

- **Data Loss**: Match known boundary/initial conditions
- **Physics Loss**: Satisfy the PDE at random collocation points (via automatic differentiation)
- **Boundary Loss**: Enforce exact boundary conditions

This means PINNs can solve PDEs with minimal labeled data — the physics itself constrains the solution space.

## Features

### 5 PDE Systems
- **Heat Equation** — Thermal diffusion in 1D. Watch heat spread and dissipate.
- **Wave Equation** — Vibrating string dynamics. Standing waves, propagation.
- **Burgers' Equation** — Nonlinear advection-diffusion. Shock formation.
- **Poisson Equation** — 2D steady-state. Electrostatics and potential fields.
- **Schrödinger Equation** — Quantum harmonic oscillator ground state.

### Real-Time Visualization
- 🔥 **PINN Prediction Heatmap** — Watch the neural network's solution evolve during training
- 📊 **Reference Solution** — Analytical/numerical ground truth for comparison
- 🎯 **Error Heatmap** — See exactly where the PINN struggles
- 🌊 **PDE Residual Map** — Visualize where physics constraints are violated
- 📈 **Live Loss Curves** — Track data, physics, boundary, and total loss in real-time

### Architecture Explorer
- Adjust hidden layers (1–8) and neurons (8–128)
- Choose activation functions: tanh, sin (SIREN), swish, GELU
- Toggle Fourier feature embeddings for high-frequency solutions
- Control physics loss weight λ to see what happens when you ignore physics

### Educational Insights
- Loss decomposition bars showing the balance between data and physics
- Architecture visualization with autodiff computation graph
- Context-sensitive explanations for each PDE system
- Real-time training status with L² error tracking

## Tech Stack

- **TensorFlow.js** — In-browser neural network training with WebGL acceleration
- **Pure HTML/CSS/JS** — Single file, zero dependencies beyond TF.js
- **Canvas API** — Custom heatmap rendering with scientific colormaps (Viridis, etc.)

## Why This Matters

PINNs are at the frontier of scientific machine learning (April 2026):

- University of Hawaiʻi published new physics-informed ML algorithms (AIP Advances)
- MIT uses AI to uncover atomic defects in materials science
- Google's TurboQuant (ICLR 2026) shows physics-ML convergence is accelerating
- Neuro-symbolic AI combining neural networks with physical laws gaining legitimacy

This lab makes PINNs accessible to anyone with a browser.

## Live Demo

🔗 [pinnlab.vercel.app](https://pinnlab.vercel.app)

## License

MIT — built autonomously with Claude Code.
