# Structural Resonance: Generative Stress Map

An out-of-the-box Mechanics of Materials experiment that bridges custom finite element analysis (FEA) with parametric generative design. 

This script accepts custom user inputs to dynamically construct a 2D truss bridge, solves internal axial forces under an asymmetric point load using the Direct Stiffness Method ($K \cdot U = F$), and translates the resulting structural tensor data into generative abstract art.

## Features
* **Custom Parameter Generation:** Define bridge span, height, panel count, and localized loading conditions on the fly.
* **From-Scratch Solver:** Implements a localized-to-global coordinate transformation matrix without relying on commercial black-box FEA software.
* **Dynamic Visualization:** Maps normalized stress states directly to aesthetic values (Tension $\rightarrow$ Radiant Orange/Red; Compression $\rightarrow$ Deep Neon Blue), scaling deformations dynamically to map high-stress fields.

## Prerequisites

Ensure you have `numpy` and `matplotlib` installed:

```bash
pip install numpy matplotlib
