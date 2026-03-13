# BACE1-Inhibitor-ML-Screening.
Predicting BACE1 inhibition for Alzheimer's Research using ECFP fingerprints and DeepChem

## **Project Overview**
This repository contains a machine learning pipeline for the identification of Beta-secretase 1 (BACE1) inhibitors, a primary therapeutic target for Alzheimer's Disease. The project evaluates the efficacy of Multi-Layer Perceptrons (MLP) compared to Logistic Regression baselines using the MoleculeNet BACE benchmark.

A key focus of this implementation is the use of Bemis-Murcko Scaffold Splitting to assess model generalizability across chemically distinct molecular families, providing a more rigorous validation than standard random partitioning.

## **Technical Stack**
* **DeepChem:** Orchestration of the molecule-to-model pipeline.
* **RDKit:** Chemical engine used for calculating physicochemical descriptors (LogP, MW).
* **Scikit-Learn:** Baseline modeling and performance metrics.
* **Matplotlib/Seaborn:** Exploratory data analysis (PCA) and result visualization.

## **Key Features**
* **Hybrid Featurization:** Combines 1,024-bit ECFP4 (Morgan) fingerprints with global RDKit descriptors.
* **Dimensionality Reduction:** Employs Principal Component Analysis (PCA) to visualize the chemical space overlap between active and inactive ligands.
* **Rigorous Validation:** Implements scaffold-based splitting to prevent data leakage and simulate real-world drug discovery scenarios.

## **Performance Summary**
| Model | ROC-AUC | Precision |
| :--- | :--- | :--- |
| **Logistic Regression** | 0.81 | 76.5% |
| **Neural Network (MLP)** | **0.83** | **79.3%** |

The model successfully identifies inhibitors with high precision, maintaining a strong predictive signal even when encountering novel chemical scaffolds.

## **Installation & Usage**
To run this notebook, ensure you have a Python 3.8+ environment. The core dependencies can be installed via:

```bash
pip install --pre deepchem
pip install rdkit-pypi
