# Prediction of Efficiency in Manufacturing

Forecasting production efficiency for a packaging machine, using synthetic data.
A temporal convolutional network (TCN) is compared with an ARIMA baseline on two
efficiency measures, OEE and MME. The approach follows the paper in
`Reference_paper.pdf`.

- **OEE** (Overall Equipment Effectiveness): quality x performance x availability.
- **MME** (Machine Mechanical Efficiency): general running time divided by
  effective running time.

## Contents

| File | Purpose |
| --- | --- |
| `Synthetic_data_final.ipynb` | Generates 547 days of synthetic machine data |
| `Dataset/synthetic_data_final.csv` | The generated dataset |
| `TCN_ARIMA_comparison.ipynb` | Trains both models and compares their errors |
| `Reference_paper.pdf` | The paper the project is based on |

## Setup

Python 3.8 or newer with NumPy, pandas, scikit-learn, matplotlib, TensorFlow,
statsmodels and pmdarima.

```bash
pip install numpy pandas scikit-learn matplotlib tensorflow statsmodels pmdarima
```

## Usage

1. Run `Synthetic_data_final.ipynb` to generate the dataset.
2. Run `TCN_ARIMA_comparison.ipynb` to train the TCN and the ARIMA baseline.
   Errors (RMSE, MAE, MAPE) for MME and OEE are printed for both models.

## Results

On this synthetic data the TCN gives a clearly lower MAPE than the ARIMA
baseline for both measures. The exact figures are in the saved notebook output.
The data is simulated to resemble production conditions; it is not from a real
line, so the numbers show the method works, not how it would perform in a plant.

The TCN is built in Keras as a 1D convolutional network (Conv1D, pooling and
dense layers) with a random 80/20 train-test split. ARIMA uses `auto_arima` to
choose its orders and a rolling one-step forecast over the last 20% of days.

## Known issues

- `TCN_ARIMA_comparison.ipynb` reads `Synthetic_data_with_OEE_MME_16_06_24.csv`,
  which is not in this repository, and expects columns (`Q`, `P`, `A`,
  `Internal_Downtime`) that `Dataset/synthetic_data_final.csv` does not contain.
  The notebook will not run end to end until that input file is restored or the
  columns are rebuilt from the generated data.
- The dataset column `Internal_owntime` is a typo for `Internal_Downtime`.
- The saved outputs in the comparison notebook come from the original run.

## Possible next steps

- Try other architectures (LSTM, transformer-based models).
- Tune hyperparameters.
- Validate against real production data.
