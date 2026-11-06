Project Overview

This project uses the UNSW-NB15 network traffic dataset to classify traffic as normal or as an attack. It is a network intrusion classification project; the `proto` column describes the connection protocol (such as TCP or UDP), while `label` is the normal/attack target in the training dataset.

## Dataset Download

- **Kaggle dataset:** [UNSW-NB15 by dhoogla](https://www.kaggle.com/datasets/dhoogla/unswnb15?resource=download)
- **Direct CSV alternative:** [Download UNSW_NB15_training-set.csv](https://huggingface.co/datasets/Mouwiya/UNSW-NB15-small/resolve/main/UNSW_NB15_training-set.csv)

For Kaggle, sign in, open the dataset page, and select **Download**. Kaggle may download a ZIP or provide Parquet files. Extract the ZIP if needed. The direct CSV link downloads the training CSV file.

## Goal

Use network traffic features to predict whether a record is normal or an attack.

## Main Columns

Column names vary slightly between dataset versions. Common UNSW-NB15 columns include:

- `proto`: connection protocol
- `dur`: connection duration
- `service`: network service
- `state`: connection state
- `spkts`, `dpkts`: source and destination packet counts
- `sbytes`, `dbytes`: source and destination byte counts
- `label`: binary target (0 = normal, 1 = attack), when included
- `attack_cat`: attack category, when included

Check the downloaded file's actual columns before using them in code.

## Project Steps

1. Download and load the dataset.
2. Inspect the rows, columns, and data types.
3. Handle missing values.
4. Remove duplicate rows.
5. Create graphs to explore the data.
6. Prepare features and the target label.
7. Train classification models.
8. Compare model performance.
9. Review a classification report and confusion matrix.
10. Make a prediction for a new network record.

## Tools

- Python and Google Colab
- pandas
- matplotlib and seaborn
- scikit-learn

## Loading the Direct CSV in Google Colab

Upload the downloaded CSV file to Colab, then run:

```python
import pandas as pd
from google.colab import files

uploaded = files.upload()
filename = next(iter(uploaded))
df = pd.read_csv(filename)

print(df.shape)
print(df.columns.tolist())
df.head()
```

If the downloaded Kaggle file is Parquet instead of CSV, use `pd.read_parquet("your_file.parquet")` instead of `pd.read_csv(...)`.

## Files

- `README.md` — project description and dataset instructions
- `*.ipynb` — Google Colab notebook

## Dataset Citation

UNSW-NB15 was created by Nour Moustafa and Jill Slay. See the [official UNSW-NB15 project page](https://research.unsw.edu.au/projects/unsw-nb15-dataset) for dataset information and citation details.
