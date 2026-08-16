# Training-Free LLM-Generated Text Detection Ensemble

This repository contains the implementation and experimental artifacts for a study on **training-free detection of LLM-generated text**. The work investigates whether combining two complementary training-free detectors, **Lastde/Lastde++** and **Fast-DetectGPT**, can improve detection performance and robustness across different datasets and experimental conditions.

The proposed ensemble combines normalized detector scores without training an additional classification model.

---

## 1. Overview

Recent advances in large language models have made automatically generated text increasingly difficult to distinguish from human-written text. Detection performance can also vary depending on the dataset, text length, generator model, and whether the text has been paraphrased.

This work evaluates two training-free detection approaches:

* **Lastde/Lastde++**
* **Fast-DetectGPT**

and investigates a simple score-based ensemble of their outputs.

The ensemble first normalizes the detector scores and then combines them using fixed score averaging. No additional detector-specific training is performed for the ensemble.

The experiments focus on comparing the individual detectors with the proposed ensemble under multiple benchmark and robustness conditions.

---

## 2. Detection Methods

### Lastde/Lastde++

Lastde/Lastde++ is a training-free detection approach that uses statistics derived from token probability sequences and related diversity/entropy characteristics of generated text.

### Fast-DetectGPT

Fast-DetectGPT is a training-free detection method based on the conditional probability curvature of text under a language model.

### Proposed Ensemble

The proposed ensemble combines the outputs of Lastde/Lastde++ and Fast-DetectGPT.

Since the two methods produce scores on different scales, the scores are normalized before being combined. The resulting ensemble score is then used for detection and evaluation.

The ensemble does not introduce a separately trained classifier.

---

## 3. Experimental Evaluation

The experiments investigate detector performance under several conditions, including:

* Different benchmark datasets
* Different LLM generator conditions
* Different text-length settings
* Original and paraphrased text
* Cross-dataset evaluation
* Detector comparison
* Performance degradation under paraphrasing and other conditions

The saved experimental artifacts include results associated with datasets and benchmark suites such as:

* XSum
* Reddit
* WritingPrompts
* SQuAD
* HLPC
* DetectRL
* EvoBench

The exact conditions and corresponding experiment files are documented in the notebook and saved result archive.

---

## 4. Evaluation Metrics

The experiments use the following evaluation measures:

* AUROC
* TPR at low false-positive rates
* F1-score
* Accuracy
* Performance degradation / robustness measures

The main comparisons consider the performance of Lastde/Lastde++, Fast-DetectGPT, and the proposed ensemble across the evaluated conditions.

---

## 5. Repository Contents

```text
training-free-llm-detection-ensemble/
│
├── ensemble_experiment.ipynb
│
├── results/
│   ├── figures/
│   │   ├── confusion_matrix_xsum.pdf
│   │   ├── degradation_delta_chart.pdf
│   │   ├── generator_comparison.pdf
│   │   ├── overall_auroc_summary.pdf
│   │   ├── roc_curve_xsum.pdf
│   │   ├── score_distribution_writing_paraphrased.pdf
│   │   └── score_distribution_xsum.pdf
│   │
│   └── lastde_backup.zip
│
├── README.md
├── REPRODUCIBILITY.md
├── LICENSE
└── .gitignore
```

### `ensemble_experiment.ipynb`

The main notebook containing the implementation and experimental workflow.

It includes the code used for detector execution, score processing, ensemble construction, evaluation, and result visualization.

### `results/lastde_backup.zip`

An archive containing the saved detector outputs and other experimental result files generated during the experiments.

The archive includes outputs for the evaluated datasets and experimental conditions, as well as the summarized result file.

### `results/figures/`

Contains the figures generated from the experimental analysis.

Current figures include:

* `confusion_matrix_xsum.pdf`
* `degradation_delta_chart.pdf`
* `generator_comparison.pdf`
* `overall_auroc_summary.pdf`
* `roc_curve_xsum.pdf`
* `score_distribution_writing_paraphrased.pdf`
* `score_distribution_xsum.pdf`

### `REPRODUCIBILITY.md`

Provides additional information about the experimental workflow, required resources, and how the notebook and saved artifacts are organized.

---

## 6. Running the Experiments

The main implementation is provided as a Jupyter notebook:

```text
ensemble_experiment.ipynb
```

The experiments were developed and executed primarily using **Google Colab**.

A typical execution workflow is:

1. Open the notebook in Google Colab.
2. Configure the required runtime.
3. Mount Google Drive where required.
4. Obtain the required datasets and model resources.
5. Install or clone the required external dependencies.
6. Run the notebook cells in sequence.
7. Generate detector outputs and evaluation results.
8. Generate the analysis figures.

Some experiments require GPU resources and pretrained language models.

The notebook contains the commands and paths used during the experimental workflow.

---

## 7. Saved Experimental Results

The repository includes the detector outputs generated during the experiments so that the reported analysis does not depend solely on re-running the original experiments.

The saved archive contains result files corresponding to different experimental settings, including:

* XSum
* Reddit
* WritingPrompts
* SQuAD
* HLPC
* DetectRL
* EvoBench
* Paraphrased datasets
* Text-length conditions
* Different generator conditions

The archive also contains:

```text
results_summary.csv
```

which provides the summarized experimental results used in the analysis.

---

## 8. External Dependencies and Resources

The experiments rely on external datasets, pretrained language models, and third-party implementations of detection methods.

These resources are **not included directly in this repository**.

In particular, the experimental workflow uses resources associated with:

* Lastde/Lastde++
* Fast-DetectGPT
* Transformer-based language models
* Hugging Face model resources
* The benchmark datasets used in the experiments

Users attempting to reproduce the experiments should obtain these resources from their respective original sources and follow their licenses and usage requirements.

---

## 9. API Credentials

Some parts of the notebook use external API services.

No actual API credentials are stored in this repository.

Where required, the notebook uses placeholders such as:

```python
GROQ_API_KEY = "YOUR_GROQ_API_KEY_HERE"
```

Users must provide their own credentials when running the relevant cells.

API keys, access tokens, and other credentials should never be committed to the repository.

---

## 10. Reproducibility

The repository provides both the experimental implementation and the saved outputs used during the analysis.

The main materials are:

```text
Implementation
    └── ensemble_experiment.ipynb

Saved experimental outputs
    └── results/lastde_backup.zip

Generated figures
    └── results/figures/

Reproducibility notes
    └── REPRODUCIBILITY.md
```

The saved outputs are provided to make the experimental analysis inspectable without requiring the original Colab runtime or previously executed session.

Re-running the experiments may produce differences depending on the versions of external libraries, models, datasets, runtime environment, and available computational resources.

---

## 11. Current Research Status

This repository is part of an ongoing research study and is intended to document the implementation, experimental workflow, and results used for the current stage of the work.

The repository may be updated as the experiments and analysis are refined.

The associated research manuscript is not included in this repository at this stage.

---

## 12. License

This repository is released under the **MIT License**.

See [`LICENSE`](LICENSE) for the full license text.

The datasets, pretrained models, and third-party implementations used by the experiments may have separate licenses and terms of use. Users are responsible for complying with those terms when obtaining or using the corresponding resources.

---

## 13. Acknowledgements

This work builds upon publicly available research, datasets, pretrained models, and third-party implementations developed by the research community.

The original authors and maintainers of the underlying detection methods and benchmark resources are acknowledged for making their work available for research purposes.
