---
layout: single
#title: "Fractures and Thin Heterogeneities as Robin–Wentzell Interface Conditions"
title: "Interface Conditions for fluid-flow in fractured porous media"
date: 2025-10-07
excerpt: "We derive Wentzell-type (flux jump) and Robin-type (flux average) interface conditions for fractures and thin inclusions in Darcy/diffusion problems, providing a weak formulation directly usable in FEM implementations."
tags: [fractures, porous-media, interface-conditions, Wentzell, Robin, FEM, Darcy]
mathjax: true
# header:
#   teaser: /assets/images/wentzell-teaser.jpg
teaserNoGrid: interfaceConditions/realistic.png
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


## Overview

We present a novel modeling technique for **fractures and thin inclusions** in heterogeneous media.  
While our primary application is **Darcy flow**, the approach applies to any problem that can be written in **divergence form** (i.e., as the divergence of a flux).

The key result is a pair of interface conditions:
- a **Wentzell-type** law for the **flux jump** (tangential diffusion along the interface acting on the **average pressure**), and
- a **Robin-type** law for the **flux average** (proportional to the **pressure jump**).

These conditions yield a compact and elegant **weak formulation** that can be used directly in standard **finite element** codes.  
Computational cost is reduced because the method **avoids explicit background–fracture coupling of unknowns**, removing the need to represent fractures with meshes.

---

## Background (Darcy / Diffusion)

We consider the diffusion/Darcy system:

$$
-\nabla\cdot \mathbf{u} = 0,
$$

$$
\mathbf{u} = -\,k\,\nabla p.
$$

Here, $k$ denotes the permeability (or mobility), which takes significantly different values in the **background** and in the **fracture** region, as illustrated in panel (a) of the figure below.

![Fracture sketch](/assets/images/interfaceConditions/domain2D.png)

By replacing the thin inclusion with an interface $\gamma$ that splits the domain into $\Omega_1$ and $\Omega_2$—see panel (b)—we allow for **discontinuities** of the pressure $p$ and of the normal flux $\mathbf{u}\!\cdot\!\boldsymbol{\eta}$ across $\gamma$. The problem is then closed with **interface conditions** obtained by formally integrating the governing equations across the inclusion aperture.

## Hypothesis in the derivation

The derivation relies on three standard assumptions:  
1. **Linearity** of fields across the thickness (trapezoidal rule),  
2. **Consistent orientation** of the normal vectors at the faces,  
3. **Small aperture variation** (A1–A3).  

---

## Main result — Flux jump and average interface conditions

For an inclusion of aperture $\varepsilon$ and mobility $k_f$, one obtains, on $\gamma$:

$$
-[[ \mathbf{u}]] \;=\; -\,\nabla_\tau\cdot\!\big(\,\varepsilon\,k_f\,\nabla_\tau \{p\}\big),
$$

$$
-\{\!\{\mathbf{u}\}\!\} \;=\; \frac{k_f}{\varepsilon}\,[p].
$$

- **Wentzell-type** on the **flux jump** (left): a **tangential diffusion** of the **average pressure** $\{p\}$ along $\gamma$.  
- **Robin-type** on the **flux average** (right): proportional to the **pressure jump** with coefficient $k_f/\varepsilon$.  

These conditions emerge from a trapezoidal integration across the aperture under mild assumptions on the variation through the thickness.

> **1D intuition.** Consider the configuration in panel (a) below.
>
> Integrating the equilibrium and constitutive laws across the inclusion interval
> $$(S-\varepsilon/2,\; S+\varepsilon/2)$$
> and then taking the limit $S_1, S_2 \to S$ (so that the domain reduces to the one in panel (b) below), one obtains:
>
> - **flux jump:** $$[[u]] = 0,$$
> - **flux average:** $$\{\!\{u\}\!\}\ \propto\ [[p]],$$
>
> i.e., the flux is continuous in 1D, while its average across the interface is proportional to the **pressure jump**.

![1D domain](/assets/images/interfaceConditions/domain1D.png)

In the figure below, the interface model **perfectly reproduces** the pressure jump obtained with the full equi-dimensional model.

![1D solution](/assets/images/interfaceConditions/solution1D.png)

---

## Multiple and intersecting fractures

The framework extends naturally to **networks of fractures** $\{\gamma_j\}$ (2D/3D), with **apertures** and **mobilities** possibly varying from fracture to fracture.  
Each interface contributes its two terms as above, and **intersections** can be handled without requiring a dedicated sub-model for the intersection geometry.

Below we report the domain for test case, regular fracture network, which features 6 intersection fractures and separate the domain into 10 subdomains.

![2D intersection](/assets/images/interfaceConditions/multiple2D.png)

---

## Validation

2D/3D benchmark tests (regular networks, single fractures, elliptical fractures) show **excellent agreement** with highly resolved equi-dimensional models and hybrid/immersed methods (BOX, XFEM, etc.).  
A particularly relevant case is the **blocking** configuration, where the interface formulation naturally captures the **pressure jump** that continuous-pressure models struggle to reproduce.

