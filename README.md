# Physics-Informed-Latent3D-Diffusion-Model
This is a developmental repo for adding physics-informed features to the Latent3D Graph Diffusion (You et al., ICLR 2024) for docking problems.
The original paper and implementation repo can be found here: https://github.com/Shen-Lab/LDM-3DG

## Problem
The Latent3D Graph Diffusion model is having issues when applying to docking problems. Similar to related research, the model may generate some unrealistic docking outcomes (e.g. collision). We suggest that adding physics-informed features into the model would help improve the accuracy and alleviate the collision issue.

## Data
We use the exact same dataset as the DiffDock.

Including:
 - **PDBBind:** download the processed complexes from [zenodo](https://zenodo.org/record/6408497).
 - **BindingMOAD:** download the processed complexes from [zenodo](https://zenodo.org/records/10656052) under `BindingMOAD_2020_processed.tar`.
 - **DockGen:** download exclusively the complexes of the DockGen benchmark already processed (e.g. chain cutoff) from [zenodo](https://zenodo.org/records/10656052) downloading the `DockGen.tar` file.
 - **PoseBusters:** download the processed complexes from [zenodo](https://zenodo.org/records/8278563).
 - **van der Mers:** the protein structures used for the van der Mers data augmentation strategy were downloaded [here](https://files.ipd.uw.edu/pub/training_sets/pdb_2021aug02.tar.gz).

## Algorithm
The Latent3D Graph Diffusion model is using a **pre-trained Autoencoder** to project input ligand to a latent space. After that, a **diffusion model** is trained in the latent space for generating ligand in the inference mode. The protein is used as a condition for decoder, which consists of 2 parts, giving the topology and 3D coordinates outcomes seperately describing the generated ligand.
The overview of the Latent3D Graph Diffusion model is illustrated below:
![image](https://github.com/YSChen0609/Physics-Informed-Latent3D-Diffusion-Model/assets/143129316/ffc7140e-db10-4d3a-ac7a-deb647e779c7)

**Note that the physics-informed features have not integrated, and not mentioned above since it is still UNDERDEVELOPMENT.**
