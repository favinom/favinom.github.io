---
layout: archive # category
title: Simulation portfolio
permalink: /portfolio/
author_profile: true
---

### Flow and transport in fractured porous media

One of the major challenges for numerical simulation of fracture media is the creation of adequate computational meshes,
which resolve the numerous and complex interfaces between the heterogeneities and the embedding background.
To this end, we have developed a novel method based on adaptive mesh refinement (AMR),
which allows for the fully automatic creation of meshes for strongly heterogenous media.
The key concept of the proposed method is to start from an initially uniform coarse mesh and
then to gradually refine elements which have non-empty overlaps with the embedded heterogeneities.
This results in a hierarchy of non-uniform meshes with a large number of elements close to the interfaces,
which do, however, not need to be explicitly resolved.
This dramatically simplifies and accelerates the laborious and time-consuming process
of meshing strongly heterogeneous poroelastic media,
thus enabling the efficient simulation of REVs containing heterogeneities of quasi-arbitrary complexity.

Adaptive mesh refinement for the example __Small Features__

<img src="/assets/maria_n_1.png" alt="mesh_front" width="300"/>
<img src="/assets/maria_n_2.png" alt="mesh_front" width="300"/>

<img src="/assets/maria_n_3.png" alt="mesh_front" width="300"/>
<img src="/assets/maria_n_4.png" alt="mesh_front" width="300"/>

Pressure distribution in flow simulation.
<img src="/assets/pressure_small_features_new-eps-converted-to.pdf" alt="mesh_front" width="500"/>


Concentration distribution in three different time steps.
<img src="/assets/c3_small_features_new-eps-converted-to.pdf" alt="mesh_front" width="500"/>


### Poroelasticity for fractured porous media

<img src="/assets/Moose_freq1e-4-eps-converted-to.pdf" alt="mesh_front" width="400"/>
<img src="/assets/Moose_freq1e0-eps-converted-to.pdf" alt="mesh_front" width="400"/>
<img src="/assets/Moose_freq1e4-eps-converted-to.pdf" alt="mesh_front" width="400"/>

### Transient wave propagation in heterogeneous media using a Generalized Finite Element Method

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
<img src="/assets/h_source.pdf" alt="mesh_front" width="400"/>

Mesh is refined in a neighborhood of the source.
<img src="/assets/h_source_doubleRef2.pdf" alt="mesh_back" width="400"/>

Example of numerical simulation in a homogenous medium.
Click to see a movie.
[![Alternate Text](/assets/solution-307.jpg)](/assets/out.mp4 "Video homogeneous media")

Heterogenous domain

<img src="/assets/scatter_source.pdf" alt="mesh_front" width="400"/>

Mesh for the heterogeneous domain

<img src="/assets/meshr_ref_v2.pdf" alt="mesh_front" width="400"/>

Seismogram scattering

<img src="/assets/seismogram_scattering.pdf" alt="mesh_front" width="400"/>


### Electro-mechanical coupling in the heart

<img src="/assets/cardio001.jpg" alt="mesh_front" width="310"/>
<img src="/assets/cardio003.jpg" alt="mesh_front" width="310"/>
<img src="/assets/cardio005.jpg" alt="mesh_front" width="310"/>
<img src="/assets/cardio007.jpg" alt="mesh_front" width="310"/>

<img src="/assets/cardio009.jpg" alt="mesh_front" width="310"/>
<img src="/assets/cardio011.jpg" alt="mesh_front" width="310"/>
<img src="/assets/cardio013.jpg" alt="mesh_front" width="310"/>
<img src="/assets/cardio015.jpg" alt="mesh_front" width="310"/>

### Thermoelasticity for a cooktop

Thermoelasticity equations are employed to simulate the deformation of a cooktop
during its heating process.
Deformations can be relatively large and can make cooktop's surface not flat.
As a consequence, pots will not adhere to the surface and energetic efficiency of the cooktop
may be affected.

In this project, we simulated cooktop's deformations.
The geometry employed is a realistic one from an industrial partner.
It features three wires that make three rounds over the vertical axis.

Thermoelasticty equations have been implemented both in **UG** and **FreeFem++**.

<img src="/assets/section001.png" alt="mesh_front" width="310"/>
<img src="/assets/top001.png" alt="mesh_back" width="310"/>

<img src="/assets/section002.png" alt="mesh_front" width="310"/>
<img src="/assets/top002.png" alt="mesh_back" width="310"/>

<img src="/assets/section004.png" alt="mesh_front" width="310"/>
<img src="/assets/top004.png" alt="mesh_back" width="310"/>

<img src="/assets/section006.png" alt="mesh_front" width="310"/>
<img src="/assets/top006.png" alt="mesh_back" width="310"/>

<img src="/assets/section008.png" alt="mesh_front" width="310"/>
<img src="/assets/top008.png" alt="mesh_back" width="310"/>

<img src="/assets/section009.png" alt="mesh_front" width="310"/>
<img src="/assets/top009.png" alt="mesh_back" width="310"/>

<img src="/assets/section010.png" alt="mesh_front" width="310"/>
<img src="/assets/top010.png" alt="mesh_back" width="310"/>

<img src="/assets/section012.png" alt="mesh_front" width="310"/>
<img src="/assets/top012.png" alt="mesh_back" width="310"/>



### Poroelasticity equations in dental biomechanics

The periodontal ligament (PDL) is a soft connective tissue that attaches a tooth to the alveolar bone.
The PDL is mainly composed of collagene fibers and an interstitial fluid.
Understanding the mechanical response in both physiological and pathological cases
is fundamental for the early detection of PDL diseases, like the parodontisis.

To take into accont the biphasic composition of the PDL
and the large deformations that may occur in the PDL ,
nonlinear Biot's equations of poroelasticity are employed.
Moreover, fine meshes are necessary to accurately represents the complicated geometrical structure of the PDL.

Below, you see the mesh of a two-root porcine tooth-PDL system.
<img src="/assets/images/01dental/mesh_front.pdf" alt="mesh_front" width="200"/>
<img src="/assets/images/01dental/mesh_back.pdf" alt="mesh_back" width="200"/>

The mesh of the PDL is colored in blue,
while the mesh of the tooth is in pink.
In red, we report the surface on which
the external displacement is imposed
and the reaction force is measured.

In order to simulate the indentation experiments on the tooth,
we have implemented a coupled elastic-poroelastic model in the software **UG**.
The tooth is modeled as an elastic body,
while the PDL as a poroelastic bosy.

In the figures below, we report the boundary stressed resulting from the application
of an external displacement (Dirichlet boundary conditions) of 0.1 mm (left)
and of 0.2 mm (right).
<img src="/assets/images/01dental/front10.pdf" alt="mesh_front" width="300"/>
<img src="/assets/images/01dental/front20.pdf" alt="mesh_back" width="300"/>


In the figures below, we report the pressure distribution in the PDL
due to the imposition external displacement (Dirichlet boundary conditions) of 0.1 mm (left)
and of 0.2 mm (right).
<img src="/assets/images/01dental/back10.pdf" alt="mesh_front" width="300"/>
<img src="/assets/images/01dental/back20.pdf" alt="mesh_back" width="300"/>

