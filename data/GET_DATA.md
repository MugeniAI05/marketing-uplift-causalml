# Get the Criteo Uplift Dataset (locally)

> ⚠️ The CSV is ~3.25GB. Do **not** commit it to Git.

## Option A: Kaggle CLI
1. Install the Kaggle API and place your API token at `~/.kaggle/kaggle.json`.
2. Run:
```bash
kaggle datasets download -d mobius/uplift-modeling-marketing-campaign-data -p data/ --unzip
```
This will create `data/criteo-uplift-v2.1.csv`.

### Option B: Manual download

Download the dataset directly from Kaggle and move the CSV into `data/`:

🔗 [Criteo Uplift Modeling, Marketing Campaign Data](https://www.kaggle.com/datasets/mobius/uplift-modeling-marketing-campaign-data)

## Tip
Work with a stratified sample for development to speed up iteration, then scale.
