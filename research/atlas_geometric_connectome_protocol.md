# Anatomically constrained functional-connectome scales

Research extension, 2026-11-13. Proposal only; no new clinical results are claimed.

## Definitions

Take atlas regions R_1,...,R_n in a documented fixed order and a real signed symmetric Pearson correlation matrix C in that exact order. Build a binary symmetric anatomical adjacency N, N_ii=0, with N_ij=1 iff the two atlas parcels share a voxel face in a specified volumetric atlas and spatial resolution. Other anatomical-adjacency conventions are distinct experiments.

Let d_N(i,j) be the shortest-path distance in N, with infinity for disconnected vertices. Define the exact shell K_k(i,j)=1[d_N(i,j)=k], and the cumulative mask K_<=k(i,j)=1[i!=j and d_N(i,j)<=k]. Then the geometry-masked functional matrices are C_k^g=K_k ⊙ C and C_<=k^g=K_<=k ⊙ C. The exact shells partition reachable pairs and their squared-correlation energies sum to the total off-diagonal energy on reachable ROI pairs.

The integral matrix power (N^k)_ij counts walks of length k, not pairs at shortest-path distance k. Shells must be derived from shortest paths, not just the support of N^k. C_k^g is real-valued and cannot directly be passed to an integer Smith-normal-form routine.

## Generalized inverses and s² caution

For the integer SNF U N V = diag(d_1,...,d_r,0...), define G_Q = V diag(1/d_1,...,1/d_r,0...) U. It is a rational reflexive generalized inverse: NG_QN=N and G_QNG_Q=G_Q. It need not satisfy Moore–Penrose conditions. An integer generalized inverse G_Z satisfying NG_ZN=N exists exactly when every nonzero Smith invariant factor is 1. A proposed alternating family based on N, N^T N or G_Q requires explicit verification of the retained s²-model axioms; neither masking nor SNF proves this structure automatically.

## Protocol for a reproducible future evaluation

1. Obtain the atlas and connectome data from their original owners. Record dataset DOI, atlas name/version, voxel-space and resolution, parcel IDs, ROI ordering, Pearson versus Fisher-z input, sign convention, diagonal handling, participant/condition grouping and source license.
2. Construct N from the documented anatomical contact rule, verify symmetry, zero diagonal and connected components. If using the same Schaefer-100/17-networks atlas and 6-face adjacency, compare to the stored edge list in volumetrica/alternating-hypergraph-scales-amai/experiments/rieck_schaefer100_v24 (356 edges reported there).
3. Compute exact shells, cumulative masks and integer walk powers; check the shell partition and off-diagonal squared-energy identity. Use per-shell pair counts for normalization.
4. Predefine global mean/RMS, shell energies, walk-weighted statistics and event-driven threshold descriptors; compare distinct raw-correlation levels against the separate rowwise tolerance-gap construction without conflation.
5. Compare to global/geometry-free controls and degree-aware randomized geometry baselines. Keep all task conditions of the same participant together in outer test folds; tune preprocessing, thresholds, scale depth and model parameters in inner folds.
6. Report subject-level splits, uncertainty, paired baselines, software versions and atlas sensitivity. Avoid claiming superiority or clinical generalization based on exploratory comparisons.
7. Do not redistribute restricted MRI data or identifiable participant metadata.

## Existing related experiment

The separate alternating-hypergraph-scales-amai repository's [V24 report](https://github.com/volumetrica/alternating-hypergraph-scales-amai/tree/main/experiments/rieck_schaefer100_v24) describes a 20-subject / 60-matrix Rieck functional-connectome pilot with genuine atlas geometry. It found no improvement over a two-feature global reference. This HIG repository has its own image-based incidence interpretation and does not identify a HIG image hole with an abstract brain-network homology class.

## References and provenance

- Rieck et al., Data in Brief (2021), https://doi.org/10.1016/j.dib.2021.107573
- Public Rieck matrices: https://github.com/giuliabaracc/covSTATIS_netneuro
- Schaefer atlas: https://github.com/ThomasYeoLab/CBIG
- Existing HIG reproducibility notebook: ../HIG_connectomes_reales_Colab.ipynb