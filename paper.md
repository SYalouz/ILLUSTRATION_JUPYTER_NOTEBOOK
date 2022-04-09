---
title: 'QuantNBody: an exact diagonalization python package for quantum chemistry and many-body Hamiltonians'
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
date: 13 August 2017
bibliography: paper.bib

# Optional fields if submitting to a AAS journal too, see this blog post:
# https://blog.joss.theoj.org/2018/12/a-new-collaboration-with-aas-publishing
aas-doi: 10.3847/xxxxx <- update this with the DOI from AAS once you know it.
aas-journal: Astrophysical Journal <- The name of the AAS journal.
---


# Summary   


'QuantNBody' is a Python package providing numerical tools for quantum chemists/physicists interested in the development of methodologies to study quantum many-body problems ranging from electronic structure to condensed matter. It provides a quick and easy way to build matrix representations of quantum many-operators (e.g. hamiltonians, spin operators) and get access to important quantities/objects (e.g. reduced density matrices, many-body wave functions). The code comes with various native operators implemented and is flexible enough to help users in building new types of operators. 

# Statement of need

The so-called exact diagonalization method is an important tool to get access to exact properties
of either ab initio or model quantum many-body systems. In practice, it requires to
develop a code that can encode a matrix representation of quantum
operators (e.g. the Hamiltonian of a system) in a given quantum many-body basis.
Usually this practical aspect is kept as a blackbox in packages (e.g. hidden
inside the code) to spare the user with these cumbersome numerical parts especially when the target 
user seek for applciations. However, this turns out to be problematic
for researchers in need of numerical tools to develop and test new methodologies and theories. 


The Python package 'QuantNBody' has been developed to help theoreticians in quantum chemistry and physics
who need a quick and easy way to numerically create and manipulate objects linked to many-fermion systems.
All of its framework is based on the creation of numerical matrix representation of quantum operators
in a given many-body basis. 

The framework of the package is focused on two fundamental steps which are :

- The creation of a many-fermion basis (based on a total number of fermion and orbitals).
- The creation of the matrix representation of a general particle-number preserving hopping operator $a^\dagger a$.

The electronic structure Hamiltonian

\begin{equation} 
\hat{H} = \sum_{p,q} h_{pq} \sum_{\sigma}^{\uparrow,\downarrow} a^\dagger_{p,\sigma} a_{q,\sigma} 
+ \sum_{p,q,r,s}  g_{pqrs} \sum_{\sigma,\tau}^{\uparrow,\downarrow} a^\dagger_{p,\sigma} a^\dagger_{r,\tau} a^\dagger_{s,\tau} a_{q,\sigma}
\end{equation}

and the Fermi-Hubbard Hamiltonian 
\begin{equation} 
\hat{H} = \sum_{p,q} h_{pq} \sum_{\sigma}^{\uparrow,\downarrow} a^\dagger_{p,\sigma} a_{q,\sigma} 
+ \sum_{p,q,r,s}  g_{pqrs} \sum_{\sigma,\tau}^{\uparrow,\downarrow} a^\dagger_{p,\sigma} a^\dagger_{r,\tau} a^\dagger_{s,\tau} a_{q,\sigma}
\end{equation}

