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
| `Synthetic_data_generation.ipynb` | Generates 547 days of synthetic machine data with OEE and MME |
| `Dataset/Synthetic_data_with_OEE_MME_16_06_24.csv` | The generated dataset |
| `TCN_ARIMA_comparison.ipynb` | Trains both models and compares their errors |
| `Reference_paper.pdf` | The paper the project is based on |

## Setup

Python 3.9 or newer.

```bash
pip install -r requirements.txt
```

## Usage

1. Optional: run `Synthetic_data_generation.ipynb` to regenerate the dataset. It
   produces the same file as the one in `Dataset/`, because the random seed is fixed.
2. Run `TCN_ARIMA_comparison.ipynb`. It trains the TCN and the ARIMA baseline and
   prints RMSE, MAE and MAPE for MME and OEE. A full run takes about a minute on
   a laptop CPU.

## Results

MAPE on the held-out data:

| Measure | TCN | ARIMA |
| --- | --- | --- |
| MME | about 0.5% | 16.6% |
| OEE | about 0.9% | 9.7% |

The TCN error is far lower than the ARIMA error for both measures. The TCN
figures change slightly from run to run because its training is not seeded; the
ARIMA figures are identical every time. The saved notebook outputs come from the
original run.

The data is simulated to resemble production conditions. It is not from a real
line, so the numbers show that the method works, not how it would perform in a
plant.

## How the models are set up

- **TCN:** built in Keras as a 1D convolutional network (Conv1D, pooling and
  dense layers) on the nine machine variables, with a random 80/20 train-test
  split.
- **ARIMA:** orders are chosen with `auto_arima`; forecasts are one step ahead
  over the last 20% of days, refitting after each new observation.

## Possible next steps

- Try other architectures (LSTM, transformer-based models).
- Tune hyperparameters.
- Validate against real production data.
