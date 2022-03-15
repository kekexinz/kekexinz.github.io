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

Current research
======

Design optimization with dynamical systems and control
------
Wind turbine aerostructural optimization
------
Past research
======

Machine learning in aerodynamica shape optimization
------

Aerodynamic shape optimization with flutter constraints
------

Aerodynamic shape optimization with laminar-turbulent transition model
------
__Background:__ The flow over an aircraft wing transits from the orderly laminar flow regime at the leading edge to the chaotic turbulent flow regime at the trailing edge.
The state-of-the-art aerodynamic optimization simulate the flow using the Renoylds average Navier-Stokes (RANS) model together with a turbulence model such as Spalart-Allmaras (SA) model for closure. 
A fully turbulent flow assumption is adopted.
However, as mentioned before, in reality, around the leading edge of the wing, the flow is in the laminar regime that has much less fraction compared that of the turbulent regime.
This is addressed by augumenting the RANS model with a transition model such as the $e^n$ method.

The $e^n$ method accumaltes small local unstable disturbances of the flow, considering it to be laminar.
When the accumlated factor (called $N$ factor) exceeds certain threshold, the flow transit from laminar to turbulent.
The local stability problem is modeled as a generalized eigenvalue problem.
The transition process is initialized at the spot where the maximum real part of the eigenvalues exceeds zero.

__Contribution:__ To conduct gradient-based optimization, we need to compute the derivatives of the function of interests with large number of design variables efficiently.
We use the adjoint method to compute the derivative.
One special challenge of the RANS with $e^n$ transition model is that we have the generalized eigenvalue problem embedded in the governing equation. 
We propose two approaches to address this challenge:

1. Using the simplified $e^n$ model that approximate the eigenvalues (Shi2020).
2. Developing an adjoint equation and reverse algorithmic differentiation (RAD) formulas for the generalized eigenvalue problem with complex coefficient matrices (He2022, Shi2022).
  
The tools we developed in the second approach turns out to be very general and they can be applied to any eigenvalue and eigenvector derivatives of generalized eigenvalue problems with complex coefficient matrices.
Besides, we also generalize the method to derive RAD formulas based on dot-product-identity proposed by Prof. Giles from real functions to complex analytic functions.

__Publication:__


|        |  |
|   :-:    | -       |  
| <img src='../images/publication/foil.png' align="center" width="200" height="10"> | Yayun Shi, Charles A. Mader, __Sicheng He__, Gustavo L. O. Halila, and Joaquim R. R. A. Martins. <br><br> [__Natural laminarﬂow airfoil optimization design using a discrete adjoint approach__](https://arc.aiaa.org/doi/10.2514/1.J058944s)  <br><br> _AIAA Journal_ (2020).|
| <img src='../images/publication/foil.png' align="center" width="200" height="10"> | __Sicheng He__, Yayun Shi, Eirikur Jonsson, and Joaquim R. R. A. Martins. <br><br> [__Eigenvalue problem derivatives computation for a complex matrix using the adjoint method__](https://arc.aiaa.org/doi/10.2514/1.J058944s)  <br><br> Submitted to _Mechanical system and signal processing_.|
