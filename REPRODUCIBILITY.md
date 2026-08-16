# Reproducibility Guide

## Main Experiment

The complete experimental workflow is provided in `ensemble_experiment.ipynb`.

The notebook contains the dataset preparation, detector execution, score processing, ensemble construction, evaluation, and result-generation workflow used in the study.

## Raw Experimental Results

The `results/lastde_backup.zip` archive contains the saved experimental outputs generated during the Colab experiments, including:

- Lastde/Lastde++ detection results
- Fast-DetectGPT / sampling-discrepancy results
- HLPC benchmark results
- DetectRL benchmark results
- EvoBench results
- Paraphrased datasets/results
- Different text-length conditions
- `results_summary.csv`

The archive is retained as a single file to preserve the original experimental artifacts without unnecessarily duplicating files in the repository.

## Figures

The `results/figures/` directory contains the figures generated from the experiments and used for analysis and presentation.

## Running the Notebook

The notebook was developed for Google Colab.

1. Open `ensemble_experiment.ipynb` in Google Colab.
2. Mount Google Drive when prompted.
3. Make the required datasets and model resources available.
4. Execute the notebook cells in their intended order.
5. The detector outputs and derived results can be saved to the experiment backup directory.
6. The generated figures can be reproduced from the corresponding analysis cells.

## Important Note

The repository contains the complete experiment notebook and saved experimental artifacts. Some external datasets, pretrained models, and third-party detector repositories are not redistributed here and may need to be obtained from their respective original sources.

