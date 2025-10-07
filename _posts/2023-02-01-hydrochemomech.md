---
layout: single
title: "Hydro–Chemo–Mechanical Modeling: Growth and Remodeling/Plasticity"
date: 2025-10-07
tags: [hydro-chemo-mechanical, growth, remodeling, plasticity, poromechanics, continuum-mechanics]
---

<!-- Enable MathJax -->
<script>
window.MathJax = {
  tex: {inlineMath: [['$', '$'], ['\\(', '\\)']]},
  svg: {fontCache: 'global'}
};
</script>
<script id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
</script>

We present a system of equations describing a **hydro–chemo–mechanical model** that accounts for **growth and remodeling** in a deformable porous medium.  

The formulation extends a classical hydro-mechanical framework of **poroelasticity** by introducing **chemical reactants** and **growth/remodeling processes**, modeled respectively as **first-** and **zero-order theories**.

In this setting:
- *Hydro-mechanical coupling* governs the balance of momentum and fluid mass.  
- *Chemical activity* regulates mass exchange and growth kinetics.  
- *Growth and remodeling* evolve according to energetically and stress-driven rules, capturing **plastic-like** behavior within the internal structure.

---

## Hydro-mechanics

Standard variables for poroelasticity are $\mathbf{u}$ and $p$.  
Since we are working in a non-linear framework, we introduce the deformation gradient $\mathbf{F}$ and its determinant $J$.

### Kinematics

$$
\mathbf{F} = \mathbf{I} + \mathrm{Grad}\,\mathbf{u}, 
\qquad 
J = \det \mathbf{F}.
$$

### Balance of linear momentum (reference configuration)

$$
\mathrm{Div}\,\mathbf{P} + \mathbf{B} = \mathbf{0}, 
\qquad 
\mathbf{P} = \mathbf{P}_{\mathrm{sc}} - J\,p\,\mathbf{F}^{-T}.
$$

- $\mathbf{P}$: total first Piola–Kirchhoff stress.  
- $$\mathbf{P}_{\mathrm{sc}}$$: effective (skeleton) Piola stress (e.g., $\mathbf{P}_{\mathrm{sc}} = \partial \Psi(\mathbf{F}) / \partial \mathbf{F}$ for a hyperelastic solid).  
- $\mathbf{B}$: body force per unit reference volume.  
- The term $J\,p\,\mathbf{F}^{-T}$ represents the pore-pressure contribution (Terzaghi/Biot split at finite strain).

### Fluid mass balance (reference configuration)

$$
\dot{J} - \mathrm{Div}\!\left( \mathbf{q}_R \right) = \Gamma_f .
$$

- $\Gamma_f$: fluid source/sink per unit reference volume.  
- $\boldsymbol{\mathfrak{K}}$: referential hydraulic mobility tensor.

### Darcy law (referential form)

If $\mathbf{k}$ is the **spatial** permeability tensor, then the referential mobility tensor is

$$
\boldsymbol{\mathfrak{K}} = J\,\mathbf{F}^{-1}\,\mathbf{k}\,\mathbf{F}^{-T},
$$

and the referential fluid flux is

$$
\mathbf{q}_R = -\,\boldsymbol{\mathfrak{K}}\,\mathrm{Grad}\,p .
$$

## Remodeling

The remodeling process describes the evolution of the internal configuration of the solid, modeled through the **Bilby–Kröner–Lee (BKL) multiplicative decomposition** of the deformation gradient.  
This allows us to distinguish between elastic and remodeling (plastic-like) deformations.

### Bilby–Kröner–Lee decomposition

$$
\mathbf{F} = \mathbf{F}_\mathrm{e}\,\mathbf{F}_\gamma,
$$

where:
- $\mathbf{F}_\mathrm{e}$ is the **elastic part** of the deformation gradient,  
- $\mathbf{F}_\gamma$ is the **remodeling (or plastic) part**, associated with the internal rearrangement of the material microstructure.

