### System and Simulation Details

A **1 μs all-atom molecular dynamics (MD) simulation** of **apo Calmodulin (CaM)** was performed under **low salt** condition.  
The simulation was used to characterize **large-scale conformational motions** of CaM and to compare **MD-sampled conformations** with **experimentally resolved structures**.



### RMSD Analysis

**Notebook:** `rmsd_plot.ipynb`

Root-mean-square deviation (**RMSD**) values were calculated throughout the trajectory for:

- **N-lobe**
- **C-lobe**
- **Linker region**

This analysis was used to assess **region-specific structural stability and flexibility** over the course of the simulation.



### Definition of Reduced Collective Variables

**Notebook:** `dihedral_distance_calculator.ipynb`

Two reduced collective variables were defined to describe global conformational motions of CaM.

#### Linker end-to-end distance (*l*<sub>linker</sub>)

- Distance between the **start and end residues of the linker region**
- Describes **linker bending motion**

#### Torsion angle (φ)

- Describes **rotational motion between the N- and C-lobes**
- Defined using the centers of mass of:
  - N-lobe
  - C-lobe
  - Start of the linker
  - End of the linker

<img width="961" height="346" alt="image" src="https://github.com/user-attachments/assets/3890e1b1-9560-4763-a787-827b63753b72" />



#### Calculation of Collective variables

**Notebook:** `dihedral_distance_calculator.ipynb`

This notebook generates the following raw data files from the MD trajectory:

- **`apo_l_1000_dihedral.dat`**  
  Torsion angle (φ) values calculated along the trajectory

- **`apo_l_1000_distance.dat`**  
  Linker end-to-end distance values calculated along the trajectory



#### Data Processing

**Notebook:** `unify_dihedral_distance_files.ipynb`

- Combines the separately calculated dihedral and distance `.dat` files
- Produces a unified file:

  - **`dihedral_distance_apo_l_1000.txt`**

This unified file is used for subsequent analysis and visualization.



#### Dihedral–Distance Analysis

**Notebook:** `dihedral_distance_code.ipynb`

The reduced collective variables were visualized as **two-dimensional density distributions**:

- **X-axis:** Torsion angle (φ)
- **Y-axis:** Linker end-to-end distance (*l*<sub>linker</sub>)

#### Overlay of Experimental Structures

Experimental structures were overlaid on the density plots for comparison with MD-sampled conformations:

- **NMR structures**
  - Shown as **black points**

- **X-ray crystal structures**
  - **1PRW:** −42.6°, 21.63 Å
  - **3CLN:** 98.92°, 33.80 Å
  - Shown as **teal points**

Both **NMR and X-ray structures** are included in:

- `apo.txt`
- `holo.txt`



### Data Files

- **`apo_l_1000_dihedral.dat`**  
  Raw torsion angle values extracted from the MD trajectory

- **`apo_l_1000_distance.dat`**  
  Raw linker end-to-end distance values extracted from the MD trajectory

- **`dihedral_distance_apo_l_1000.txt`**  
  Unified dihedral angle and linker distance file used for plotting

- **`apo.txt`**  
  Dihedral angle and linker distance values for **experimental apo CaM structures**  
  (includes both **NMR** and **X-ray** structures)

- **`holo.txt`**  
  Dihedral angle and linker distance values for **experimental holo CaM structures**  
  (includes both **NMR** and **X-ray** structures)


This Supplementary Information provides a reduced-dimensional description of CaM conformational dynamics and enables direct comparison between **MD simulations**, **NMR ensembles**, and **X-ray crystal structures**.
