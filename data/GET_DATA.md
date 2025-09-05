# Get the Criteo Uplift Dataset (locally)

> ⚠️ The CSV is ~3.25GB. Do **not** commit it to Git.

## Option A: Kaggle CLI
1. Install the Kaggle API and place your API token at `~/.kaggle/kaggle.json`.
2. Run:
```bash
kaggle datasets download -d mobius/uplift-modeling-marketing-campaign-data -p data/ --unzip
```
This will create `data/criteo-uplift-v2.1.csv`.

## Option B: Manual download
Download from the dataset page and move the CSV into `data/`.

## Tip
Work with a stratified sample for development to speed up iteration, then scale.