# Co-Crystal Formation Prediction

Stacking-based solution for a co-crystal formation prediction hackathon. The repository combines molecular feature engineering, Optuna tuning, graph neural network experiments, and final submission generation.

## What is inside

- Molecular descriptors and fingerprints for two-input chemistry data
- XGBoost, CatBoost, LightGBM, MLP, and GNN experiments
- 3-fold / 5-fold validation and stacking ensemble logic
- Threshold search for the custom hackathon metric
- Baseline notebook for reference

## Core idea

The best notebook builds a wide feature space from SMILES inputs and then blends several model families:

1. Generate molecular features for both compounds
2. Combine them with pairwise transforms such as concat, diff, prod, sum, min, and max
3. Tune tree models with Optuna
4. Train a stacking ensemble with a meta-model
5. Optimize the decision threshold for the final hackathon score

## Files

- `best_solution.ipynb` - main stacked solution
- `cocrystal-challenge-baseline.ipynb` - baseline and reference experiments
- `train.csv` - training data
- `test.csv` - test data

## Tech stack

- Python
- NumPy, Pandas
- scikit-learn
- XGBoost
- CatBoost
- LightGBM
- Optuna
- RDKit
- PyTorch Geometric

## Results

Notebook outputs show:

- Best score: `0.98196`
- Final AUC: `0.98970`

These are local notebook results captured during experimentation.

## How to use

Open the notebooks in Jupyter or VS Code and run the pipeline from `best_solution.ipynb`. If you need a fresh environment, install the typical dependencies used in the notebooks:

```bash
pip install numpy pandas scikit-learn xgboost catboost lightgbm optuna rdkit-pypi torch torch-geometric
```

## Repository structure

```text
hackathon-2/
├── README.md
├── best_solution.ipynb
├── cocrystal-challenge-baseline.ipynb
├── train.csv
└── test.csv
```

## Notes

- The repository is intentionally notebook-driven and keeps both the final solution and baseline work.
- The main notebook emphasizes ensemble performance rather than a single-model approach.
- If you publish this publicly, this README is already framed for GitHub portfolio presentation.