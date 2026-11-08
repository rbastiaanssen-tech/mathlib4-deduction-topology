# The Topologies of Formal Deduction: Lean 4 Mathlib Audit
### Supplementary Code & Replication Package (Double-Blind Review)

This repository contains the complete empirical codebase, extraction filters, native C++ Flagser reduction wrappers, and visualization scripts for the submitted manuscript.

## Quickstart (Google Colab / Jupyter)
You can run the entire audit with a single click in Jupyter or Google Colab:
1. Open `notebooks/mathlib_topological_audit_clean.ipynb`.
2. Upload the raw environment graph `mathlib4_deps.gexf` (or download it from the anonymous dataset link).
3. Select **Runtime -> Run all**.

The notebook will automatically:
- Install all necessary dependencies (`networkx`, `ripser`, `scipy`, `matplotlib`).
- Clone and build the native C++ `flagser` solver.
- Purge 43,299 compiler-synthesized declarations.
- Generate directed `.flag` files with ancestor cone Jaccard weights ($w = 0.30 + 0.70 \cdot J(u,v)$).
- Compute directed persistent homology ($H_0$, $H_1$, Epistemic Disparity Index, cycle retention $H_1/C$).
- Reproduce the Epistemic Morphospace and comparative Betti figures.

## Directory Structure
- `notebooks/`: Contains `mathlib_topological_audit_clean.ipynb`, the clean, verified replication notebook.
- `scripts/`: Modular Python runner scripts.
- `data/`: Destination directory for input `.gexf` graphs and output `.flag` / `.txt` persistence diagrams.
- `requirements.txt`: Python package specifications.

## Local Command-Line Execution
```bash
pip install -r requirements.txt
python scripts/run_audit.py
```

## Large Dataset Download
Due to file size constraints, pre-computed `.flag` input files and Flagser barcode text files can be downloaded from the anonymous repository mirror.
