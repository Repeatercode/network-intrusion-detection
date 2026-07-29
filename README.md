Network Intrusion Detection Using Deep Learning

A machine-learning and deep-learning project for detecting malicious network traffic using the UNSW-NB15 dataset. The project includes exploratory data analysis, preprocessing, binary classification, multiclass classification, model optimization, and autoencoder-based anomaly detection.

Project Objectives

Explore and understand the UNSW-NB15 network traffic dataset.

Prepare numerical and categorical network features for machine learning.

Build a baseline binary classifier for normal and attack traffic.

Classify different categories of network attacks.

Improve model performance through optimization.

Explore autoencoder-based anomaly detection.

Save preprocessing objects and model-related outputs for reuse.

Dataset

This project uses the UNSW-NB15 dataset, which contains normal network traffic and several categories of cyberattacks.

The repository includes:

data/
├── UNSW-NB15_features.csv
├── UNSW_NB15_training-set.csv
└── UNSW_NB15_testing-set.csv

Important target columns commonly used in the notebooks are:

label: Binary target where normal and attack traffic are separated.

attack_cat: Multiclass target containing the attack category.

Repository Structure

network-intrusion-detection/
├── data/                         # UNSW-NB15 dataset files
├── figures/                      # Generated graphs and visualizations
├── models/                       # Saved preprocessors and encoders
│   ├── multiclass_label_encoder.joblib
│   └── preprocessor.joblib
├── notebooks/                    # Jupyter notebooks
│   ├── EDA.ipynb
│   ├── Preprocessing.ipynb
│   ├── Binary_Baseline.ipynb
│   ├── Optimization.ipynb
│   ├── Multiclass.ipynb
│   └── Autoencoder.ipynb
├── results/                      # Evaluation results and experiment outputs
├── .gitignore
├── requirements.txt
└── README.md

Notebook Workflow

Run the notebooks in the following order:

EDA.ipynbExamines the dataset structure, missing values, feature distributions, class balance, correlations, and attack categories.

Preprocessing.ipynbCleans the data, transforms categorical features, scales numerical features, and saves reusable preprocessing objects.

Binary_Baseline.ipynbTrains and evaluates a baseline model for binary classification:

Normal traffic vs. Attack traffic

Optimization.ipynbImproves the baseline model through architecture changes, hyperparameter tuning, regularization, or training adjustments.

Multiclass.ipynbTrains a model to identify specific network attack categories.

Autoencoder.ipynbUses reconstruction error to explore anomaly-based intrusion detection.

Technologies Used

Python

NumPy

pandas

Matplotlib

scikit-learn

TensorFlow / Keras

Jupyter Notebook

Joblib

System Requirements

Windows, macOS, or Linux

Python 3.10, 3.11, or 3.12

Git

VS Code with the Python and Jupyter extensions, or Jupyter Notebook

Python 3.14 should not be used for this project because a compatible TensorFlow package may not be available.

Installation

1. Clone the repository

git clone https://github.com/Repeatercode/network-intrusion-detection.git
cd network-intrusion-detection

2. Create a virtual environment

On Windows:

py -3.12 -m venv venv

On macOS or Linux:

python3.12 -m venv venv

3. Activate the virtual environment

On Windows PowerShell:

.\venv\Scripts\Activate.ps1

If PowerShell blocks the activation script:

Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\venv\Scripts\Activate.ps1

On Windows Command Prompt:

venv\Scripts\activate

On macOS or Linux:

source venv/bin/activate

4. Upgrade pip

python -m pip install --upgrade pip

5. Install dependencies

python -m pip install -r requirements.txt

6. Confirm TensorFlow installation

python -c "import tensorflow as tf; print(tf.__version__)"

Running the Project in VS Code

Open the project:

code .

Then:

Install the Python and Jupyter VS Code extensions.

Open notebooks/EDA.ipynb.

Click Select Kernel in the top-right corner.

Select the Python interpreter inside the venv environment.

Run the notebook cells from top to bottom.

Running with Jupyter Notebook

Start Jupyter from the project directory:

jupyter notebook

Open the notebooks directory and begin with:

EDA.ipynb

Optional: Register the Virtual Environment as a Jupyter Kernel

python -m ipykernel install --user --name network-intrusion --display-name "Python 3.12 - Network Intrusion"

Select Python 3.12 - Network Intrusion as the notebook kernel.

Model Evaluation

Depending on the notebook and experiment, models may be evaluated using:

Accuracy

Precision

Recall

F1-score

Confusion matrix

Classification report

Training and validation loss

Training and validation accuracy

Reconstruction error for anomaly detection

For intrusion detection, accuracy alone may be misleading when the classes are imbalanced. Recall, F1-score, per-class performance, and the confusion matrix should also be examined.

Expected Outputs

The project may generate:

Dataset distribution charts

Correlation and feature-analysis figures

Training-history plots

Confusion matrices

Classification reports

Saved preprocessing pipelines

Saved label encoders

Binary and multiclass experiment results

Autoencoder reconstruction-error analysis

Generated files should be stored in the relevant directories:

figures/
models/
results/

Troubleshooting

TensorFlow cannot be installed

Example error:

ERROR: Could not find a version that satisfies the requirement tensorflow
ERROR: No matching distribution found for tensorflow

This commonly occurs when an unsupported Python version is being used.

Check the Python version:

python --version

Create the environment using Python 3.12:

py -3.12 -m venv venv
.\venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt

Notebook uses the wrong Python interpreter

In VS Code:

Select Kernel → Python Environments → venv

You can verify the active notebook interpreter with:

import sys
print(sys.executable)

Module not found

Make sure the virtual environment is active, then run:

python -m pip install -r requirements.txt

Dataset file not found

Run the notebooks from the repository structure without moving them or changing the data directory. If needed, check the dataset path used in the notebook.

Example:

from pathlib import Path

project_root = Path.cwd().parent
data_path = project_root / "data" / "UNSW_NB15_training-set.csv"

Reproducibility

For more consistent experiment results, set random seeds where appropriate:

import random
import numpy as np
import tensorflow as tf

SEED = 42

random.seed(SEED)
np.random.seed(SEED)
tf.random.set_seed(SEED)

Model results can still vary slightly depending on the environment, hardware, TensorFlow version, and training process.

Future Improvements

Compare additional neural-network architectures.

Add systematic hyperparameter tuning.

Address class imbalance using class weights or resampling.

Improve minority attack-category detection.

Add cross-validation where appropriate.

Track experiments and model configurations.

Add explainable-AI methods for feature interpretation.

Build a prediction interface for testing new network records.

Add automated tests and a reproducible training script.

Ethical Use

This project is intended for educational, academic, and defensive cybersecurity research. It should not be used to access, damage, disrupt, or attack systems without authorization.

Author

Repeatercode

GitHub repository:https://github.com/Repeatercode/network-intrusion-detection

License
