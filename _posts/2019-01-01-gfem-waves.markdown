---
layout: single
title:  "Transient wave propagation in heterogeneous media using a Generalized Finite Element Method"
# date:   2022-09-17 00:05:13 +0200
# categories: jekyll update
exampleFigure: solution-307.jpg
---

Spectral element method (SEM) is usually employed to simulate wave propagation
together with explicit time-stepping schemes.
SEM ensures that the matrix to invert at each time step is diagonal,
rendering the simulations accurate and efficient.

However, for heterogeneous media, while SEM keeps its efficiency,
its accuracy is reduced due to the low regularity of the solution.

On the other hand, GFEM allows to improve the accuracy even in case of heterogeneous media
by employing suitable additional basis functions.
The price to pay is not having a diagonal system to invert at each time step.

Below we report some simulatios performed with a GFEM implemented in **Deal.II**.


Example of a domain for a homogenous media.
<img src="/assets/images/04gfem-waves/h_source.png" alt="mesh_front" width="400"/>

Mesh is refined in a neighborhood of the source.
<img src="/assets/images/04gfem-waves/h_source_doubleRef2.png" alt="mesh_back" width="400"/>

Example of numerical simulation in a homogenous medium.
Click to see a movie.
[![Alternate Text](/assets/images/04gfem-waves/solution-307.jpg)](/assets/images/04gfem-waves/out.mp4 "Video homogeneous media")

Heterogenous domain

<img src="/assets/images/04gfem-waves/scatter_source.png" alt="mesh_front" width="400"/>

Mesh for the heterogeneous domain

<img src="/assets/images/04gfem-waves/meshr_ref_v2.png" alt="mesh_front" width="400"/>

Seismogram scattering

<img src="/assets/images/04gfem-waves/seismogram_scattering.png" alt="mesh_front" width="400"/>


