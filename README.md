# 🔬 Thin Film Hardness Prediction using Artificial Neural Networks

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-latest-orange.svg)](https://scikit-learn.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

**Author:** Veena Sahu (@Veena Sahu)

---

## Overview

This project predicts the **Vickers Hardness (VHN)** of thin film multi-principal element alloys (MPEAs) using an **Artificial Neural Network (ANN)**. The model is trained on a curated dataset of **218 alloys** with physically meaningful features derived from alloy composition and thermodynamic properties, and evaluated using **5-fold cross-validation**.

## Features Used

| Feature | Description |
|---------|-------------|
| `R_cov_delta` | Covalent radius mismatch |
| `G_delta` | Shear modulus mismatch |
| `VEC` | Valence electron concentration |
| `E_delta` | Young's modulus mismatch |
| `H_chem` | Chemical enthalpy |
| `H_el` | Elastic strain energy |

## Project Structure

```
├── Thin_Film_Hardness_Prediction.ipynb   # Complete pipeline (single notebook)
├── db_HEAs.csv                           # Dataset (218 alloys)
├── README.md                             # This file
└── LICENSE                               # MIT License
```

## Notebook Contents

The notebook contains a complete, end-to-end ML pipeline:

1. **Imports & Configuration** — all dependencies and model hyperparameters
2. **Data Loading & Exploration** — dataset overview, statistics, correlation heatmap, feature-target scatter plots, phase distributions
3. **Data Preparation** — feature extraction, shuffling, train/test split
4. **ANN Model Definition** — multi-layer perceptron (20 → 15 → 10 → 1 units)
5. **K-Fold Cross-Validation Training** — 5-fold CV with multiple restarts for best model selection
6. **Results & Visualization** — loss curves, actual vs predicted scatter, error distributions, per-fold performance bar charts, summary table
7. **Conclusion** — summary of results

## Requirements

| Package | Version |
|---------|---------|
| Python | ≥ 3.8 |
| scikit-learn | ≥ 0.22 |
| pandas | ≥ 1.0 |
| NumPy | ≥ 1.18 |
| matplotlib | ≥ 3.0 |
| seaborn | ≥ 0.10 |

### Install dependencies

```bash
pip install scikit-learn pandas numpy matplotlib seaborn
```

## How to Run

1. Clone or download this repository
2. Install the required packages (see above)
3. Open and run the notebook:

```bash
jupyter notebook Thin_Film_Hardness_Prediction.ipynb
```

4. Results (predictions, performance logs) will be saved to the `ThinFilm_Hardness_ANN/` directory

## Model Architecture

```
Input (6 features)
  → Dense(20, relu)
  → Dense(15, relu)
  → Dense(10, relu)
  → Output (1 unit: Hardness)
```

- **Optimizer:** Adam (lr = 0.02)
- **Validation:** 5-fold cross-validation with multiple restarts per fold
- **Feature scaling:** StandardScaler applied per fold

## Dataset

The dataset (`db_HEAs.csv`) contains **218 multi-principal element alloys** with:
- Alloy composition and name
- Phase information (FCC, BCC, etc.)
- Vickers Hardness Number (VHN) — target variable
- Normalized physical/thermodynamic features

## License

This project is licensed under the MIT License — see [LICENSE](LICENSE) for details.

---

**Veena Sahu** | Thin Film Hardness Prediction Project
