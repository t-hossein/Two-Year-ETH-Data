# Two-Year-ETH-Data
A two-year ETH Open-High-Low-Close-Volume (OHLCV) dataset, fetched from Tiingo, for research purposes. This dataset spans 728 days (~ 2 years), from 2023-08-15 to 2025-08-12. The full dataset is split into training/validation (2023-08-15 to 2024-08-12) and test (2024-08-12 to 2025-08-12) sets, each covering approximately one year of data. The reported values for the accuracy of your model should be solely based on its performance on all the test datapoints.

To load the desired ```'dataset.csv'``` file among provided files, use

```
df = pd.read_csv('dataset.csv', index_col='datetime', parse_dates=True)
```


