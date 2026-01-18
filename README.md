# Functional Calmodulin States are Selected from an Electrostatically Tuned Free Energy Landscape

This repository contains simulation data and analysis workflows used to map the **conformational free-energy landscape of calmodulin (CaM)**.

Using **well-tempered metadynamics** and **classical molecular dynamics**, the study identifies distinct CaM conformational states and examines how **electrostatics and calcium binding** regulate their populations and kinetic accessibilit.


### Repository Structure

#### `1 μs cMD Simulations`
Analysis of **1 μs unbiased MD simulations** of apo CaM under low-salt conditions, including:
- RMSD analysis
- Reduced collective variables (dihedral angle and linker distance) [1]
- Comparison with experimental structures



#### `MetaD`
Analysis of **well-tempered metadynamics simulations** of CaM in holo/apo states under low-salt and physiological conditions, including:
- Free-energy (PMF) landscapes
- Hills analysis
- Comparison with experimental conformations



#### `cMD_from_MetaD_Conformers`
Classical MD simulations of **conformers selected from MetaD free-energy minima**, including:
- Dihedral–distance analysis
- Salt-bridge analysis
- Radial distribution function (RDF) analysis



Each directory contains its own detailed `README.md` describing the analyses and data therein.

### References

[1] Aykut, A. O., Atilgan, A. R., & Atilgan, C.  
*Designing Molecular Dynamics Simulations to Shift Populations of the Conformational States of Calmodulin.*  
PLOS Computational Biology **9** (2013).  
https://doi.org/10.1371/journal.pcbi.1003366


