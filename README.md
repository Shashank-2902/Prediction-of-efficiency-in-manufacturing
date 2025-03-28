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
