Where:
- **NIR** = Near-Infrared reflectance  
- **Red** = Red light reflectance  

NDVI reflects vegetation health. Higher values typically indicate dense, healthy vegetation.

---

## 🗂 Dataset

Each row represents a geolocation over time:

| Column         | Description                                      |
|----------------|--------------------------------------------------|
| `ID`           | Unique identifier for the sample                 |
| `class`        | Ground truth label (target variable)            |
| `YYYYMMDD_N`   | NDVI value on a specific date (27 time points)   |

### Target Classes:
- `Water`
- `Impervious`
- `Farm`
- `Forest`
- `Grass`
- `Orchard`

---

## ⚠ Data Challenges

- **Noise**: Due to cloud cover and crowd-sourced labeling errors.
- **Missing Data**: NDVI values are sometimes missing or distorted.
- **Temporal Variations**: NDVI fluctuates seasonally, requiring feature engineering.

**Note**:  
- Training & public test sets contain **noisy data**.  
- Private test set is **clean**, testing the model's generalization.

---

## 🧠 Approach

### Model
- **Multiclass Logistic Regression** (as per competition rules)

### Preprocessing
- Missing value imputation (e.g., using mean or interpolation)
- Denoising with smoothing techniques (e.g., rolling median)
- Feature extraction from time series (mean, std, min, max, seasonal trends)

---

## 🚀 How to Run

### 1. Install dependencies
```bash
pip install -r requirements.txt
