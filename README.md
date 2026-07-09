# K-Means Clustering From Scratch

A from-scratch clustering project comparing random centroid initialization with K-Means++ and using elbow curves to reason about cluster count.

## Overview

K-Means is a foundational unsupervised learning algorithm. This project implements and analyzes the clustering loop so initialization, convergence, and inertia are easy to inspect.
The repository includes generated figures for both clustering behavior and initialization comparison.

## Project Design

- Generate or load data for clustering.
- Initialize centroids randomly or with K-Means++.
- Assign points to nearest centroids.
- Update centroids iteratively.
- Use elbow-method plots to compare cluster-count behavior.

## Key Capabilities

- Synthetic dataset generation for controlled experiments.
- K-Means clustering workflow with centroid refinement.
- K-Means++ initialization comparison.
- Elbow-method visualization.
- Saved figures for direct inspection.

## Repository Structure

```text
notebooks/kmeans_clustering.ipynb  Main clustering notebook.
figures/                           Generated clustering and elbow-method plots.
requirements.txt                   Python dependencies.
```

## Running Locally

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook notebooks/kmeans_clustering.ipynb
```

## Results and Artifacts

- `figures/1_generated_dataset.png` shows the generated dataset.
- `figures/1_k-means_on_generated_dataset.png` shows clustering output.
- `figures/2_elbow_method_comparison_k-means++ vs random initialization.png` compares initialization strategies.

## Reproducibility Notes

- Set the random seed before comparing random initialization with K-Means++.
- Regenerate elbow plots after changing the cluster-count range or dataset generator.
- Run the notebook from top to bottom so centroid histories and figures use the same data.
- Interpret inertia together with visual cluster structure because the elbow method is heuristic.

## Detailed Workflow

- Open the notebook and inspect the generated dataset first.
- Run the clustering cells with random initialization.
- Run the K-Means++ initialization comparison.
- Inspect the elbow-method plot to reason about cluster count.
- Compare generated figures with the notebook implementation details.

## Implementation Details

- The project exposes the iterative K-Means loop rather than only relying on a black-box call.
- Centroid initialization is treated as an experimental variable.
- K-Means++ is compared against random initialization to show why initialization matters.
- The elbow-method visualization helps connect inertia to model selection.
- Figures are saved so the final clustering behavior can be inspected directly.

## Data and Inputs

- The notebook includes generated data for controlled clustering analysis.
- The workflow can be adapted to external datasets by replacing the data-loading section.
- Scaling and feature selection can significantly affect clustering quality.
- Generated figures provide a stable record of the current experiment outputs.

## How To Interpret the Results

- Lower inertia usually means tighter clusters, but it does not always mean a better real-world grouping.
- The elbow point is a heuristic and should be interpreted with domain context.
- K-Means++ often improves initialization stability but does not remove all local-minimum issues.
- Cluster plots are easiest to interpret when the data is two-dimensional or projected.

## Limitations and Assumptions

- K-Means assumes compact centroid-shaped clusters.
- Results can change with initialization and random seed.
- The current project is notebook-first and does not expose a CLI.
- Additional metrics such as silhouette score could make comparisons stronger.


## Review Guide

Use this checklist when reviewing the repository on GitHub:

- Start with the overview to understand the project objective before opening notebooks or source files.
- Read the repository structure section to identify the main entry point.
- Inspect generated outputs before rerunning experiments; they provide a quick view of the current project state.
- Review scripts and notebooks together when both are present, since notebooks often explain decisions while scripts preserve reusable execution paths.
- Check the limitations section before interpreting results too strongly.
- Use the possible extensions section to understand how the project can grow without changing its core purpose.

## Troubleshooting

Common issues and fixes:

- If imports fail, confirm that the virtual environment is activated and dependencies were installed from `requirements.txt`.
- If a notebook cell fails because a variable is missing, restart the kernel and run the notebook from the first cell.
- If a script cannot find a data file, run it from the repository root unless the README gives a different working directory.
- If plots are not regenerated, check that the output folder exists and that the script has write permission.
- If a package version causes errors, create a fresh environment and reinstall dependencies before debugging the source code.
- If GPU-related packages are unavailable, run CPU-compatible sections first and treat heavier deep-learning experiments separately.

## Development Notes

The repository is organized to be understandable before it is optimized. Most code favors clear structure, visible intermediate steps, and saved artifacts over highly compressed implementations. When extending the project, prefer small changes that keep the original experiment reproducible.

Recommended development practices:

- Keep new data files under `data/`, `datasets/`, or the existing local data folder for that project.
- Keep generated figures under `figures/`, `plots/`, `outputs/`, or `results/` depending on the existing convention.
- Add new experiments as separate scripts or clearly labeled notebook sections.
- Avoid overwriting existing outputs unless the experiment is intentionally being refreshed.
- Document any new dependency in `requirements.txt`.
- Prefer relative paths so the repository works after cloning on another machine.

## Project Status

This repository is prepared as a standalone GitHub project. The current version includes the core implementation, documentation, and available artifacts needed to understand the work. Future improvements can focus on stronger automation, more tests, richer visual summaries, and cleaner packaging where appropriate.

## Possible Extensions

- Move the clustering implementation into a reusable class.
- Add convergence diagnostics for centroid movement.
- Compare inertia with silhouette scores.
- Add command-line arguments for number of clusters and initialization mode.

## Tech Stack

Python, NumPy, Matplotlib, scikit-learn, tqdm, Jupyter Notebook.

## Author

Prahladha, IIT Hyderabad
