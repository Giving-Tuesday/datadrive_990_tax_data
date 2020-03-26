# Setup

## Data

To download into repository root:

* `Sample_Program_Service_Data.csv` - [Download from Amazon](https://s3.us-east-2.amazonaws.com/datadive-gates92y-seattle/Project+3+-+Form+990+Data/2+-+Clean+Data/Sample_Program_Service_Data.csv) Sample pre-aggregated financial and text data from Form 990s.

In repository:

* `manula_datakind_labels.csv` - \~345 hand-labeled SDG rows (about ten per SDG)
* `NTEE_EINs_EOBMF.csv` maps between EINs and NTEE taxonomy
* `goals.txt` contains SDGs and their descriptions

## Code

This code requires Python 3 and `pip`. We recommend using virtual environments (via `virtualenv` or `conda`).

1. Run `pip install -r requirements.txt` to get all Python dependencies.

# Analytics

## Notebooks

* `990_analysis.ipynb` - requires missing `nonprofit-descriptions_2016.csv` and `NTEE_EINs.csv`
* `merged_data_models.ipynb` - trains and evaluates a set of NLP models on the sample dataset, to predict SDGs

# Other Notes

## Producing data

Script to produce NTEE EINs from the [IRS EOBMF](https://www.irs.gov/charities-non-profits/exempt-organizations-business-master-file-extract-eo-bmf)
```python
df = pd.read_csv("irs_eobmf.csv")
df = df[["ein", "ntee_cd"]].rename(columns={"ein": "EIN", "ntee_cd": "NTEE"})
df.to_csv("NTEE_EINs_EOBMF.csv", index=False)
```