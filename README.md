# Two-Year ETH Data

This dataset contains **Ethereum (ETH) Open–High–Low–Close–Volume (OHLCV)** data at **5-minute intervals** over a **two-year period**, sourced from Tiingo for research purposes. It spans **730 days** (from `2023-08-14` to `2025-08-13`).

The full dataset is split into:

* **Training/Validation set:** `2023-08-15` to `2024-08-12` (≈1 year)
* **Test set:** `2024-08-12` to `2025-08-12` (≈1 year)

Both sets include precomputed `log_return` and `target_log_return` values.

---

### Loading a Provided Dataset

To load a specific `dataset.csv` file from the provided files:

```python
df = pd.read_csv('dataset.csv', index_col='datetime', parse_dates=True)
```

---

### Calculating Log Returns from the Full Dataset

To compute `log_return` and `target_log_return` from the raw full dataset (`ETH_two_year_data_full.csv`):

```python
df['log_return'] = np.log(two_year_data['close'] / two_year_data['close'].shift(288))  # 288 × 5 min = 1440 min = 1 day
df['target_log_return'] = np.log(two_year_data['close'].shift(-288) / two_year_data['close'])
```

---

**Note:**
Model accuracy should be reported **only** based on its performance across all test datapoints.