The associated remodeling metric tensor is defined as

$$
\mathbf{B}_\gamma = \mathbf{F}_\gamma\,\mathbf{F}_\gamma^{T}.
$$

This tensor encodes the evolving internal geometry and is responsible for anisotropy and residual stress in the remodeled configuration.

---

### Strong form

$$
\dot{\mathbf{B}}_\gamma
= -\,2\,\lambda_\gamma\,\mathbf{B}_\gamma\,\mathbf{G}\,
\mathrm{dev}\,\boldsymbol{\Sigma}^{(\mathrm{sc})}.
$$

Here:
- $\lambda_\gamma$ is a **kinetic coefficient** controlling the rate of remodeling,  
- $\mathbf{G}$ is the reference metric or elastic tensor,  
- $\mathrm{dev}\,\boldsymbol{\Sigma}^{(\mathrm{sc})}$ is the deviatoric part of the solid (skeleton) stress tensor.

This constitutive evolution law drives the internal variable $\mathbf{B}_\gamma$ toward states that relax deviatoric stresses, in analogy with **plastic flow**.

---

### Interpretation

- The decomposition $$\mathbf{F} = \mathbf{F}_\mathrm{e}\,\mathbf{F}_\gamma$$ separates recoverable (elastic) and irreversible (remodeling/plastic) contributions.  
- The tensor $\mathbf{B}_\gamma$ evolves according to a **stress-driven flow rule**, relaxing the deviatoric stresses while preserving volume or other invariants, depending on the specific constitutive assumptions.  
- This evolution law ensures **energy dissipation** and describes slow structural adaptation, such as **tissue remodeling**, **plastic reorientation**, or **fabric evolution** in geomaterials.

---

## Validation for the remodeling

We consider a **2D poroelastic square** in contact with a **rigid circular indenter**.  
The object is pressed against the square for **6 seconds**, then the load is **held constant** until **8 seconds**.  
After this stage, the indenter is **released**.

The simulation shows that:
- the **hydro-mechanical coupling** produces a **viscous-like relaxation** after unloading,  
- while the **remodeling (plastic-like) effects** remain, leading to **permanent deformations** in the solid structure.

<video width="640" height="360" controls>
  <source src="/videos/output2.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

---

## Growth

The growth process describes the local change in the volume of the solid matrix, represented by the determinant of the growth tensor $J_\gamma$.  
It accounts for chemically or physiologically driven mass production within the solid skeleton, according to a **first-order theory**.

### Strong form

$$
\dot{J}_\gamma
+ \mathrm{Div}\!\big(\boldsymbol{\mathfrak{M}}\,\mathrm{Grad}\,\mu_\gamma\big)
= J_\gamma\,R_{\mathrm{ph}}.
$$

Here:
- $J_\gamma$ is the determinant of the growth tensor (volumetric growth variable).  
- $\mu_\gamma$ is the **chemical potential** (growth driving potential).  
- $\boldsymbol{\mathfrak{M}}$ is the **growth mobility tensor**, governing fluxes of $\mu_\gamma$.  
- $R_{\mathrm{ph}}$ is the **physiological source term**, representing internal production or resorption of mass.

This equation expresses a local **balance of growth mass**, where volumetric changes are driven by gradients of the chemical potential and by internal reaction terms.

---

## Chemical potential

The **chemical potential** $\mu_\gamma$ acts as the **driving force for growth** within the hydro–chemo–mechanical system.  
It represents the local thermodynamic potential associated with the redistribution of mass or reactants inside the solid matrix.  
Spatial gradients of $\mu_\gamma$ induce diffusive fluxes that control the rate and direction of growth or resorption.

$$
\dot{J}_\gamma \;+\; \mathrm{Div}\!\big(\boldsymbol{\mathfrak{M}}\,\mathrm{Grad}\,\mu_\gamma\big)
= J_\gamma\,R_{\mathrm{ph}}.
$$

