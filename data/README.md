Explainable AI for Detecting Code–Comment Inconsistencies
Description

This repository contains the code and experiments for the study “Explainable AI for Detecting Code–Comment Inconsistencies”.
The project investigates the use of pretrained transformer-based models to detect semantic inconsistencies between source code and comments in Java programs and applies explainable AI techniques to interpret model predictions.

The repository includes Colab notebooks for data preprocessing, model training and evaluation, explainability analysis using SHAP, and result generation.

Dataset Information

This study uses the DeepJIT dataset introduced by Panthaplackel et al. (2020) for detecting inconsistencies between source code and comments.

Dataset name: DeepJIT

Programming language: Java

Subset used: @summary

Analysis setting: Just-in-time

Dataset source: https://github.com/panthap2/deep-jit-inconsistency-detection


Code Information

The repository is organized as follows:

notebooks/
  01_train_eval_codebert.ipynb
  02_train_eval_graphcodebert.ipynb
  03_train_eval_longformer.ipynb
  04_shap_generate_outputs.ipynb
  05_shap_tp_tn_fp_fn_analysis.ipynb
  06_confusion_matrix_full_test.ipynb
  07_confusion_matrix_shap_subset.ipynb

data/
  README.md

results/
  tables/
  figures/
  shap_output/


Training notebooks fine-tune and evaluate CodeBERT, GraphCodeBERT, and Longformer.

Explainability notebooks apply SHAP to analyze Longformer predictions.

Confusion matrix notebooks generate evaluation summaries for the full test set and the SHAP subset.

All figures and tables reported in the manuscript are saved locally under results/.

Usage Instructions

To reproduce the experiments:

Download the DeepJIT dataset and place it in the data/ directory

Install the required dependencies (see Requirements below).

Run the notebooks in order from 01_train_eval_codebert.ipynb to 07_confusion_matrix_shap_subset.ipynb.

Generated outputs (metrics, figures, SHAP plots) will be saved under the results/ directory.

Requirements

The experiments were conducted using Python 3.10.

Key dependencies include:

torch

transformers

scikit-learn

pandas

numpy

shap

matplotlib

Methodology

The workflow implemented in this repository follows these main steps:

Data preprocessing and formatting of code–comment pairs from the DeepJIT dataset.

Fine-tuning pretrained transformer models (CodeBERT, GraphCodeBERT, Longformer) for binary classification.

Evaluation using accuracy, precision, recall, and F1-score.

Selection of a subset of test instances for explainability analysis.

Application of SHAP to interpret Longformer predictions at local and global levels.

Analysis of error patterns using confusion matrices and class-specific explanations.

Model Checkpoints

Trained model checkpoints are not included in this repository due to file size constraints.

The best-performing Longformer checkpoint used for explainability analysis can be made available upon reasonable request.

Citations

If you use the dataset, please cite:

@inproceedings{PanthaplackelETAL21DeepJITInconsistency,
  author = {Panthaplackel, Sheena and Li, Junyi Jessy and Gligoric, Milos and Mooney, Raymond J.},
  title = {Deep Just-In-Time Inconsistency Detection Between Comments and Source Code},
  booktitle = {AAAI},
  pages = {427--435},
  year = {2021},
}

License

This repository is provided for research and educational purposes.

Contributions

Issues and pull requests related to reproducibility, documentation, or minor fixes are welcome.
