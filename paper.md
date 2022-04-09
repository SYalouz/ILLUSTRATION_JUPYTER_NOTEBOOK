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


This Python package provides numerical tools for quantum chemists/physicists interested in the development of methodologies to study quantum many-body problems ranging from electronic structure to condensed matter. It provides a quick and easy way to build matrix representations of quantum many-operators (e.g. hamiltonians, spin operators) and get access to important quantities/objects (e.g. reduced density matrices, many-body wave functions). The code comes with various native operators implemented and is flexible enough to help users in building new types of operators. 

# Statement of need

Exact diagonalization method is an important tool to get access to exact properties
of either ab initio or model quantum many-body systems. In practice, it requires to
develop a code that can encode a matrix representation of quantum
operators (e.g. the Hamiltonian of a system) in a given quantum many-body basis.
Usually in numerical packages, this practical aspect is kept as a “blackbox” (e.g. hidden
inside the code) to spare the user with these cumbersome numerical parts. This practice is
particularly suitable for realizing application however, it turns out to be problematic
for researchers in need of numerical tools to develop and test new methodologies and theories. 



The Python package 'QuantNBody' has been developed to help theoreticians in quantum chemistry and physics who need a quick and easy way to numerically create and manipulate objects linked to quantum many-body systems. All of its framework is based on the creation of matrix representation of quantum operators in a given many-body basis. 

The framework of the package is focus on two fundamental steps which are :

Creating a many-body basis

the particle number preserving operator 

$ a^\dagger a $
