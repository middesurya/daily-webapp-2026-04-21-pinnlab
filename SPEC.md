# PINNLab — Interactive Physics-Informed Neural Networks Laboratory

## Concept
An in-browser interactive laboratory where users train Physics-Informed Neural Networks (PINNs) in real-time using TensorFlow.js. Users select physical systems governed by PDEs, define boundary conditions visually, watch the neural network learn to satisfy both data and physics constraints simultaneously, and explore how the physics loss reshapes the optimization landscape.

## Why This Is Innovative
- **No interactive browser PINN playground exists** — TensorFlow Playground is for vanilla NNs, this is specifically for physics-constrained learning
- **Trending**: UH Mānoa published physics-informed ML algorithm (April 2026), MIT materials science AI, ICLR 2026 physics-ML convergence
- **Scientific depth**: Real PDE solving, automatic differentiation for physics constraints, loss decomposition
- **Visual wow factor**: Watch neural networks learn physics in real-time with heatmaps and error surfaces

## Core Modules

### 1. PDE System Selector
- **Heat Equation** (1D/2D): ∂u/∂t = α∇²u — diffusion, thermal conduction
- **Wave Equation** (1D): ∂²u/∂t² = c²∂²u/∂x² — vibrating strings, sound
- **Burgers' Equation** (1D): ∂u/∂t + u·∂u/∂x = ν·∂²u/∂x² — shock formation, turbulence
- **Schrödinger Equation** (1D): iℏ∂ψ/∂t = -ℏ²/2m·∂²ψ/∂x² + V(x)ψ — quantum mechanics
- **Poisson Equation** (2D): ∇²u = f — electrostatics, gravity

### 2. Interactive Training Dashboard
- Real-time loss curves: total loss, data loss, physics (PDE residual) loss, boundary loss
- Animated solution heatmap showing the network's prediction evolving during training
- Side-by-side comparison with analytical/numerical reference solution
- Error heatmap showing |PINN - reference| at each point

### 3. Physics Loss Anatomy
- Visual decomposition of how the physics loss is computed via automatic differentiation
- Show the computation graph: input → network → output → derivatives → PDE residual
- Interactive sliders for physics loss weight (λ) — watch what happens when you ignore physics

### 4. Architecture Explorer
- Adjust hidden layers, neurons per layer, activation functions (tanh, sin, swish)
- Fourier feature embeddings toggle (for high-frequency solutions)
- Learning rate scheduler visualization
- Compare training with and without physics constraints simultaneously

### 5. Boundary Condition Canvas
- Draw/modify boundary conditions interactively on a 2D domain
- Drag control points for Dirichlet/Neumann conditions
- See how boundary conditions affect the learned solution

## Tech Stack
- Single HTML file with embedded JS/CSS
- TensorFlow.js for in-browser neural network training with automatic differentiation
- D3.js for data visualization
- Canvas API for heatmaps and solution visualization
- No backend required — everything runs client-side

## Scoring
- Novelty: 10/10 (no PINN playground exists in browsers)
- Feasibility: 8/10 (TF.js has autodiff, but PDE residuals are compute-intensive)
- Wow Factor: 9/10 (watching neural nets learn physics is mesmerizing)
- Learning Value: 10/10 (teaches PINNs, PDEs, autodiff, constrained optimization)
- Utility: 8/10 (useful for researchers, students, educators)
- **Total: 96/110**
