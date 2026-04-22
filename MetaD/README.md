# Well-Tempered Metadynamics (MetaD) Analysis of Calmodulin (CaM)

This directory contains analyses of **well-tempered metadynamics (MetaD) simulations** of **Calmodulin (CaM)**, focusing on **free-energy landscapes** defined by two collective variables: **dihedral angle** and **linker distance**.

The results are compared directly with **experimental NMR and X-ray structures**.



## Directory Overview

### `MetaD_PMF_Data`

This directory contains notebooks for analyzing and visualizing **potential of mean force (PMF)** data obtained from MetaD simulations.

#### `merge_metad_replicas.ipynb`

This notebook merges PMF data from **two or more MetaD replicas**.

It performs the following steps:

- Reads **2 or more replica PMF files**
- Checks that all PMFs share the same **2D collective-variable grid**
- Merges the PMFs using **Boltzmann/probability averaging**
- Writes the resulting **merged PMF**
  

#### `pmf_plot_script.ipynb`

This notebook plots the **PMF landscapes** of CaM from well-tempered metadynamics simulations.

The PMF data are used to visualize CaM conformational landscapes in:

- **Ca²⁺-bound (holo)** and **Ca²⁺-free (apo)** states
- **Low-salt (l)** and **physiological (p)** ionic strength conditions

The notebook includes the following features:

- PMF values are **normalized** using the energy value of **3CLN**, which is the initial structure
- PMFs are **scaled** within the energy range **(-9, 6)**
- **Experimental NMR and X-ray structures** are overlaid for comparison (see the *1 μs cMD Simulations* README)
- This enables direct comparison between **MetaD free-energy minima** and **experimentally observed conformations**
- **Three-dimensional PMF surfaces** are also plotted to visualize the **depth of free-energy minima**
- In the final block of the notebook, the **minimum free-energy value** corresponding to a given **dihedral angle** and **linker distance** is reported



### `MetaD_Hills_Data`

This directory contains notebooks for analyzing **`hills.traj`** files, which are another output of MetaD simulations.

#### `hills_plot.ipynb`

This notebook analyzes **`hills.traj`** files.

- `hills.traj` files record the **time evolution of the collective variables** during the simulation
- The notebook visualizes how the sampled **dihedral angle** and **linker distance** evolve over time
- **Only a small portion of the `hills.traj` files is uploaded** because of file size limitations

#### `merge_metad_energies_apo_p.ipynb`

This notebook analyzes hills trajectory data from **two replicas** and computes basin-based **probabilities** and **free energies** for the **apo physiological-salt system**.

It performs the following analyses:

- Reads all **hills trajectory files** from **two replicas**
- Classifies each sampled point into predefined **structural basins**
- Uses the two collective variables:

  - **phi** = torsion angle  
  - **linker** = linker distance

- Determines whether each sampled point falls inside predefined **rectangular basin regions**
- Computes **basin probabilities** and **free energies** in separate **time windows**

The trajectory is divided into three windows:

- **200-400 ns**
- **400-600 ns**
- **600-800 ns**

Within each time window, the notebook:

- Counts how many sampled points fall into each basin
- Converts the counts into **probabilities**
- Computes basin **free energies** using:

F = -k_BT ln(p)

A **pseudocount** is used so that zero counts do not cause numerical problems.

Depending on the system and comparison, the notebook also computes quantities such as:

- **deltaP**
- **deltaF = F2 - F1**

In addition, it generates:

- **summary tables**
- **sanity-check plots**
- final summaries reporting **mean**, **standard deviation (SD)**, and **standard error of the mean (SEM)**



### `experimental_structures`

This directory contains the **experimental structures** used in this study.

It includes:

- **NMR and X-ray PDB files** of experimental CaM structures used in this work

#### `dihedral_distance_nmr.ipynb`

This notebook performs the same **dihedral angle** and **linker distance** calculations as `dihedral_distance_calculator.ipynb` in the *1 μs cMD Simulations* directory.

It is applied specifically to **experimental structures**.

#### `unification_nmr_dihedral_distance.ipynb`

This notebook unifies the dihedral angle and linker distance files generated for the experimental structures.

It adds:

- an **energy column**
- a **numerical label** (for example, **6.0** or **8.0**)

These labels are used to:

- overlay experimental structures onto **PMF plots**
- overlay experimental structures onto **dihedral-distance plots**
- control **scatter coloring and grouping** more easily in the plots



### `example_metad_submission_file`

This directory provides example input files for **well-tempered MetaD simulations**.

It includes:

- example **ionized PDB and PSF files**
- a **collective variables (colvars) file**
- a **MetaD configuration (`.conf`) file**

These files serve as a reference setup for reproducing or adapting the MetaD simulations used in this study.



## Summary

This directory provides a **MetaD-based free-energy perspective** on CaM dynamics and enables direct comparison between **MetaD results** and **experimental structures** within the same reduced collective-variable space.
