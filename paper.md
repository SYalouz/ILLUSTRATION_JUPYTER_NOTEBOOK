---
title: 'QuantNBody: a python package for methodological developments in quantum chemistry and many-body Hamiltonians'
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
 - name: Laboratoire de Chimie Quantique, 4 rue Balise Pascal, 67000 Strasbourg, France
   index: 1
date: 11 March 2022
bibliography: paper.bib
 
---

# Summary

'QuantNBody' is a Python package providing numerical tools for quantum chemists/physicists interested in the development of methodologies to study quantum many-body problems ranging from electronic structure to condensed matter. It provides a quick and easy way to build matrix representations of quantum many-operators (e.g. hamiltonians, spin operators) and get access to important quantities/objects (e.g. reduced density matrices, many-body wave functions). The code comes with various native operators implemented and is flexible enough to help users in building new types of operators. 

# Statement of need


The so-called exact diagonalization method is an important tool to get access to exact properties
of either ab initio or model quantum many-body systems. In practice, it requires to
develop a code that can encode a sparse matrix representation of quantum
operators (e.g. the Hamiltonian of a system) in a given quantum many-body basis.
Usually this aspect is kept as a blackbox in packages (e.g. hidden
inside the code) to spare the user with the cumbersome numerical parts especially for applications.
However, this blackbox approach turns out to be problematic for researchers in need
of numerical tools to develop and test new methodologies and theories. 

The Python package 'QuantNBody' has been developed to help theoreticians in quantum chemistry and physics
who need a quick and easy way to numerically create and manipulate objects linked to many-body systems.
The package framework is based on the creation of numerical matrix representation of quantum operators
in a given many-body basis with a special enphasis on fermionic system (note that extensions are
planned to include bosonic systems).

The framework of the 'QuantNBody' package stand on two fundamental steps :

- Creating a reference many-body basis (based on a total number of quantum particles and modes/orbitals to fill).
- Creating a matrix representation of a general object operator called $a^\dagger a$.

Once these two ingredients have been created, the user can provide the so-called general $a^\dagger a$
operator to already-built functions in order to built quantum Hamiltonian of his/her choice. The user can also 
use this same operator to build his/her own objects.

# A quick illustration

One of the most emblematic operators in quantum many-body theory which is already built in the 'QuantNBody' package is the ab initio electronic structure Hamiltonian from quantum chemistry which reads
\begin{equation} 
\hat{H} = \sum_{p,q} h_{pq} \sum_\sigma^{\uparrow,\downarrow} a^\dagger_{p,\sigma} a_{q,\sigma} 
+ \sum_{p,q,r,s}  g_{pqrs} \sum_{\sigma,\tau}^{\uparrow,\downarrow} a^\dagger_{p,\sigma} a^\dagger_{r,\tau} a_{s,\tau} a_{q,\sigma} + E_{nuc}
\end{equation}
In practice, the QuantNBody package manages on its own the building of all the one- and two-body fermionic operators (i.e. the operators $a^\dagger_{p,\sigma} a_{q,\sigma}$ and $a^\dagger_{p,\sigma} a^\dagger_{r,\tau} a_{s,\tau} a_{q,\sigma}$) via the already built object $a^\dagger a$. The one-/two-electron integrals and nuclear repulsion (i.e. $h_{pq}$, $g_{pqrs}$ and $E_{nuc}$) however have to be obtained (very easily) from external chemistry python packages like PySCF or Psi4. Once these parameters are provided to QuantNBody, one can (i) build the Hamiltonian in its entierity (or in an active space representation) and diagonalize it (ii) check the many-body decomposition of the resulting eigenstates $ | \Psi_k \rangle $, (iii) Build spin operators $S^2$ (or $S_z$, $S_x$ and $S_y$) to check the spin properties of the resulting states.

The picture shows linking the QuantNBody package

