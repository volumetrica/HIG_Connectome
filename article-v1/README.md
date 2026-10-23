# Article v1: geometric HIG analysis of functional connectomes

**Status: methodological draft; real-data empirical evaluation pending.** The PDF manuscript and reproducibility bundle were prepared in the companion ChatGPT conversation and require repository upload. Do not represent synthetic evaluation as real fMRI evidence.

The manuscript concerns an atlas-ordered correlation-matrix HIG application, citing the earlier HIG theory instead of reproving the original method.

## Reproducible public-data source

ADHD-200-derived 190×190 functional connectivity matrices, Figshare CC0: https://doi.org/10.6084/m9.figshare.16437534

Secondary HCP public resource: https://doi.org/10.5281/zenodo.6770120

## Experiments executed so far

30 synthetic positive-semidefinite correlation matrices (N=12,20,32, 2 factor settings, 5 replicates each): basic HIG4/HIG8 consistency checks passed. Ten ROI ordering permutations of a synthetic N=20 matrix were computed.

**No empirical neuroimaging classifier AUC or diagnostic group tests have been executed in this version.**

## Intended tracked assets

- HIG_connectome_article_v1.tex / .pdf
- HIG_connectomes_realdata_article_Colab.ipynb
- run_experiments.py
- figures/synthetic_connectome_hig.png and synthetic_runtime.png
- results/synthetic_hig_features.csv and synthetic_ordering.csv

The full archive is available from the research conversation until these files are committed here.
