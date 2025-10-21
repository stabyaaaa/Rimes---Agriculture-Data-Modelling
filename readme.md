# 🌾 Agriculture Data Modeling — Internship Project

## 📍 Overview
This project was conducted under the **Regional Integrated Multi-Hazard Early Warning System (RIMES)**.  
The main goal was to build **data-driven models** to support agricultural decision-making in Nepal.  
The internship lasted **8 weeks**, supervised by **Mr. Sanim Raj Shakya**, and focused on early warning and smart resource optimization.

---

## 🎯 Objectives
- Develop an **Early Warning System** for major crops using weather and soil data.  
- Predict **heat stress** and **cold stress** events based on climatic variables.  
- Estimate **disease risk** for Rice Blast, Bacterial Leaf Blight, and Sheath Blight.  
- Recommend **fertilizer doses** using Reinforcement Learning (PPO).  
- Integrate weather, soil, and crop data for real-time, adaptive decision-making.

---

## 🧩 Datasets Used

| Source | Description | Parameters |
|---------|--------------|-------------|
| **ECMWF (Weather)** | Temperature (2m), Precipitation | `T2m_C`, `tp_mm`, `tp_cum`, `tp_avg`, `anomaly_T2m_C` |
| **NARC (Soil)** | Soil property dataset from Nepal | `pH`, `organic_matter`, `N`, `P`, `K`, `boron`, `zinc`, `texture`, `crop` |
| **Temporal Coverage** | 2021–2025 (merged for continuity) | — |

⚠️ *Soil data sampling dates were estimated based on NARC knowledge and data collection timelines.*

---

## ⚙️ Modeling Components

<details>
<summary><b>🌡️ Heat Stress Prediction</b></summary>

- **Target:** Binary label (`heat_proxy`) indicating heat stress conditions.  
- **Models:** Random Forest, Gradient Boosting, Extra Trees.  
- **Evaluation:** 5-Fold Stratified CV with F1-score metric.  
- **Best Model:** Gradient Boosting  
  - CV F1 = 0.9855  
  - Test Accuracy = 0.9913  

</details>

<details>
<summary><b>🌾 Disease Risk Prediction</b></summary>

- **Targets:** Rice Blast, Bacterial Leaf Blight, Sheath Blight.  
- **Models Tested:** Random Forest, XGBoost, LightGBM, Gradient Boosting.  
- **Balancing:** SMOTE used to handle class imbalance.  
- **Best Model:** LightGBM  
  - Accuracies → 0.916 (Blast), 0.918 (BLB), 0.874 (Sheath Blight).  
- **Data Handling:** Scaling within folds to prevent leakage.

</details>

<details>
<summary><b>🧪 Fertilizer Optimization (RL PPO)</b></summary>

- **Algorithm:** Proximal Policy Optimization (PPO).  
- **State:** Soil features (pH, N, P, K, texture) + crop & growth stage.  
- **Action:** Recommended doses for `UREA`, `DAP`, `MOP`.  
- **Reward:** Optimal yield & balanced nutrient efficiency.  
- **Outcome:** RL PPO learned adaptive dosing strategies — stable convergence with minimal overfitting.  

</details>

---

## 📉 Key Findings
- **Temperature** and **cumulative rainfall** strongly influence heat stress.  
- **Rainfall anomalies** and **temperature** drive disease occurrence.  
- **RL PPO** offers superior adaptability compared to regression for dose optimization.  
- Feature engineering (lags, cumulative rainfall) significantly improved performance.  

---

## ⚠️ Limitations
1. **Temporal Uncertainty** – Exact soil data sampling dates unknown (merged 2021–2025).  
2. **Weather Granularity** – ECMWF data may not reflect microclimatic farm variations.  
3. **Disease Coverage** – Only three rice diseases modeled so far.  
4. **Regional Generalization** – Model trained mainly on **Kathmandu Valley** data.  
5. **Humidity Missing** – Could improve **heat** and **disease** models if included.

---

## 🧠 Learnings
- Proper **feature scaling**, **encoding**, and **missing value handling** are vital for stable models.  
- **Cross-validation** and **SMOTE** improve generalization and reduce overfitting.  
- Reinforcement Learning (**PPO**) enables **adaptive, real-time fertilizer optimization**.  
- Integration of soil, crop, and weather data leads to better predictive insights.

---

## 📂 Folder Structure
```bash
RIMES/
│
├── dataset/
│   └── csv_by_year/
│
├── notebook/
│   ├── disease_risk/
│   ├── fert_optimization/
│   ├── heat_cold_stress/
│   └── preprocessing_dataset/
│
├── IMAGES/
│
├── Misc/
│
├── models/
│
└── .gitignore
