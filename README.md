# Hindmarsh-Rose-Model-
Neuronal chaos analysis: Hindmarsh-Rose model with Lyapunov exponents and bifurcation studies in Python with using only the inbuild libraries 
#  Hindmarsh–Rose Neuron Model — Chaos Analysis

This repository contains a complete numerical exploration of the **Hindmarsh–Rose neuronal model**, focusing on:

- Phase portraits across different input currents  
- Sensitivity to initial conditions (Butterfly Effect)  
- Largest Lyapunov exponent computation  
- Numerical confirmation of chaotic vs periodic regimes  

All simulations use a custom **4th-order Runge–Kutta integrator (RK4)** implemented from scratch.

##  About the Hindmarsh–Rose Model

The Hindmarsh–Rose (HR) model is a biologically inspired neuron model capable of producing:

- Regular spiking  
- Bursting  
- Mixed-mode oscillations  
- Chaos  

It is governed by:

\[
\dot{x} = y - ax^3 + bx^2 - z + I
\]
\[
\dot{y} = c - dx^2 - y
\]
\[
\dot{z} = r (s(x - x_r) - z)
\]


##  Project Structure

```
├── hr_chaos.py        # Main simulation and analysis script
├── plots/             # Optional: store generated plots
└── README.md
```

---

##  Features

###  Custom RK4 Integrator  
Numerical integration written manually, no SciPy dependency.

###  Phase Portrait Sweep  
Plots HR dynamics for several external current values.

###  Butterfly Effect  
Simulates two trajectories starting ε-apart to visualize exponential divergence.

###  Lyapunov Exponent Calculation  
Implements the renormalization method:  
- discards initial transients  
- tracks divergence  
- computes largest Lyapunov exponent  
- determines chaotic vs periodic regimes  

###  Lyapunov vs Input Current Plot  
Shows how chaos emerges as input current increases.

---

##  Plots Generated

The script produces:

- Phase portraits (x-y)
- Membrane potential time series
- Divergence plot (Butterfly effect)
- Lyapunov exponent vs external current

---

##  How to Run

Install dependencies:

```bash
pip install numpy matplotlib
```

Run:

```bash
python hr_chaos.py
```

This executes all experiments:

1. Phase portraits sweep  
2. Butterfly-effect simulation  
3. Single-current diagnostics  
4. Lyapunov exponent sweep  

---

##  Important Functions

### `simulate_hr(I, T, dt)`
Simulates HR neuron using RK4.

### `lyapunov_convergence(...)`
Computes the largest Lyapunov exponent.

### `sweep_and_plot()`
Plots phase portraits for multiple current values.

### `butterfly_effect()`
Shows sensitivity to initial conditions.

### `lyapunov_vs_I_plot()`
Plots λ vs I to detect chaos.

---

##  Scientific Interpretation

- **λ > 0** → Chaotic regime  
- **λ = 0** → Quasi-periodic  
- **λ < 0** → Stable periodic orbit  

HR model typically becomes chaotic near **I ≈ 3.2–3.4**.

---

##  Example Output (Lyapunov Sweep)

```
I = 2.500 → λ ≈ -0.00231
I = 3.000 → λ ≈  0.00015
I = 3.250 → λ ≈  0.01782   (chaotic)
I = 3.500 → λ ≈  0.00451
```

---

##  Why This Project Is Useful

This repository demonstrates:

- Deterministic chaos in neuronal models  
- Numerical ODE integration  
- Lyapunov exponent estimation  
- How micro-changes → macro-differences (Butterfly effect)  
- Transition between periodic and chaotic regimes  


##  Contributing

Pull requests and improvements are welcome.  
You may extend this to multi-neuron networks, bifurcation diagrams, or noise-driven dynamics.

