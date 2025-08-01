# CanScan
# 🧠 CanScan: Cancer Drug Sensitivity Predictor

CanScan is a deep learning model built using PyTorch that predicts cancer drug **sensitivity scores** based on genomic and clinical features. It helps estimate how effective a drug might be for a given cancer profile.

---

## 🚀 What This Project Does
- ✅ Preprocesses a real-world cancer dataset (TCGA, GDSC, etc.)
- ✅ Encodes biological features (mutation status, tissue type, etc.)
- ✅ Trains a multi-layer neural network to predict drug response
- ✅ Provides test-time prediction using new patient-like data

---

## 📊 Input Features
- Microsatellite instability (MSI)
- Copy Number Alteration (CNA)
- Whole Exome Sequencing
- Tissue Descriptors (1 & 2)
- Other numeric/clinical features

---

## 🎯 Output
- A **sensitivity score** (continuous value) — the higher/lower the score, the more/less sensitive a tumor is predicted to be to a drug

---

## 📦 How to Run

### Train the model:
```bash
python scripts/train.py
```

### Predict from new data:
```python
from scripts.predict import predict_drug_sensitivity

sample_input = {
    'Microsatellite instability Status (MSI)_x': 'MSI-High',
    'CNA': 'High',
    'GDSCTissue descriptor 1': 'Lung',
    'GDSCTissuedescriptor 2': 'NSCLC',
    'Whole Exome Sequencing (WES)': 'Y',
    # Add other required features...
}

prediction = predict_drug_sensitivity(sample_input)
print(f"Predicted Sensitivity Score: {prediction:.4f}")
```

---

## 🛠️ Tech Stack
- Python 3
- PyTorch
- scikit-learn
- pandas / numpy

---

## ✅ Highlights
- Loss dropped from 0.95 → ~0.50 (validation)
- Realistic inference on unseen samples
- Smart preprocessing (encoding, scaling)
- Modular + reproducible pipeline

---

## 🧬 Why This Matters
Accurate sensitivity predictions could help prioritize treatment options and guide drug testing for cancer patients in a non-invasive way.

---
