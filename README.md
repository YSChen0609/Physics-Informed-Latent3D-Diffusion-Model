# Physics-Informed-Latent3D-Diffusion-Model
This is a developmental repo for adding physics-informed features to the Latent3D Graph Diffusion (You et al., ICLR 2024) for docking problems.
The original paper and implementation repo can be found here: https://github.com/Shen-Lab/LDM-3DG

# Problem
The Latent3D Graph Diffusion model is having issues when applying to docking problems. Similar to related research, the model may generate some unrealistic docking outcomes (e.g. collision). We suggest that adding physics-informed features into the model would help improve the accuracy and alleviate the collision issue.

# Data
We use the exact same dataset as the DiffDock.
Including:
 - **PDBBind:** download the processed complexes from [zenodo](https://zenodo.org/record/6408497).
 - **BindingMOAD:** download the processed complexes from [zenodo](https://zenodo.org/records/10656052) under `BindingMOAD_2020_processed.tar`.
 - **DockGen:** download exclusively the complexes of the DockGen benchmark already processed (e.g. chain cutoff) from [zenodo](https://zenodo.org/records/10656052) downloading the `DockGen.tar` file.
 - **PoseBusters:** download the processed complexes from [zenodo](https://zenodo.org/records/8278563).
 - **van der Mers:** the protein structures used for the van der Mers data augmentation strategy were downloaded [here](https://files.ipd.uw.edu/pub/training_sets/pdb_2021aug02.tar.gz).

# Algorithm
