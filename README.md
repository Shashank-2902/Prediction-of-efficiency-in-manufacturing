# Prediction of Efficiency in Manufacturing

## Overview

This repository contains a deep learning based production forecasting model for manufacturing, built around a packaging equipment case study using synthetic data.

Two models are compared:

- **Temporal Convolutional Network (TCN)** — the primary model
- **ARIMA (AutoRegressive Integrated Moving Average)** — used as the baseline

Forecasting accuracy is evaluated using two metrics: **OEE** (Overall Equipment Effectiveness) and **MME**.

## Contents

- `Reference_paper.pdf` — the paper this project is based on
- `Synthetic_data_final.ipynb` — generates the synthetic dataset used for training and evaluation
- `TCN_ARIMA_comparison.ipynb` — trains and compares the TCN and ARIMA models

## Dependencies

- Python 3.8+
- NumPy
- Pandas
- scikit-learn
- TensorFlow
- statsmodels (for ARIMA)
- pmdarima

## Usage

1. Run the synthetic data notebook to generate the dataset.
2. Run the model comparison notebook to train and evaluate both models.
3. Compare the OEE and MME results printed at the end of the notebook.

## Results

The TCN model reduced MAPE substantially compared to the ARIMA baseline on both metrics. Exact figures are printed in the notebook output. The dataset is synthetic, built to simulate realistic production conditions, not collected from a live production line.

## Possible next steps

- Try additional architectures (LSTM, transformer based models)
- Tune hyperparameters further
- Validate against real production data if it becomes available
