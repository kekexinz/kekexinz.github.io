---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
redirect_from:
  - /resume
---

Research vision
======
The past decades see fast progress of the research in steady-state high-fidelity based design optimization.
The state-of-the-art MDO frameworks such as [MACH](https://github.com/mdolab/MACH-Aero) can handle problems with millions of state variables and thousands of design variables.
With the success in steady-state problems, the future research direction of MDO will be shifted towards dynamical system such as limit cycle oscillation and periodic problems.
Building on top of the dynamical system design optimization, the passive plant design will be augumented by control system co-design.
The potential impact areas include aerospace, wind turbine, robotics, and automobiles.
In my research, I develop novel algorithms and programs based on PDE-constrained optimization, dynamical system, and control theories to enable large-scale design optimization with dynamical system and control.

<!-- 
1. Big picture
   1. Why MDO.
   2. Why MDO + control.
2. Zoom in, what I do
-->

Current research
======

Design optimization with dynamical systems and control
------
Wind turbine aerostructural optimization
------

Robust design optimization
------

Past research
======

Machine learning in aerodynamica shape optimization
------

Aerodynamic shape optimization with flutter constraints
------

Aerodynamic shape optimization with laminar-turbulent transition model
------
<!-- __Background:__ The flow over an aircraft wing transits from the orderly laminar flow regime at the leading edge to the chaotic turbulent flow regime at the trailing edge.
The state-of-the-art aerodynamic optimization simulate the flow using the Renoylds average Navier-Stokes (RANS) model together with a turbulence model such as Spalart-Allmaras (SA) model for closure. 
A fully turbulent flow assumption is adopted.
However, as mentioned before, in reality, around the leading edge of the wing, the flow is in the laminar regime that has much less fraction compared that of the turbulent regime.
This is addressed by augumenting the RANS model with a transition model such as the $e^n$ method.

The $e^n$ method accumaltes small local unstable disturbances of the flow, considering it to be laminar.
When the accumlated factor (called $N$ factor) exceeds certain threshold, the flow transit from laminar to turbulent.
The local stability problem is modeled as a generalized eigenvalue problem.
The transition process is initialized at the spot where the maximum real part of the eigenvalues exceeds zero. -->

We apply gradient-based optimization to design more efficient airfoils with the laminar-turbulent transition modeled by the $e^n$ method. 
To compute derivatives with large number of design variables, we use the adjoint method.
One special challenge of the RANS with $e^n$ transition model is that we have the generalized eigenvalue problem embedded in the governing equation. 
We propose two approaches to address this challenge:

1. Using the simplified $e^n$ model that approximate the eigenvalues (Shi2020).
2. Developing an adjoint equation and reverse algorithmic differentiation (RAD) formulas for the generalized eigenvalue problem with complex coefficient matrices (He2022, Shi2022).
  
The tools we developed in the second approach turns out to be very general and they can be applied to any eigenvalue and eigenvector derivatives of generalized eigenvalue problems with complex coefficient matrices.
Besides, we also generalize the method to derive RAD formulas based on [dot-product-identity](https://people.maths.ox.ac.uk/gilesm/files/NA-08-01.pdf) proposed by Prof. Giles from real functions to complex analytic functions.

__Publication:__


|        |  |
|   :-:    | -       |  
| <img src='../images/publication/foil.png' align="center" width="200" height="10"> | Yayun Shi, Charles A. Mader, __Sicheng He__, Gustavo L. O. Halila, and Joaquim R. R. A. Martins. <br><br> [__Natural laminarﬂow airfoil optimization design using a discrete adjoint approach__](https://arc.aiaa.org/doi/10.2514/1.J058944s)  <br><br> _AIAA Journal_ (2020).|
| <img src='../images/publication/complex_eigen.png' align="center" width="200" height="10"> | __Sicheng He__, Yayun Shi, Eirikur Jonsson, and Joaquim R. R. A. Martins. <br><br> [__Eigenvalue problem derivatives computation for a complex matrix using the adjoint method__](../paper/eigen_der_complex.pdf)  <br><br> Submitted to _Mechanical system and signal processing_.|
