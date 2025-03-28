# Prediction of Efficiency in Manufacturing

## **Deep Learning-based Production Forecasting in Manufacturing: A Packaging Equipment Case Study**

### **Overview**
This repository contains the implementation of a deep learning-based production forecasting model for manufacturing. The case study focuses on packaging equipment, leveraging synthetic data to evaluate forecasting performance.

Two models were used for comparison:

- **Temporal Convolutional Network (TCN)** – The primary deep learning model.
- **AutoRegressive Integrated Moving Average (ARIMA)** – Used as a baseline model.

Key performance metrics, **Overall Equipment Effectiveness (OEE)** and **Mean Model Error (MME)**, were computed using Python to assess the model's forecasting accuracy.

---
## **Contents**

📄 **Reference Paper**  
- `Reference_paper.pdf` - The research paper used as the basis for this study.

📊 **Synthetic Data Generation**  
- `Sythetic_data_final.ipynb` - Jupyter Notebook for generating synthetic data.

📈 **Model Comparison**  
- `TCN_ARIMA_comparision.ipynb` - Notebook implementing and comparing TCN and ARIMA models.

---
## **Installation & Dependencies**

To run the notebooks, install the required dependencies:

```bash
pip install -r requirements.txt
```

(Ensure you have **Python 3.8+** installed)

---
## **Usage**

1️⃣ **Run Synthetic Data Generation Notebook**  
- Generates the required dataset for model training and evaluation.

2️⃣ **Execute Model Comparison Notebook**  
- Trains and evaluates **TCN** and **ARIMA** models on the generated dataset.

3️⃣ **Analyze Results**  
- Review **OEE** and **MME** calculations to compare forecasting performance.

---
## **Results & Findings**

✔️ **TCN outperformed ARIMA** in predictive accuracy across key evaluation metrics.  
✔️ **OEE and MME calculations** confirmed the superior performance of the deep learning model.  
✔️ The **synthetic dataset** effectively simulated real-world production scenarios.

---
## **Future Improvements**

🚀 **Experiment with additional deep learning models** (e.g., LSTM, Transformer-based models).  
🔍 **Optimize hyperparameters** to enhance forecasting accuracy.  
📊 **Extend dataset with real-world production data** to validate findings.

---
## **Author**

👤 **Shashank Sakhala**  
📧 shashankssakhala@gmail.com
