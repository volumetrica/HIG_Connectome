# HIG_Connectome

Geometric Homological Incidence Graph (HIG) descriptors for **functional-connectivity matrices**.

This repository adapts the intrinsic HIG (4,8) / combinatorial HIG (8,4) construction to atlas-ordered correlation matrices used in functional-connectome research. The HIG mathematical construction is credited to the prior methodological HIG work; the focus here is on **connectome applications and reproducible experiments**.

## Notebook

[▶ Open the notebook in Google Colab](https://colab.research.google.com/github/volumetrica/HIG_Connectome/blob/main/HIG_connectomes_reales_Colab.ipynb)

1. Open the Colab notebook and run its setup cells.
2. Supply square `N × N` matrices in `.csv`, `.txt`, or `.npy` format (or an archive of matrices).
3. Configure the ROI count, Pearson correlation vs. Fisher-z input, the fixed ROI ordering and the segmentation thresholds.
4. Add a subject/group manifest for group comparisons (see `manifest_hig_connectomes_example.csv`).
5. Run HIG construction, incidence checks, feature extraction and grouped evaluation.

## Scientific interpretation

A HIG hole in an atlas-ordered correlation image is **not** the same as a homology class of the abstract brain network. ROI ordering is deliberately fixed and part of the image coding. Changes in index ordering may change HIG geometry.

Results from synthetic matrices are only functional checks. No real-data clinical or HCP classification results are claimed here.

## Reproducibility and data

Report atlas version, ROI ordering, correlation estimator, signed threshold scheme, diagonal handling, subject-level splits and software versions. Avoid uploading participant identifiers, restricted neuroimaging files or sensitive clinical metadata.

## Project status

Research prototype. The notebook has undergone synthetic smoke tests, but published results require independent verification on real connectome datasets and comparisons against simpler region-adjacency and geometric baselines.

## Licensing

No software license has yet been assigned; one should be chosen after reviewing attribution and reuse conditions of the underlying HIG notebook.
