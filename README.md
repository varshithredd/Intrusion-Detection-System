# Intrusion Detection System

A Python notebook exploring multiclass network intrusion classification using a CICIDS2017 sample dataset.

## Workflow

- Explore network-flow features and class distributions.
- Encode target labels and handle non-finite feature values.
- Apply SMOTE to address class imbalance.
- Scale features and reduce dimensionality to ten PCA components.
- Train a K-nearest neighbors classifier and compare neighbor counts.
- Inspect classification reports, confusion matrices, and accuracy.

## Technology

Python · NumPy · pandas · matplotlib · seaborn · scikit-learn · imbalanced-learn · Jupyter

## Getting started

```bash
git clone https://github.com/varshithredd/Intrusion-Detection-System.git
cd Intrusion-Detection-System
python -m venv .venv
```

Activate the environment:

```powershell
# Windows PowerShell
.\.venv\Scripts\Activate.ps1
```

```bash
# macOS / Linux
source .venv/bin/activate
```

Install the notebook dependencies:

```bash
python -m pip install jupyter numpy pandas matplotlib seaborn scikit-learn imbalanced-learn
jupyter notebook
```

Place `CICIDS2017_sample.csv` beside [Intrusion Detector.ipynb](Intrusion%20Detector.ipynb), then open the notebook and run cells in order. The dataset is not included in this repository. These commands provide an initial environment; dependency compatibility has not been validated by a fresh execution.

## Evaluation notes

The saved notebook is an exploratory experiment. SMOTE is applied before the train/test split, test features are scaled using their own statistics, and neighbor counts are selected against the test set. These choices limit the reliability of the reported performance.

For a rigorous benchmark, split the original data first, fit scaling and resampling only on training data, select hyperparameters using cross-validation, and evaluate once on an untouched test set. Metric calls should use `y_true, y_pred` in that order; the current notebook reverses them for classification reports and confusion matrices.
