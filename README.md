# Training-Free LLM-Generated Text Detection Ensemble

This repository contains the complete experiment notebook and generated result figures for a training-free ensemble approach to LLM-generated text detection.

The proposed method combines Lastde/Lastde++ and Fast-DetectGPT using normalized score averaging without additional detector training.

## Main Implementation

The complete experimental implementation is provided in ensemble_experiment.ipynb.

## Results

Generated experimental figures are provided under esults/figures/.

## Reproducibility

The notebook contains the experiment workflow, detector execution, score processing, ensemble construction, evaluation, and visualization steps.

Datasets, pretrained models, external detector repositories, and API credentials are not included in this repository. They must be obtained or configured separately when required.

API keys and other credentials must never be committed to GitHub.
