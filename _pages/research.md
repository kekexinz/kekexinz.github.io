---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
redirect_from:
  - /resume
---

Table of content
- [Research vision](#research-vision)
- [Research projects](#research-projects)
  - [1. MDO with general dynamical systems and control](#1-mdo-with-general-dynamical-systems-and-control)
  - [2. The algorithmic differentiation (AD) formula and the adjoint development](#2-the-algorithmic-differentiation-ad-formula-and-the-adjoint-development)
  - [3. Machine learning in aerodynamic shape optimization](#3-machine-learning-in-aerodynamic-shape-optimization)
  - [4. Wind turbine aerostructural optimization](#4-wind-turbine-aerostructural-optimization)
  - [5. Aerodynamic shape optimization with laminar-turbulent transition model](#5-aerodynamic-shape-optimization-with-laminar-turbulent-transition-model)

# Research vision
My research is driven by the critical applications required by the industry and the government.
I am passionate about math and programming.
In my research, I use mathematical tools to convert the previous untackled problem into a formulation that can be solved efficiently and I develop programs to solve the problems on a large scale.
The potential impact areas of my research include aerospace, wind energy, robotics, and automobile industries.
My previous research was funded by AFOSR, ARPA-e, and FAA.
An overview of my research is shown below:

![Drag Racing](../images/balls.001.png)

The research vision that differentiates me from other labs working on MDO is listed below:
1. **(Theory)** MDO shall be enabled to address ever **more complex dynamical systems and control problems** beyond the current focus, i.e., the steady-state problems.
2. **(Implementation/code)** **Efficient and general-purpose codes** for design optimization in dynamical systems and control shall be developed leveraging the abstraction ability of the mathematical representation.
3. **(Application)** I develop **environmentally friendly engineering designs**, such as efficient off-shore wind turbines, and aircraft with less noise and emission, to address critical climate and energy challenges of modern society.


<!-- 
1. Big picture
   1. Why MDO.
   2. Why MDO + control.
2. Zoom in, what I do
-->

# Research projects

## 1. MDO with general dynamical systems and control
Dynamical system is universal.
In MDO, the last decades, most of the research projects focus on fixed point, and little previous research are on bifurcation, LCO, and chaotic systems.
One example is transonic buffet constraint, a bifurcation triggered by shock wave and boundary layer interaction, has not been modeled using first principle in MDO.
Also, the control as a fundamental discipline in aerospace engineering, has been largely overlooked in the previous research due to its high computational cost. 
The question I am trying to answer in this research is:
**How can we optimize a general dynamical system (with or without control) performance using MDO?**

To answer the question, I develop:
1. Fundamental derivative computation methods using the adjoint method and algorithmic differentiation. 
2. High-fidelity model-based code implementation.

Notably, for the category 1, I develop an algorithm that demontrate that the closed-loop control co-design problem can be solved at a cost independent with the number of design variables. 
Another highlight of this category is that I develop a fundamental method to discover reverse algorithmic differentiation formula using the forward algorithmic differentiation formula for complex analytic equation and I am **the first to discover** (see the following [section](#2-the-algorithmic-differentiation-ad-formula-and-the-adjoint-development)) a succint eigenvalue derivative formula for a general complex matrix.
A list of publication for category (1) is shown below. 

__Publication:__


|        |  |
|   :-:    | -       |  
| <img src='../images/publication/complex_eigen.png' align="center" width="200" height="10"> | __Sicheng He__, Yayun Shi, Eirikur Jonsson, Joaquim R. R. A. Martins.  <br><br> [__Eigenvalue problem derivatives computation for a complex matrix using the adjoint method__](https://www.researchgate.net/publication/362931690_Eigenvalue_problem_derivatives_computation_for_a_complex_matrix_using_the_adjoint_method)  <br><br> _MSSP_ (2022).|
| <img src='../images/publication/eigenXDSM.png' align="center" width="200" height="10"> | __Sicheng He__, Eirikur Jonsson, and joaquim R. R. A. Martins.  <br><br> [__Derivatives for Eigenvalues and Eigenvectors via Analytic Reverse Algorithmic Differentiation__](https://arc.aiaa.org/doi/abs/10.2514/1.J060726?journalCode=aiaaj)  <br><br> _AIAA Journal_ (2022).|

For the category (2), we focus on CFD-based aeroelastic LCO (flutter) suppression problem.
Using our proposed methods, we obtain **the-first-of-it-kind** high-fidelity aerodyanmic shape optimization for a wing using the time-spectral method which improves the flutter speed by 118\%.
This is my PhD project and I was awarded an AIAA aviation conference **best student paper award** for this research.
A list of publication for category (2) is shown below. 

|        |  |
|   :-:    | -       |  
| <img src='../images/publication/flutter_opt.png' align="center" width="200" height="10"> | __Sicheng He__, Eirikur Jonsson, Joaquim R. Martins. <br><br> [__Wing Aerodynamic Shape Optimization with Time Spectral Limit-Cycle Oscillation Adjoint__](https://arc.aiaa.org/doi/abs/10.2514/6.2022-3357). <br><br> _In AIAA Aviation, Chicago, IL, June 2022. American Institute of Aeronautics and Astronautics_.|
| <img src='../images/publication/83.png' align="center" width="200" height="10"> | __Sicheng He__, Eirikur Jonsson, Charles A. Mader, and Joaquim R. R. A. Martins. <br><br> [__Coupled Newton–Krylov timespectral solver for ﬂutter and limit cycle oscillation prediction__](https://arc.aiaa.org/doi/10.2514/1.J059224)  <br><br> _AIAA Journal_ (2021).|
| <img src='../images/publication/flutter_fine_ezgif.gif' align="center" width="200" height="10"> | __Sicheng He__, Eirikur Jonsson, Charles A. Mader, and Joaquim R. R. A. Martins. <br><br> [__A coupled Newton–Krylov time-spectral solver for wing ﬂutter and LCO prediction__](https://arc.aiaa.org/doi/10.2514/6.2019-3549). <br><br> _In AIAA Aviation Forum, Dallas, TX, June 2019_. (Best student paper award, 2nd place)|


## 2. The algorithmic differentiation (AD) formula and the adjoint development

Did you know that there is a very elegant equation to compute eigenvalue derivatives with respect to all the entries of the matrix for real and symmetric matrix?

$$
\frac{\mathrm{d} \lambda}{\mathrm{d} \mathbf{A}} = 
\frac{\boldsymbol{\phi}\boldsymbol{\phi}^T}{\boldsymbol{\phi}^T\boldsymbol{\phi}},
$$

where $\mathbf{A}$ is a real and symmetric coefficient matrix,  $\lambda$ is an eigenvalue, and $\boldsymbol{\phi}$ is a corresponding eigenvector. 

We discovered in this [paper](https://www.researchgate.net/publication/362931690_Eigenvalue_problem_derivatives_computation_for_a_complex_matrix_using_the_adjoint_method) a general version of this formula for a complex non-Hermitian matrix.

$$
\begin{aligned}
\frac{\mathrm{d} \lambda_r}{\mathrm{d} \mathbf{A}} &= \frac{\tilde{\boldsymbol{\phi}}\boldsymbol{\phi}^*}{\boldsymbol{\phi}^*\tilde{\boldsymbol{\phi}}}, \\
\frac{\mathrm{d} \lambda_i}{\mathrm{d} \mathbf{A}} &=  i\frac{\mathrm{d} \lambda_r}{\mathrm{d} \mathbf{A}},\\
\end{aligned}
$$

where $\mathbf{A}$ is a general complex coefficient matrix,  $\lambda = \lambda_r + i \lambda_i$ is an eigenvalue, $\boldsymbol{\phi}$ is a corresponding right eigenvector, and $\tilde{\boldsymbol{\phi}}$ is the corresponding left eigenvector.

The tools we developed in the second approach turns out to be very general and they can be applied to any eigenvalue and eigenvector derivatives of generalized eigenvalue problems with complex coefficient matrices.
Besides, we also generalize the method to derive RAD formulas based on [dot-product-identity](https://people.maths.ox.ac.uk/gilesm/files/NA-08-01.pdf) proposed by Prof. Giles from real functions to complex analytic functions.

__Publication:__


|        |  |
|   :-:    | -       |  
| <img src='../images/publication/complex_eigen.png' align="center" width="200" height="10"> | __Sicheng He__, Yayun Shi, Eirikur Jonsson, Joaquim R. R. A. Martins.  <br><br> [__Eigenvalue problem derivatives computation for a complex matrix using the adjoint method__](https://www.researchgate.net/publication/362931690_Eigenvalue_problem_derivatives_computation_for_a_complex_matrix_using_the_adjoint_method)  <br><br> _MSSP_ (2022).|
| <img src='../images/publication/eigenXDSM.png' align="center" width="200" height="10"> | __Sicheng He__, Eirikur Jonsson, and joaquim R. R. A. Martins.  <br><br> [__Derivatives for Eigenvalues and Eigenvectors via Analytic Reverse Algorithmic Differentiation__](https://arc.aiaa.org/doi/abs/10.2514/1.J060726?journalCode=aiaaj)  <br><br> _AIAA Journal_ (2022).|

## 3. Machine learning in aerodynamic shape optimization

|        |  |
|   :-:    | -       |  
| <img src='../images/publication/buffet.png' align="center" width="200" height="10"> | Jichao Li, __Sicheng He__, Mengqi Zhang, Joaquim R. R. A. Martins, Boo Cheong Khoo.  <br><br> [__Physics-Based Data-Driven Buffet-Onset Constraint for Aerodynamic Shape Optimization__](https://arc.aiaa.org/doi/10.2514/1.J061519)  <br><br> _AIAA Journal_ (2022).|
| <img src='../images/publication/transonic.png' align="center" width="200" height="10"> | Mohamed Amine Bouhlel, __Sicheng He__, and Joaquim R. R. A. Martins. <br><br> [__Scalable gradient-enhanced artiﬁcial neural networks for airfoil shape design in the subsonic and transonic regimes__](https://link.springer.com/article/10.1007/s00158-020-02488-5)  <br><br> _Structural and Multidisciplinary Optimization_ (2020). (Webfoil)|
| <img src='../images/publication/stream.png' align="center" width="200" height="10"> | Jichao Li, __Sicheng He__, and Joaquim R. R. A. Martins. <br><br> [__Data-driven constraint approach to ensure low-speed performance in transonic aerodynamic shape optimization__](https://www.sciencedirect.com/science/article/pii/S1270963819304912)  <br><br> _Aerospace Science and Technology_ (2019).|

## 4. Wind turbine aerostructural optimization

__Publication:__


|        |  |
|   :-:    | -       |  
| <img src='../images/publication/FIG2.jpg' align="center" width="200" height="10"> | Denis-Gabriel Caprace, Adam Cardoza, Teagan Nakamoto, Andrew Ning, Marco Mangano, __Sicheng He__, and Joaquim R. R. A. Martins. <br><br> [__Incorporating high-ﬁdelity aerostructural analyses in wind turbine rotor optimization__](https://arc.aiaa.org/doi/abs/10.2514/6.2022-1290). <br><br> _In AIAA Scitech, San Diego, CA, January 2022. American Institute of Aeronautics and Astronautics_.|
| <img src='../images/publication/Span_comparison.png' align="center" width="200" height="10"> | Marco Mangano, __Sicheng He__, Denis-Gabriel Caprace, Yingqian Liao, and Joaquim R. R. A. Martins. <br><br> [__Passive aeroelastic tailoring of large wind turbines using high-ﬁdelity multidisciplinary design optimization__](https://arc.aiaa.org/doi/abs/10.2514/6.2022-1289). <br><br> _In AIAA Scitech, San Diego, CA, January 2022. American Institute of Aeronautics and Astronautics_.|

## 5. Aerodynamic shape optimization with laminar-turbulent transition model

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