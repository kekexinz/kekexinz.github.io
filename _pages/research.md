---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
redirect_from:
  - /resume
---

<!-- Check out my recent [presentation](https://github.com/SichengHe/MIT_LAE_seminar/blob/main/Sicheng_He_seminar.pdf)!-->

Table of content
- [Research vision](#research-vision)
- [Research projects](#research-projects)
  - [1. Multiscale modeling of RNA structures using NMR chemical shifts](#1-multiscale-modeling-of-rna-structures-using-nmr-chemical-shifts)
  - [2. _in situ_ cryo-EM single particle classification](#2-in-situ-cryo-em-single-particle-classification)
  - [3. 2DTM statistical metric for robust target detection](#3-2dtm-statistical-metric-for-robust-target-detection)
  - [4. Structure determination of sub-50 kDa complexes](#4-structure-determination-of-sub-50-kda-complexes)


# Research vision
My research focuses on developing quantitative models for cells, cellular compartments, and biochemical pathways using cryo-electron microscopy (cryo-EM) and tomography (cryo-ET). This interdisciplinary work, summarized in Fig. 1, is driven by a central goal: to uncover the mechanisms by which biomolecules perform specific cellular functions and to design and discover novel therapeutics. Our research aims to revolutionize cryo-EM/ET image processing and quantitatively analyze experimental data using techniques from the fields of statistics and computer science.

The development of direct electron detectors (DEDs) and high-performance computing has enabled structure determination of purified macromolecules at atomic resolution through single-particle cryo-EM. Additionally, thinned cellular samples can be prepared by focused ion beam (FIB) and imaged via cryo-ET to reconstruct the 3D organization of cellular environments. However, the resolution of cryo-ET-derived tomograms remains limited, requiring subtomogram averaging to achieve high-resolution structures. To address this limitation, my research is driven by the following fundamental question: How do we maximize the information that can be extracted from images of radiation-sensitive biological samples to understand the structure-function relationship of biomolecules in cells?

Advancements in microscope hardware and image processing methods are required to improve signal-to-noise ratio and data throughput. My research lab will combine numerical analysis and deep learning algorithms to improve cryo-EM/ET data processing workflows. Specifically, building on the high-resolution 2D template matching (2DTM) approach developed in my postdoctoral lab [1, 2], I will leverage the expanding repository of high-resolution structures and AlphaFold predictions as prior information to detect more challenging targets in images of diverse types of specimens.

<div style="text-align: center;">
    <img src="../images/balls.png" alt="Vision of research" width="600">
</div>

The research vision that differentiates me from other labs working on MDO is listed below:
1. **(Theory)** MDO shall be enabled to address ever **more complex dynamical systems and control problems** beyond the current focus, i.e., the steady-state problems.
2. **(Implementation/code)** **Efficient and general-purpose codes** for design optimization in dynamical systems and control shall be developed leveraging the abstraction ability of the mathematical representation.
3. **(Application)** I develop **environmentally friendly engineering designs**, such as efficient off-shore wind turbines, and aircraft with less noise and emission, to address critical climate and energy challenges of modern society.


# Research projects

## 1. Multiscale modeling of RNA structures using NMR chemical shifts

The central dogma of molecular biology states that genetic information is stored in DNA and passed to proteins by RNA. 
The proteins then carry out the cellular functions encoded by genetic information from DNA. 
Thus, for a long time, RNA was considered to be the intermediate of genetic information.
However, it was discovered that only 2\% of the human genome is translated into proteins, and the remaining transcripts are thought to be functional non-coding RNAs (ncRNAs). 
**To carry out biological functions, some ncRNAs may sample different conformational states and fluctuate between a ground state and transient states contingent on environmental conditions.** The structures of these transient RNA states provide significant information regarding their function. 

Solution state NMR has been the primary technique for RNA structure determination, and NMR-derived chemical shifts are considered structural “fingerprints” of RNA conformational state(s). **My PhD thesis aimed to develop computational methods to accurately model the structures (secondary structures in particular) of RNA conformational states**, including sparsely populated transient states, based on their chemical shift signatures. 

Accurately determining the structure of an RNA is the first step in studying its spatiotemporal properties. To address this challenge, I developed three computational frameworks - **CS-Fold**, **CS-BME**, and **CS-Annotate** - that utilize readily accessible NMR chemical shifts to achieve the following objectives: guiding _de novo_ RNA (secondary) structure prediction, probabilistically modeling the conformational landscape of RNA ensembles, and evaluating the quality of RNA structural models. These tools incorporate a variety of machine learning techniques.

<!-- [baseline](../images/research/baseline.gif)
![optimized](../images/research/optimized.gif)-->

__Publication:__


|        |  |
|   :-:    | -       |  
| <img src='../images/publication/codesign.png' align="center" width="200" height="10"> | __Sicheng He__, Shugo Kaneko, Eirikur Jonsson, Marco Mangano, Joaquim R. R. A. Martins.  <br><br> [__Control co-design sensitivity computation using the adjoint method__](https://www.researchgate.net/publication/362931690_Eigenvalue_problem_derivatives_computation_for_a_complex_matrix_using_the_adjoint_method)  <br><br> _submitted to SIAM applied dynamics (SIADS)_ (2022).|
| <img src='../images/publication/LST.png' align="center" width="200" height="10"> | __Sicheng He__, Eirikur Jonsson, Joaquim R. R. A. Martins.  <br><br> [__Adjoint-based Linear stability constrained design optimization__](https://www.researchgate.net/publication/362931690_Eigenvalue_problem_derivatives_computation_for_a_complex_matrix_using_the_adjoint_method)  <br><br> _submitted to SIAM applied dynamics (SIADS)_ (2022).|
| <img src='../images/publication/LCO_stability.png' align="center" width="200" height="10"> | __Sicheng He__, Eirikur Jonsson, Joaquim R. R. A. Martins.  <br><br> [__Adjoint-based Limit Cycle Oscillation Instability Sensitivity and Suppression__](https://www.researchgate.net/publication/363581644_Adjoint-based_Limit_Cycle_Oscillation_Instability_Sensitivity_and_Suppression)  <br><br> _Nonlinear dynamics_ (2022).|
| <img src='../images/publication/complex_eigen.png' align="center" width="200" height="10"> | __Sicheng He__, Yayun Shi, Eirikur Jonsson, Joaquim R. R. A. Martins.  <br><br> [__Eigenvalue problem derivatives computation for a complex matrix using the adjoint method__](https://www.researchgate.net/publication/362931690_Eigenvalue_problem_derivatives_computation_for_a_complex_matrix_using_the_adjoint_method)  <br><br> _MSSP (accepted)_ (2023).|
| <img src='../images/publication/eigenXDSM.png' align="center" width="200" height="10"> | __Sicheng He__, Eirikur Jonsson, and joaquim R. R. A. Martins.  <br><br> [__Derivatives for Eigenvalues and Eigenvectors via Analytic Reverse Algorithmic Differentiation__](https://arc.aiaa.org/doi/abs/10.2514/1.J060726?journalCode=aiaaj)  <br><br> _AIAA Journal_ (2022).|

## 2. _in situ_ cryo-EM single particle classification

![Flutter](../images/publication/flutter_fine_ezgif.gif)

The next-generation aircraft are trending with more flexible wings.
This makes the aircraft wings more susceptible to flutter.
However, the state-of-art MDO problem formulation usually only includes a steady-state aerostructure module and rarely a low-fidelity flutter module.
The missing or inaccurate flutter modeling in the aircraft conceptual design stage may cause costly redesign if the flutter is found in a later stage.
The fundamental question that I want to answer is that:
**How to design the future aircraft free from flutter?**
Answering this question, the aircraft designs generated from MDO will be much more realistic.

This project is closely related to the previous project because the aeroelastic problem is categorized as an LCO problem from the perspective of dynamical system theory.
To answer the question, we developed novel algorithms using time spectral method, Newton--Krylov method, and the coupled adjoint method to obtain good scalability with respect to both state and design variables.
The key finding of the research is that for LCO problem, it has a unique problem structure that shall be exploited by the solver to obtain the best computational performance.
Using our proposed methods, we obtain **the-first-of-it-kind** high-fidelity CFD-based aerodynamic shape optimization for a wing using the time-spectral method that improves the flutter speed by 118%.
This is my Ph.D. project. 
I was awarded an AIAA Aviation Conference **best student paper award**.

|        |  |
|   :-:    | -       |  
| <img src='../images/publication/flutter_opt.png' align="center" width="200" height="10"> | __Sicheng He__, Eirikur Jonsson, Joaquim R. Martins. <br><br> [__Wing Aerodynamic Shape Optimization with Time Spectral Limit-Cycle Oscillation Adjoint__](https://arc.aiaa.org/doi/abs/10.2514/6.2022-3357). <br><br> _In AIAA Aviation, Chicago, IL, June 2022. American Institute of Aeronautics and Astronautics_.|
| <img src='../images/publication/83.png' align="center" width="200" height="10"> | __Sicheng He__, Eirikur Jonsson, Charles A. Mader, and Joaquim R. R. A. Martins. <br><br> [__Coupled Newton–Krylov timespectral solver for ﬂutter and limit cycle oscillation prediction__](https://arc.aiaa.org/doi/10.2514/1.J059224)  <br><br> _AIAA Journal_ (2021).|
| <img src='../images/publication/flutter_fine_ezgif.gif' align="center" width="200" height="10"> | __Sicheng He__, Eirikur Jonsson, Charles A. Mader, and Joaquim R. R. A. Martins. <br><br> [__A coupled Newton–Krylov time-spectral solver for wing ﬂutter and LCO prediction__](https://arc.aiaa.org/doi/10.2514/6.2019-3549). <br><br> _In AIAA Aviation Forum, Dallas, TX, June 2019_. (Best student paper award, 2nd place)|

## 3. 2DTM statistical metric for robust target detection

Surrogate models, including the classic and more recent machine learning models, are becoming essential tools for designers because they outperform a direct numerical analysis in speed with similar accuracy,and they can also solve problems without explicit numerical models.
Compared with the classic tools (e.g., the kriging method), machine learning tools (e.g., the deep neural network) suffer less from overfitting and perform better when the data set is large.
With the aforementioned benefits, we want to address the following question in our research:
**How can we accelerate the optimization using machine learning?**


We develop deep neural network-based models to answer this question.
The key finding is that uniformly sampling design space is inefficient.
The design space paramitrization and the sampling shall favor the region with good performance.
As one highlight of the research, we are the first to apply the so-called Sobolev neural network, a gradient-enhanced neural network, to obtain the **state-of-the-art** accurate surrogate model for airfoil aerodynamic parameters, such as lift and drag.
The proposed method enables **real-time** aerodynamic analysis and shape optimization, and it is one of the engines that drive the online airfoil simulation website, [Webfoil](http://webfoil.engin.umich.edu/)
. 


|        |  |
|   :-:    | -       |  
| <img src='../images/publication/buffet.png' align="center" width="200" height="10"> | Jichao Li, __Sicheng He__, Mengqi Zhang, Joaquim R. R. A. Martins, Boo Cheong Khoo.  <br><br> [__Physics-Based Data-Driven Buffet-Onset Constraint for Aerodynamic Shape Optimization__](https://arc.aiaa.org/doi/10.2514/1.J061519)  <br><br> _AIAA Journal_ (2022).|
| <img src='../images/publication/transonic.png' align="center" width="200" height="10"> | Mohamed Amine Bouhlel, __Sicheng He__, and Joaquim R. R. A. Martins. <br><br> [__Scalable gradient-enhanced artiﬁcial neural networks for airfoil shape design in the subsonic and transonic regimes__](https://link.springer.com/article/10.1007/s00158-020-02488-5)  <br><br> _Structural and Multidisciplinary Optimization_ (2020). (Webfoil)|
| <img src='../images/publication/stream.png' align="center" width="200" height="10"> | Jichao Li, __Sicheng He__, and Joaquim R. R. A. Martins. <br><br> [__Data-driven constraint approach to ensure low-speed performance in transonic aerodynamic shape optimization__](https://www.sciencedirect.com/science/article/pii/S1270963819304912)  <br><br> _Aerospace Science and Technology_ (2019).|

## 4. Structure determination of sub-50 kDa complexes

![Wind turbine](../images/research/wind_turbine.gif)

The state-of-the-art design optimization in the field assumes that the structure is rigid and the coupling between the structure and fluid is neglected.
In effect, such assumptions become problematic as the size of the wind turbine increases to improve efficiency and the structure is becoming more flexible.
In addition, by considering the coupling effect, we can explore a larger design space and design more efficient wind turbines.
In this research, the pressing question we plan to address is: **How can we optimize the wind turbine design with both structural and aerodynamic shape variables and account for their coupling?**

To answer that question, we apply the MDO algorithms together with computational fluid dynamics (CFD) and finite element analysis (FEA) tools. 
The key finding of the research is that the aeroelastic coupling can be exploited to reduce the structure mass by about 2.2% compared with an optimized design without the coupling.
We obtained **the-first-of-it-kind** high-fidelity aerostructural optimization for wind turbines.
We are currently exploring using the composite to obtain passive load alleviation to further improve the performance of the wind turbine designs.

__Publication:__


|        |  |
|   :-:    | -       |  
| <img src='../images/publication/FIG2.jpg' align="center" width="200" height="10"> | Denis-Gabriel Caprace, Adam Cardoza, Teagan Nakamoto, Andrew Ning, Marco Mangano, __Sicheng He__, and Joaquim R. R. A. Martins. <br><br> [__Incorporating high-ﬁdelity aerostructural analyses in wind turbine rotor optimization__](https://arc.aiaa.org/doi/abs/10.2514/6.2022-1290). <br><br> _In AIAA Scitech, San Diego, CA, January 2022. American Institute of Aeronautics and Astronautics_.|
| <img src='../images/publication/Span_comparison.png' align="center" width="200" height="10"> | Marco Mangano, __Sicheng He__, Denis-Gabriel Caprace, Yingqian Liao, and Joaquim R. R. A. Martins. <br><br> [__Passive aeroelastic tailoring of large wind turbines using high-ﬁdelity multidisciplinary design optimization__](https://arc.aiaa.org/doi/abs/10.2514/6.2022-1289). <br><br> _In AIAA Scitech, San Diego, CA, January 2022. American Institute of Aeronautics and Astronautics_.|