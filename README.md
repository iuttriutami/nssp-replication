# Replication package — "Selecting Spatial Connectivity Structures for Spatial Econometric Analysis: A Reproducible Workflow"

Network Structure Selection Protocol (NSSP) applied to poverty in the 35 regencies/cities of Central Java, Indonesia, 2020–2024.

## Contents

| Folder | Content |
|---|---|
| `data/` | Panel 2020–2024 (`jateng_panel_2020_2024_full.csv`), 2019 pre-sample profile, boundary file — see `data/README_data.md` |
| `weights/` | Row-standardised weight matrices used in the paper (`W_queen.csv`, `W_knn4.csv`, `W_econ.csv`), indexed by BPS regency code 3301–3376 |
| `notebooks/nssp_main_tables_kaggle.ipynb` | Tables 1–8 and S1–S33 (see `TABLE_MAP.md`), with automatic checks |
| `notebooks/nssp_precise_tables_kaggle.ipynb` | High-precision versions of the simulation-based tables (Tables 3, 6, 7, 8, S11–S13, S27–S29) with Monte Carlo errors |
| `notebooks/nssp_addon8_kaggle.ipynb` | Moran's I, Getis–Ord, LISA and Fig. 2; Tables S5, S18b, S25, S30–S32 |
| `notebooks/nssp_addon6_kaggle.ipynb` | Iterated bias correction of the dynamic SDM, its Monte Carlo, Durbin-test power curve (Tables S24b, S35, S36) |
| `notebooks/nssp_addon7_kaggle.ipynb` | Monte Carlo of dynamic estimators incl. Bayesian FE sampler (Table S34) |
| `results/` | CSV output of every script, as used in the paper |

## How to reproduce

1. Python 3.13 with the packages in `requirements.txt` (`pip install -r requirements.txt`).
2. Put the data files in `data/` (or attach them as a Kaggle dataset).
3. Run `nssp_main_tables_kaggle.ipynb`, `nssp_precise_tables_kaggle.ipynb`, then the three addon notebooks. On Kaggle, import a notebook, add the data as input and choose *Save & Run All*; the notebooks locate the data and weight matrices automatically. Each notebook has `QUICK = True` for a one-minute check run.
4. Compare the output with `results/`. Fixed seeds are set in every script (notebooks: `SEED = 20260101`).

Run times on a 4-core Kaggle CPU: addon 6 ≈ 15 min, addon 7 ≈ 20 min.

## Validation checks printed by the notebooks

* Uncorrected QML τ under queen contiguity: 0.327 (unit FE), 0.394 (two-way FE) — Table S27.
* Bayesian fixed-effects τ under queen contiguity: 0.380 and 0.405 (Table S30: 0.377 and 0.407).

## Notes

* `results/addon6`: rows for the single-step correction contain point estimates only. Their interval columns were produced by an earlier version of the notebook that centred the basic bootstrap interval incorrectly and are left blank; the notebook in this package contains the corrected code. Iterated-correction results are unaffected. Single-step intervals and coverage in the paper come from `results/addon7` (Table S34).
* `results/addon5`: PSIS-LOO with exact refits, WAIC, model weights and model-averaged impacts (Tables 3, 6, S11–S13).

## Software

Python 3.13, NumPy 2.1.3, SciPy 1.16.3, pandas 2.3.3, joblib (see `requirements.txt`).

## Licence

Code: MIT. Derived data and weight matrices: CC BY 4.0. Source statistics: BPS-Statistics of Jawa Tengah Province; boundaries: Badan Informasi Geospasial (BIG).
