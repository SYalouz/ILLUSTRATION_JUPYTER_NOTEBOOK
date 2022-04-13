---
title: 'QuantNBody:  a python package for quantum chemistry and physics to build and manipulate many-body operators and wave functions.'
tags:
  - Python
  - quantum physics and chemistry
  - quantum many-body systems
  - exact diagonalization
authors:
  - name: Saad Yalouz^[yalouzsaad@gmail.com]
    orcid: 0000-0002-8818-3379
    affiliation: 1  # (Multiple affiliations must be quoted)
  - name: Martin Rafael Gullin # note this makes a footnote saying 'Co-first author'
    affiliation: 1
  - name: Sajanthan Sekaran
    affiliation: 1
affiliations:
 - name: Laboratoire de Chimie Quantique, 4 rue Blaise Pascal, 67000 Strasbourg, France
   index: 1
date: 11 March 2022
bibliography: paper.bib
 
---

# Summary

'QuantNBody' is a Python package providing numerical tools for quantum chemists/physicists interested in the development of methodologies to study quantum many-body problems ranging from electronic structure to condensed matter theory. It provides a quick and easy way to build matrix representations of quantum many-operators (e.g. hamiltonians, spin operators) and get access to important quantities/objects (e.g. reduced density matrices, many-body wave functions). The code comes with various native functions and is flexible enough to help users in building new types of many-body operators or quantum states. 

# Statement of need
  
Encoding numerically a quantum many-body system is an important step to get access to exact properties 
of either ab initio or model systems in quantum chemistry and physics.
In practice, it requires to develop a code that builds sparse matrix representations of quantum
operators (e.g. the Hamiltonian of a system) in a given quantum many-body basis.
Usually this aspect is kept as a blackbox in packages (e.g. hidden
inside the code) to spare the user with the cumbersome numerical parts especially for applications.
However, this blackbox approach turns out to be problematic for researchers in need
of numerical tools to develop and test new methodologies and theories. 

The Python package 'QuantNBody' has been designed to help theoreticians in quantum chemistry and physics
who need an easy way to numerically create and manipulate objects linked to many-body systems.
The package framework is based on the creation of numerical matrix representation of quantum operators
in a given many-body basis with a special enphasis on fermionic system (note that extensions are
planned to include bosonic systems).  

The framework of the 'QuantNBody' package lies on two fundamental ingredients. The first one is the creation of a reference
many-body basis (based on a total number of quantum particles and modes/orbitals to fill) in which every operator
can be represented. The second ingredient consists in creating a general tool that can help building any particle-number
conserving many-body operator : the single-body hopping operator $a^\dagger a$.  Once these two ingredients
have been created, the user can employ pre-built functions in order to (i) construct various type of many-body
operators (e.g. hamiltonians, spin operators), (ii) manipulate/visualize quantum many-body states. Note that
the QuantNBody package has been designed to provide flexibility to the user so that the he/she can also create his/her
own operators and functions based on the tools already implemented in the code.

# A quick illustration

A few native many-body operators are already implemented in the QuantNBody package such as the ab initio
electronic structure Hamiltonian from quantum chemistry
\begin{equation} 
\hat{H} = \sum_{p,q} h_{pq} \sum_\sigma^{\uparrow,\downarrow} a^\dagger_{p,\sigma} a_{q,\sigma} 
+ \frac{1}{2} \sum_{p,q,r,s}  g_{pqrs} \sum_{\sigma,\tau}^{\uparrow,\downarrow} a^\dagger_{p,\sigma} a^\dagger_{r,\tau} a_{s,\tau} a_{q,\sigma}  
\end{equation}

or the Fermi-hubbard Hamiltonian from condensed matter theory
\begin{equation} 
\hat{H} = -t  \sum_{i,j} \sum_\sigma^{\uparrow,\downarrow} a^\dagger_{i,\sigma} a_{j,\sigma} 
+ U \sum_{i}  a^\dagger_{i,\uparrow}a_{i,\uparrow} a^\dagger_{i,\downarrow} a_{i,\downarrow}
\end{equation}

where $a^\dagger_{i,\sigma}/a_{i,\sigma}$ are the fermionic creation/annihilation operators (in orbital $i$ with spin $\sigma$).

The QuantNBody package manages on its own the building of all the one- and two-body fermionic operators via the already built object $a^\dagger a$ mentioned earlier. The one-/two-body integrals (i.e.  $h_{pq}$, $g_{pqrs}$  and $t$ and $U$ ) however have to be defined by the user. They can be pure parameters of directly obtained (very easily) from external chemistry python packages like PySCF [@sun2020recent] or Psi4 [@turney2012psi4]. As an illustration, we show in figure 1 a few results one can produce with the package with both types of hamiltonians.
 
![$H_2$ molecule and Fermi-Hubbard dimer. **Left column :** ground state energy and ground state decomposition in the many-body basis for the $H_2$ molecule dissociation in a minimal basis STO-3G. **Right column :** ground state energy and ground state decomposition in the many-body basis for the Fermi-Hubbard dimer as a function of $U$  (2 electrons on 2 sites and $t=1$). \label{fig:example}](figure.png)

The package QuantNBody is currently being used in a number of scientific projects realised in the "Laboratoire de Chimie Quantique de Strasbourg".
These projects are dedicated to the developement of new methodologies to study strongly correlated systems in quantum chemistry and
condensed matter.
 
 
# Acknowledgements

Saad Yalouz acknowledges support from the Interdisciplinary Thematic Institute ITI-CSC
via the IdEx Unistra (ANR-10-IDEX-0002) within the program Investissement d’Avenir.

# References

