# Build Report: PINNLab

**Date**: 2026-04-21
**Build Time**: ~45 minutes
**Status**: Deployed

## Links
- **Live**: https://pinn-lab.vercel.app
- **GitHub**: https://github.com/middesurya/daily-webapp-2026-04-21-pinnlab

## Idea Selection

Scored 12 ideas from trending AI topics (April 2026):
- Physics-Informed Neural Networks Lab: **96/110** (winner)
- KV Cache Compression Visualizer (TurboQuant): 78/110
- Agentic AI Orchestration Playground: 72/110
- AI Cybersecurity Vulnerability Scanner: 65/110

PINNLab won because: no interactive browser PINN playground exists, scientifically rigorous, trending (UH Mānoa, MIT, ICLR 2026), visually stunning, high educational value.

## What Was Built

A single-file HTML application (55KB) that trains Physics-Informed Neural Networks in-browser using TensorFlow.js. Users select from 5 PDE systems, configure network architecture, and watch real-time heatmap visualizations of the solution, error, and PDE residual.

## Technical Decisions

1. **Single HTML file** — maximizes portability, no build step needed
2. **TensorFlow.js WebGL backend** — GPU-accelerated training in browser
3. **Numerical derivatives** (finite differences) instead of tf.grad — more reliable across TF.js versions, still accurate to O(h²)
4. **Viridis colormap** — perceptually uniform, colorblind-friendly, scientific standard
5. **Resample collocation points every 200 epochs** — prevents overfitting to fixed points

## Avoided Past Mistakes

- Embedded all data inline (no fetch())
- Used `{"cleanUrls": true}` for vercel.json
- Validated JS syntax with `new Function()` before committing
- Used HTTPS remote for git push

## What I'd Improve Next

1. Add true automatic differentiation via tf.grad() for exact PDE residuals
2. Add adaptive collocation point sampling (concentrate near high-error regions)
3. Add multi-fidelity training (coarse-to-fine)
4. Add a comparison mode showing PINN vs pure data-fitting side by side
5. Add the Allen-Cahn and Navier-Stokes equations
