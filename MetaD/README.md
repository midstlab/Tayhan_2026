# Supplementary Information  
**Metadynamics (MetaD) Analysis of Calmodulin (CaM)**

This directory contains analysis of **well-tempered metadynamics (MetaD) simulations** of Calmodulin (CaM), focusing on **free-energy landscapes** defined by dihedral angle and linker distance collective variables.

The results are compared with **experimental NMR and X-ray structures** and with the **1 μs cMD simulations** described in the corresponding README.



## MetaD_PMF_Data

### `pmf_plot_script.ipynb`

This notebook plots **potential mean force (PMF)** landscapes of CaM obtained from **well-tempered metadynamics simulations**.

The PMF files are used to visualize the energy landscapes of CaM in:

- **Ca²⁺-bound (holo)** and **Ca²⁺-free (apo)** states  
- **Low-salt (l)** and **physiological (p)** ionic strength conditions  

The PMF data are:
- **Normalized** by the energy value of **3CLN**, used as the initial structure
- **Scaled** within the energy range **(−9, 6)**

### Experimental structure overlay

- **Experimental NMR and X-ray structures** (see *1 μs cMD Simulations* README)
- Overlaid on PMF plots for direct comparison between **MetaD free-energy minima** and experimentally observed conformations

### Three-dimensional PMF landscapes

- Three-dimensional PMF surfaces are also plotted to visualize the **depth of free-energy minima**

### Minimum energy reporting

- In the final block of the notebook, the **minimum free-energy value** corresponding to a given **dihedral angle and linker distance** is reported.



## MetaD_Hills_Data

### `hills_plot.ipynb`

This notebook analyzes **`hills.traj` files**, which are another output of MetaD simulations.

- `hills.traj` files record the **evolution of collective variables throughout the simulation**
- The notebook visualizes how the sampled dihedral angle and linker distance evolve over time



## experimental_structures

This directory contains **experimental structures** used in the study.

### Contents
- **NMR and X-ray PDB files** of experimental CaM structures used in this work

### `dihedral_distance_nmr.ipynb`

- Performs the same dihedral angle and linker distance calculations as  
  `dihedral_distance_calculator.ipynb` in the *1 μs cMD Simulations* directory
- Applied specifically to **experimental structures**

### `unification_nmr_dihedral_distance.ipynb`

- Unifies dihedral angle and linker distance files for experimental structures
- Adds:
  - An **energy column**
  - A **numerical label** (e.g. 6.0, 8.0 )

These labels are used to:
- Overlay experimental structures onto **PMF plots**
- Overlay experimental structures onto **dihedral–distance plots** in the  
  *1 μs cMD Simulations* directory
- Easily control **scatter coloring and grouping** in the plots

---

This directory provides the MetaD-based free-energy perspective of CaM dynamics and enables direct comparison between **MetaD**, **cMD**, and **experimental structures** in the same reduced collective-variable space.
