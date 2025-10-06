---
layout: single
title:  "Poroelasticity in dental biomechanics"
# date:   2022-09-17 00:05:13 +0200
categories: jekyll update

# this works only with grid in index.html
#header:
#  teaser: /assets/images/front20.png

teaserNoGrid: front20.png

---


The periodontal ligament (PDL) is a soft connective tissue that attaches a tooth to the alveolar bone.
The PDL is mainly composed of collagene fibers and an interstitial fluid.
Understanding the mechanical response in both physiological and pathological cases
is fundamental for the early detection of PDL diseases, like the parodontisis.

To take into accont the biphasic composition of the PDL
and the large deformations that may occur in the PDL ,
nonlinear Biot's equations of poroelasticity are employed.
Moreover, fine meshes are necessary to accurately represents the complicated geometrical structure of the PDL.

Below, you see the mesh of a two-root porcine tooth-PDL system.
<img src="/assets/images/01dental/mesh_front.png" alt="mesh_front" width="200"/>
<img src="/assets/images/01dental/mesh_back.png" alt="mesh_back" width="200"/>

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
<img src="/assets/images/01dental/front10.png" alt="mesh_front" width="300"/>
<img src="/assets/images/01dental/front20.png" alt="mesh_back" width="300"/>


In the figures below, we report the pressure distribution in the PDL
due to the imposition external displacement (Dirichlet boundary conditions) of 0.1 mm (left)
and of 0.2 mm (right).
<img src="/assets/images/01dental/back10.png" alt="mesh_front" width="300"/>
<img src="/assets/images/01dental/back20.png" alt="mesh_back" width="300"/>
