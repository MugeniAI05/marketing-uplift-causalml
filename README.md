# Causal Uplift Modeling for Smarter Marketing Campaigns (Criteo)

**One-liner:** Estimate who is *persuaded* by ads (not just who converts), and build a budget-aware targeting policy that maximizes **incremental conversions/ROAS** using [CausalML](https://github.com/uber/causalml).

## Why this matters
Traditional models rank users by likelihood to convert. Advertisers need **incremental** impact—treat **persuadables**, not sure-things or lost-causes. This repo shows how uplift modeling + policy simulation saves spend and lifts ROI.

## Dataset
- **Criteo Uplift Modeling** benchmark (13M users, RCT): features `f0..f11`, `treatment`, `visit`, `conversion`, `exposure`.
- Due to size, data is **not checked into Git**. See `data/GET_DATA.md` to download.

## Methods
- Experiment validity: randomization checks, imbalance handling (85/15), ITT vs CACE using `exposure`.
- ATE: Diff-in-means, IPW/DR.
- CATE/Uplift: S/T/X/R meta-learners (XGBoost, LR, MLP), uplift trees.
- Policy optimization: budget/CPA guardrails, Counterfactual Value Estimator; Qini/AUUC, uplift@k.

## Repo layout
```
notebooks/
  01_eda_validity.ipynb
  02_ate_baselines.ipynb
  03_uplift_models.ipynb
  04_policy_simulation.ipynb
  05_explainability.ipynb
src/
  data_loader.py
  evaluation.py
  uplift_models.py
  policy_optimizer.py
reports/
  figures/           # charts (not versioned)
data/
  GET_DATA.md        # how to fetch dataset locally
```

## Quickstart
```bash
# create and activate a virtual env if you like
pip install -r requirements.txt

# open the notebooks in order (1→5)
jupyter notebook
```

## Results (to fill after running)
- AUUC / Qini by model
- Uplift@k and incremental conversions under budget
- ROI comparison: random vs propensity vs uplift policy

## Business takeaway
> Reallocating spend to **high-uplift cohorts** improves incremental ROAS at fixed budget. This repo ships a **decision policy**, not just a model.