![Zelestra x AWS ML Ascend Challenge](assets/ffad4794-e212-4717-8db0-4a53a7d24565.jpg)

<img src="Assets/TeamLogo.jpg" alt="Dragon Tech Logo" width="200"/>

# Solar PV Efficiency Prediction

Machine learning models for solar PV efficiency and loss attribution — part of the **Zelestra x AWS ML Ascend Challenge (2nd Edition)**.

---

## 👥 Team

**DRAGON TECH**
- Sartaj Singh Virdi (`svirdi_be23@thapar.edu`)
- Prabhpreet Singh (`psingh9_be23@thapar.edu`) 
- Gurkirat Singh (`gsingh9_be23@thapar.edu`)

---

## ⚠️ Dataset Notice

This project was developed using operational solar power plant data provided **exclusively as part of the Zelestra x AWS ML Ascend Challenge**.

> **The dataset is proprietary and is *not* included in this repository.  
> Redistribution or public sharing of the dataset is not permitted under the competition’s terms of use.**

---

##  Project Goals

- Predict solar PV efficiency and power output accurately.
- Attribute losses to factors like temperature derating, irradiance variability, and tracking accuracy.
- Develop an ensemble model optimized for time-series solar plant data.

---

##  Highlights

- **Time-aware cross-validation** (TimeSeriesSplit)  
- **Solar-specific feature engineering** (e.g. clear sky index, temperature efficiency factor)  
- **XGBoost and ElasticNet ensemble**  
- **Multi-method feature selection with voting**
- **Conservative outlier handling for time-series integrity**

---

##  Results Summary

- **R² Score:** 0.76 (excellent for solar prediction)
- **Correlation:** 0.95 (strong predictive relationship)
- **NRMSE:** 15.5% (low normalized error)
- **MAPE:** High due to near-zero values (common in solar data during low irradiance)

---

##  Contact

For any queries related to this project:

- **Sartaj Singh Virdi** (`svirdi_be23@thapar.edu`)
- **Prabhpreet Singh** (`psingh9_be23@thapar.edu`)
- **Gurkirat Singh** (`gsingh9_be23@thapar.edu`)

---

##  Usage

Example code for loading your *own* dataset (if you have authorized access):

```python
import pandas as pd

# Replace with your dataset path
df = pd.read_csv('your_preprocessed_solar_data.csv')
df['datetime'] = pd.to_datetime(df['datetime'])
df = df.set_index('datetime')

print(df.shape)
print(df.head())
