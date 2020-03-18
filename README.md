

# Installation

## Tableau

1. Download [Tableau Desktop](https://www.tableau.com/products/desktop/download)

## PowerBI

### OSX

1. Get [Virtualbox](https://www.virtualbox.org/wiki/Downloads)
2. [Download a virtualbox windows virtual machine](https://developer.microsoft.com/en-us/microsoft-edge/tools/vms/)
3. Open your Windows virtual machine
4. Within your Windows virtual machine, connect to https://www.microsoft.com/en-us/download/details.aspx?id=58494

## Data

* `manula_datakind_labels.csv` - \~345 hand-labeled SDG rows (about ten per SDG)
* `manula_datakind_labels.csv` contains \~350 labeled SDG examples
* `nonprofit-descriptions_2016.csv` contains thousands of examples with EINs
* `NTEE_EINs.csv` maps between `nonprofit-descriptions_2016.csv` EINs and NTEE taxonomy
* `goals.txt` contains SDGs and their descriptions


## Notebooks

### Good

* `labeled_set_model.ipynb` - trains and evaluates a set of NLP models on the sample dataset, `manula_datakind_labels.csv`

### Needs work

* `990_kmeans.ipynb` - requires missing `nonprofit-descriptions_2016.csv` and `NTEE_EINs.csv`
* `merged_data_models` - well-documented notebook, but requires missing `NTEE_EINs.csv` and `nonprofit-descriptions_2016.csv`
