RIMES/
├── dataset/                         # Contains raw and processed datasets
│
├── IMAGES/                          # For storing project-related images or plots
│
├── Misc/                            # Miscellaneous files or temporary work
│
├── models/                          # Saved model files and checkpoints
│
├── notebook/                        # All analysis and training notebooks
│   ├── csv_by_year/                 # Year-wise CSV data
│   │
│   ├── disease_risk/                # Disease risk prediction models
│   │   ├── cv_main.ipynb
│   │   ├── disease_risk_rf_main.ipynb
│   │   ├── rf_main.ipynb
│   │   ├── rf_overfit.ipynb
│   │   └── disease_risk_rf_main copy.ipynb
│   │
│   ├── fert_optimization/           # Fertilizer optimization models (RL PPO)
│   │   ├── check_dataset.ipynb
│   │   ├── rl_ppo_main.ipynb
│   │   ├── rl_ppo copy.ipynb
│   │   ├── modelling_fail.ipynb
│   │   ├── fertilizer_model.pth
│   │
│   ├── heat_cold_stress/            # Temperature stress prediction models
│   │   ├── heatforecasting.ipynb
│   │   ├── heatstress_prediction.ipynb
│   │   ├── modelling_heatstress_cv.ipynb
│   │
│   └── preprocessing_dataset/       # Data preprocessing and feature engineering
│       ├── dataset_precipitation.ipynb
│       ├── dataset_t2m.ipynb
│       ├── merge_narc_cdf.ipynb
│       ├── merge_t2m_tp_preprocessing.ipynb
│       ├── pre_processing_EDA_ktm_t2m.ipynb
│       ├── pre_processing_EDA_ktm_tp.ipynb
│       └── heatstress_prediction_another_method.ipynb
│
└── .gitignore                       # Git ignore file to exclude unnecessary files