Beyond quantitative match, the **pressure distributions** exhibit the hallmarks of real porous systems:
- smooth pressure decay in the matrix with **localized steep gradients** near interfaces and tips,  
- **anisotropic pressure channels** along conductive fractures,  
- and **sharp discontinuities** across blocking interfaces, consistent with measured drawdown and interference patterns in field data.

Below we report a selection of figures.

![2D intersection](/assets/images/interfaceConditions/regCond2D.png)  
*Regular 2D network, conductive case: pressure funnels along the connected fracture set, with gentle transverse leakage into the matrix.*

![2D intersection](/assets/images/interfaceConditions/regBlock2D.png)  
*Regular 2D network, blocking case: a clean pressure offset across the interface; lateral equilibration occurs primarily within subdomains.*

![3D network](/assets/images/interfaceConditions/regCond3D.png)  
*Regular 3D network, conductive case: elongated pressure contours aligned with the main fracture families, mimicking preferential flow paths observed in outcrop-based DFN models.*

![3D network](/assets/images/interfaceConditions/regBlock3D.png)  
*Regular 3D network, blocking case: pronounced interfacial jumps and compartmentalization consistent with sealed or low-aperture features.*

![Single fracture](/assets/images/interfaceConditions/single3D.png)  
*Single 3D fracture: symmetric pressure decay from the source and a narrow high-gradient corridor along the interface plane.*

![Elliptical fracture](/assets/images/interfaceConditions/elliptical.png)  
*Elliptical inclusion: elliptical isobars, stronger curvature near the tips; this reproduces tip effects commonly reported in laboratory analogs.*

![Realistic network](/assets/images/interfaceConditions/realistic.png)  
*Realistic network: heterogeneous pressure plateaus in the matrix and fracture-guided conduits; the spatial patterns mirror field-like pressure interference and drawdown behavior.*

---

**In summary.** The interface formulation **perfectly recovers the physics** in the representation of the pressure fields without the need of an explicit mesh respresentatio of the fractures. It channels pressure along transmissive features, preserves **discontinuities** across blocking interfaces, and maintains **matrix diffusion** away from fractures—precisely the behavior documented in experimental and field-scale observations.

---

## Takeaways

- **Flux jump = Wentzell** (tangential diffusion of the **mean pressure**).  
- **Flux average = Robin** (proportional to the **pressure jump**).  
- **Weak formulation**: minimal, with only two additional interface integrals.  
- **Meshes conforming to $\gamma$**, duplicated DoFs on the boundary ⇒ easy implementation.  
- Works for both **conductive** and **blocking** interfaces, including **intersections** and **variable apertures**.

---

# Mathematical framework

## Function spaces & Wentzell regularity

The presence of **tangential diffusion** terms on $\gamma$ implies that the test functions (and thus $p$) require **tangential regularity** ($H^1(\gamma)$) whenever Wentzell-type terms are active; in their absence, this requirement relaxes to $L^2(\gamma)$.

---


## Primal weak formulation (FEM-ready)

Let $$\{\Omega_i\}_{i=1}^{n_S}$$ be the decomposition induced by a set of interfaces $$\{\gamma_j\}_{j=1}^{n_F}$$.  
The weak formulation reduces to a combination of **background** and **interface** integrals:

$$
\sum_{i=1}^{n_S}\!\int_{\Omega_i}\! k_i\,\nabla p_i\!\cdot\!\nabla q_i\,d\Omega 
\;+\;
\sum_{j=1}^{n_F}\!\left[
\int_{\gamma_j}\!\varepsilon_j k^f_j\,\nabla_\tau\{p\}\!\cdot\!\nabla_\tau\{q\}\,d\Gamma
\;+\;
\int_{\gamma_j}\!\frac{k^f_j}{\varepsilon_j}\,[p]\,[q]\,d\Gamma
\right]
=
\int_{\Gamma^u}\! h\,q\,d\Gamma.
$$

This form is **simple and elegant**: it adds only two interface terms — one **tangential diffusion** on the **mean pressure**, and one **penalization/coupling** term on the **jump**.  
It can be directly implemented in standard FEM by duplicating the degrees of freedom on the two sides of each interface.

---

## FEM in practice

The FEM discretization is standard: each subdomain $\Omega_i$ is meshed conforming to $\gamma$, duplicating nodes along the interface to allow the **pressure jump**.  
The resulting linear system remains well-conditioned and can be solved efficiently with direct/parallel solvers (e.g., **MUMPS**) or iterative ones.  
The approach integrates seamlessly with frameworks such as **MOOSE**, and allows automated mesh splitting.

![2D intersection](/assets/images/interfaceConditions/mesh.png)

---

## Reference

- M. Favino, *Fractures and Thin Heterogeneities as Robin–Wentzell Interface Conditions*. Manuscript/PDF.
