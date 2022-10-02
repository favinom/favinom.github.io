---
layout: archive # category
title: Software
permalink: /software/
author_profile: true
---

### Parrot2

[Parrot2](github.com/favinom/parrot2) is an app developed
inside the finite element framework [MOOSE](https://mooseframework.inl.gov).
Parrot2 solves Darcy's flow and transport equations in fractured porous media.
Similar to Parrotc, it exploits adaptive mesh refinement to adapt an initial uniform mesh to any fracture distribution.
Parrot2 is developed together with [Maria Nestola](https://github.com/MGCN).
You can download Parrot2 at this [link](github.com/favinom/parrot2).
The versions [Parrot_real](https://github.com/favinom/parrot_real) and [Parrot](https://github.com/favinom/parrot)
provide the same functionalities but relies on old implementations, which are slower.

### GFEM_acoustic

[GFEM_acoustic](https://github.com/esotelog/GFEM_acoustic) is an application
developed in the FE framework [Deal.II](https://www.dealii.org)
to solve transient wave propagation using a Generalized Finite Element Method.
Accuracy and efficiency of the GFEM approach has been assessed against a spectral element method.
GFEM_acoustic has been employed in the simulation of relevant models to exploration seismology.
GFEM_acoustic has been developed together with [Edith Sotelo](https://github.com/esotelog)
and
can be download at this [link](https://github.com/esotelog/GFEM_acoustic).

### Parrotc

Parrotc is an app developed inside the finite element framework [MOOSE](https://mooseframework.inl.gov).
Parrotc relies on MOOSEc
to exploit complex-type variables to solve poroelasticity equations in fractured media in the frequency-space domain.
The use of complex variables allows for an enormous speed-up in the assembly and solution time.
Parrotc exploits adaptive mesh refinement to adapt an initial uniform mesh to any fracture distribution.
Parrotc allows to set different material properties to the background and to each fracture.
Parrotc allows for 3D simulations, two fluid-phases, and partially saturated fractures.
Moreover, it exploits several optimization with respect to standard MOOSE apps.
MOOSEc is not publicly available, it is stored at the [Source Code Management server](Source Code Management)
of USI and SUPSI. If you are interested, please contact me.

### MOOOSEc

MOOSEc is a fork from the finite element framework [MOOSE](https://mooseframework.inl.gov).
It makes MOOSE compatible with complex-type variables.
MOOSEc has been developed together with [Eric Botter](https://github.com/EricBotter/).
MOOSEc is not publicly available, it is stored at the [Source Code Management server](Source Code Management)
of USI and SUPSI. If you are interested, please contact me.

### Rabbit

[Rabbit](github.com/favinom/rabbit) is an app developed into the FE framework [MOOSE](https://mooseframework.inl.gov).
Rabbit allows for electrophysiology simulations by means of an operator splitting approach
and a hybrid CPU-GPU architecture. While the diffusion term is solved by means of an implicit scheme,
the reaction term is treated explicitely and can be combined with several GPU implementations of ionic currents.
Rabbit has been developed together with [Simone Pezzuto](https://github.com/pezzus).

### Mech

Mech is an app developed into the FE framework [MOOSE](https://mooseframework.inl.gov).
Mech allows to perfom continuum mechanics simulations, such as non-linear elasticty,
fluid dynamics, and Fluid-Structure Interaction.
Mech is developed together with [Maria Nestola](https://github.com/MGCN).
Mech is not publicly available, it is stored at the [Source Code Management server](Source Code Management)
of USI and SUPSI. If you are interested, please contact me.

[Pony](https://github.com/Silvia-Caligari/pony) is an app which allows for the simulation of Monodomain models employing high-order time intefration schemes. Pony is developed together with [Silvia Caligari](https://github.com/Silvia-Caligari).


### Hart and Pony

Hart is an app developed into the FE framework [MOOSE](https://mooseframework.inl.gov).
Hart allows to simulate action potential propagation inside the cardiac tissue both
with monodomain model and Eikonal equation. Hart is developed together with [Maria Nestola](https://github.com/MGCN)
and Sonia Pozzi. Hart is not publicly available, it is stored at the [Source Code Management server](Source Code Management)
of USI and SUPSI. If you are interested, please contact me.

[Pony](https://github.com/Silvia-Caligari/pony) is an app which allows for the simulation of Monodomain models employing high-order time intefration schemes. Pony is developed together with [Silvia Caligari](https://github.com/Silvia-Caligari).


### UG

**UG** is a flexible software system for numerical simulation of PDE-based models on high performance computers.
**UG** is widely used by several research groups in Europe.
I was responsible for the development of a fast template-based assembly library
for the discretization of PDEs for the Lugano branch of UG.
I worked with Prof. Rolf Krause, Dr. Dorian Krause, Dr. Johanner Steiner (integration of finite volume into UG),
Dr. Lea Conen and Dr. Christian Gross (fast linear algebra), Dr. Hardik Kothari (parallelization with DDD).
The current version [**UG4.0**](https://gcsc.uni-frankfurt.de/simulation-and-modelling/ug4) is developed and mantained
at the [Goethe Center for Scientific Computing (G-CSC)](https://gcsc.uni-frankfurt.de).

If intersted in UG4.0, you can contact [Arne Naegel](https://gcsc.uni-frankfurt.de/simulation-and-modelling/people).
