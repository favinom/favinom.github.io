---
layout: single
title:  "Flow and transport in fractured porous media"
# date:   2022-09-17 00:05:13 +0200
# categories: jekyll update
exampleFigure: pressure_small_features_new-eps-converted-to.png
---


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

<img src="/assets/images/06flow-and-transport-equi/maria_n_1.png" alt="mesh_front" width="300"/>
<img src="/assets/images/06flow-and-transport-equi/maria_n_2.png" alt="mesh_front" width="300"/>

<img src="/assets/images/06flow-and-transport-equi/maria_n_3.png" alt="mesh_front" width="300"/>
<img src="/assets/images/06flow-and-transport-equi/maria_n_4.png" alt="mesh_front" width="300"/>

Pressure distribution in flow simulation.
<img src="/assets/images/06flow-and-transport-equi/pressure_small_features_new-eps-converted-to.png" width="500"/>


Concentration distribution in three different time steps.
<img src="/assets/images/06flow-and-transport-equi/c3_small_features_new-eps-converted-to.png" width="500"/>


