
**cMD Simulations of Conformers Selected from MetaD Minima**

This directory contains **classical MD (cMD) simulations** of CaM conformers selected from **free-energy minima identified in MetaD simulations**.  
The analyses focus on comparing **structural and interaction features** of these conformers across different **functional states** and **salt conditions**.



## dihedral_distance

This directory includes dihedral angle and linker distance analyses for the selected conformers.

- Dihedral angle and linker distance data are calculated as in the *1 μs cMD Simulations* analysis.

### `cMD_conformers_dih_dist.ipynb`

- Plots dihedral angle versus linker distance for **four selected conformers**
- Shown as a **four-panel plot** corresponding to holo/apo and low-salt/physiological conditions
- Within each panel, conformers are **overlaid** for comparison



## saltbridges

This directory contains salt bridge analyses for all selected conformers and systems.

- Salt bridge occupancy files (`*detail.dat`) were generated using **VMD**

### `filtering_occupancies.ipynb`

- Filters salt bridge occupancies **exceeding 20%**
- Applied to all conformers and systems

### `saltbr_selected.ipynb`

- Plots **salt bridge distances** for **unique salt bridges**
- Analysis shown **throughout the trajectory** for **conformer 4**


## rdf_results

This directory contains **radial distribution function (RDF)** analyses.

- RDFs were calculated using **VMD** by executing the script:
  - `rdf_calculation.tcl`

### `rdf_plotting.ipynb`

- Plots RDF results for the selected conformers
- Used to analyze **local structural environments** and **ion/residue distributions**



This directory provides a detailed characterization of **MetaD-selected conformers** using cMD simulations, enabling comparison of **global conformational metrics**, **salt bridge interactions**, and **local structural properties** under different s conditions.