Here:
- $J_\gamma$ is the **determinant of the growth tensor**, describing volumetric change of the solid matrix.  
- $\mu_\gamma$ is the **chemical potential**, coupling mechanical, chemical, and energetic contributions.  
- $\boldsymbol{\mathfrak{M}}$ is the **mobility tensor**, controlling how fast gradients in $\mu_\gamma$ relax through mass flux.  
- $R_{\mathrm{ph}}$ is the **physiological reaction rate** (source/sink term), accounting for local mass production, degradation, or biochemical activity.

The term $\mathrm{Div}(\boldsymbol{\mathfrak{M}}\mathrm{Grad}\,\mu_\gamma)$ represents **diffusive mass transport**, while $J_\gamma R_{\mathrm{ph}}$ describes **local reactions** contributing to volume changes.  
Altogether, this equation expresses the **mass balance for the growth subsystem**.

---

### Constitutive closure

The potential $\mu_\gamma$ is typically defined by a constitutive relation combining:
1. a **chemical/energetic contribution** $z/J_\gamma$,  
2. a **viscous or dissipative term** proportional to $$\dot{J}_\gamma/J_\gamma$$, and  
3. the **elastic (energetic) part** from the free energy density $\Psi_{\mathrm{R}}$.

That is,

$$
\mu_\gamma
= \frac{z}{J_\gamma}
- k_\nu\,\frac{\dot{J}_\gamma}{J_\gamma}
- \mathcal{E}_{J_\gamma}(\Psi_{\mathrm{R}}),
$$

where:
- $z$ is a **chemical–mechanical potential** (e.g. related to species concentration or mechanical work),  
- $k_\nu$ is a **viscous coefficient** regulating dissipative effects,  
- $$\mathcal{E}_{J_\gamma}(\Psi_{\mathrm{R}})$$ is the **elastic energetic contribution** (derivative of the free energy density with respect to $J_\gamma$).

---

### Physical interpretation

- $\mu_\gamma$ acts as a **diffusive potential** coupling chemistry and mechanics.  
- Gradients in $\mu_\gamma$ drive **mass redistribution**, enabling heterogeneous growth or dissolution.  
- The balance between diffusive transport and the source term $R_{\mathrm{ph}}$ determines whether the system **accretes**, **resorbs**, or **stabilizes**.  
- In coupled hydro–chemo–mechanical systems, $\mu_\gamma$ also transmits **feedback from stresses and strains**, allowing mechanical loading to influence growth kinetics.


## Hydro–chemo–mechanical simulation

We consider a **spherical geometry**, where only **one octant** is simulated due to symmetry.  
A **chemical source** is placed at the center, driving the **growth process** through diffusion of the chemical potential.

The model couples:
- **hydro-mechanical deformation**,  
- **chemical transport**, and  
- **growth kinetics** governed by the local chemical activity.

This configuration allows observing how chemical concentration gradients induce **nonuniform growth** and **stress development** in the surrounding solid.

<video width="640" height="360" controls>
  <source src="/videos/growth3D.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

---


### Numerical implementation

The governing equations have been solved using a **finite element method (FEM)** for the spatial discretization, ensuring accurate treatment of the coupled hydro–chemo–mechanical fields in complex geometries.  
A **finite-difference time-stepping scheme** was employed to advance the system in time, allowing for a stable and efficient resolution of the evolution equations for $J_\gamma$, $\mu_\gamma$, and $\mathbf{B}_\gamma$.  

To integrate the remodeling equation, which involves a nonlinear stress-driven evolution of the internal tensor $\mathbf{B}_\gamma$, we adopted an **exponential integrator**.  
This approach preserves the tensorial structure of $$\mathbf{B}_\gamma$$, guarantees positive-definiteness, and provides improved numerical stability compared to standard explicit updates.  

Overall, the combination of FEM for space, finite differences for time, and exponential integration for the remodeling variable yields a robust and accurate framework for simulating coupled growth and remodeling phenomena.
