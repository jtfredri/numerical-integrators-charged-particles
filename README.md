# Numerical Integrators for Charged Particle Dynamics

This project investigates numerical methods for simulating the motion of charged particles in electromagnetic fields, with a particular focus on **long-time stability and energy conservation**. Standard high-order methods can exhibit unphysical energy drift over long simulations, so the project compares classical methods with **structure-preserving (geometric) integrators**.

---

## Problem Overview

We consider the motion of a charged particle with unit mass and charge in a static magnetic field $B(x)$ and an electrostatic potential $U(x)$. The dynamics are governed by

$$
\dot{x} = v, \qquad
\dot{v} = v \times B(x) - \nabla U(x).
$$

The system conserves the energy

$$
E(x, v) = \frac{1}{2}\|v\|^2 + U(x).
$$


---

## Implemented Methods

The project implements and compares three numerical integrators:

### 1. Runge–Kutta 4 (RK4)
- Classical fourth-order explicit method  
- High short-term accuracy  
- Known to suffer from **energy drift** in long-time simulations  

### 2. Boris Method
- Second-order method
- Exhibits excellent long-term energy behavior  

### 3. Fourth-Order Symmetric Multistep Method
- Explicit geometric integrator based on vector potentials  
- Preserves symmetry
- Requires high-accuracy starting values


---

## Model Problems

Two physically systems are studied:

### • 2D Charged Particle in a Non-Uniform Magnetic Field
- Includes both magnetic and electrostatic forces  

### • Tokamak Magnetic Field
- Models particle motion in a toroidal magnetic confinement device  

---

## Numerical Experiments

The notebook includes the following experiments:

### Trajectories
- Phase-space trajectories and spatial orbits  
- Visualization of confinement behavior in the tokamak field  

### Error Analysis
- Comparison against high-accuracy reference solutions  
- Log-scale error growth over long time intervals  

### Energy Conservation
- Tracking deviation from initial energy over time  

### Order Verification
- Convergence studies using decreasing step sizes 
- Log–log plots to confirm theoretical orders of accuracy

### Work–Precision Diagrams
- Error versus runtime comparisons  
- Efficiency analysis of each method  

---

## References

- Y. He, Y. Sun, J. Liu, and H. Qin,  
  *Volume-preserving algorithms for charged particle dynamics*,  
  Journal of Computational Physics, 281, 135–147 (2015).

- E. Hairer and C. Lubich,  
  *Symmetric multistep methods for charged-particle dynamics*,  
  The SMAI Journal of Computational Mathematics, 3, 205–218 (2017).

