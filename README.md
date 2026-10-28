# Predicting Melting Point of Organic Molecules Using Machine Learning

## Overview
This project uses machine learning to predict the melting point of organic molecules from their molecular structure (SMILES notation). Molecular descriptors are generated using RDKit, and three regression models are compared.

## Research Question
Can we predict the melting point of organic molecules from their 2D molecular descriptors?

## Dataset
- **Name:** Jean-Claude Bradley Open Melting Point Dataset (DoublePlusGood)
- **Size:** 3,041 molecules (3,025 after cleaning)
- **Source:** [Figshare](https://figshare.com/articles/dataset/Jean_Claude_Bradley_Open_Melting_Point_Datset/1031637)
- **License:** CC-BY
- **Reference:** Bradley, Jean-Claude; Lang, Andrew; Williams, Antony (2014)

## Molecular Descriptors (RDKit)
| Descriptor | Chemical Meaning |
|-----------|-----------------|
| MolWt | Molecular weight |
| LogP | Lipophilicity (oil vs water preference) |
| TPSA | Topological polar surface area |
| NumHDonors | Hydrogen bond donors |
| NumHAcceptors | Hydrogen bond acceptors |
| NumRotatableBonds | Molecular flexibility |
| NumAromaticRings | Aromatic ring count |
| HeavyAtomCount | Non-hydrogen atom count |

## Results

| Model | R² | RMSE (°C) | MAE (°C) |
|-------|-----|-----------|----------|
| Linear Regression | 0.6477 | 56.88 | 43.87 |
| **Random Forest** | **0.7781** | **45.14** | **34.20** |
| Gradient Boosting | 0.7745 | 45.50 | 34.39 |

**Best Model:** Random Forest (R² = 0.78, MAE = 34.2°C)

## Key Findings
- **TPSA** is the most important predictor (43.8% importance), reflecting the role of polar interactions in crystal packing
- **Molecular weight** (21.5%) and **aromatic ring count** (13.1%) are the next most important features
- Melting point prediction is inherently challenging because it depends on 3D crystal packing, which 2D descriptors cannot fully capture
- Cross-validation confirms the model generalizes well (not overfitting)

## Tools Used
- **Language:** Python
- **Libraries:** pandas, NumPy, Matplotlib, Seaborn, scikit-learn, RDKit
- **Platform:** Kaggle Notebooks

## Links
- **Kaggle Notebook:** [View on Kaggle](https://www.kaggle.com/code/abdurrahim003/predicting-melting-point-using-machine-learning)

## Author
**Abdur Rahim** — B.Sc. in Chemistry, Gono Bishwabidyalay (GSTU), Bangladesh
- Kaggle: [abdurrahim003](https://www.kaggle.com/abdurrahim003)
- GitHub: [abdurrahim003](https://github.com/abdurrahim003)
