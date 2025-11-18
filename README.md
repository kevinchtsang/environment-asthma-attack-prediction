# Environment-Asthma-Attack-Prediction
This analysis developed asthma attack predictions using only outdoor environmental data (weather, pollen, air quality). More details in the publication [Enhancing Asthma Self-Management with Environmental Passive-Monitoring Data and Machine Learning-Based Predictions](https://doi.org/10.3233/shti240510) - *Medical Informatics Europe 2024*

## AAMOS-00 Study 

We carried out the 2-phase, 7-month AAMOS-00 observational study to collect data about asthma status using three smart-monitoring devices (smart peak flow meter, smart inhaler, smartwatch), and daily symptom questionnaires. Combined with localised weather, pollen, and air-quality reports, we collected a rich longitudinal dataset to explore the feasibility of passive monitoring and asthma attack prediction.

Between June-2021 and June-2022, in the midst of UK’s Covid-19 lockdowns, 22 participants across the UK provided 2,054 unique patient-days of data in phase 2 of the AAMOS-00 Study.


## Data Dictionary

The full data dictionary is available [via the DataShare website](https://datashare.ed.ac.uk/bitstream/handle/10283/4761/aamos00_data_dictionary.xlsx)


## This Repository

Begin by downloading all 12 files from [the DataShare page](https://doi.org/10.7488/ds/3775). 

All the data processing and model training is conducted in `data_processing_model_training.ipynb` notebook, outputs like plots and model performance are saved in the `outputs` folder. Feature importance of models can be explored in `explore_feature_importance.ipynb` notebook.

## Prediction Model

Using a lookback window of 7 days, the XGBoost model is able to predict asthma attacks (defined as 3 days of sustained elevated relief inhaler usage) with the following performance

|                    | Env-sensitive Patients                   | Env-tolerant Patients                   |
| ------------------ | ---------------------------------------- | --------------------------------------- |
| Active monitoring  | AUC = 0.89, 3.1x increase in precision   | AUC = 0.83, 3.7x increase in precision  |
| Passive monitoring | AUC = 0.83, 2.9x increase in precision   | AUC = 0.52, 1.2x increase in precision  |

The novel passive monitoring prediction model for env-sensitive patients achieves comparable performance to models developed on current practice active monitoring data, demonstrating the feasibility of environmental passive-monitoring for asthma attack prediction.

<img src="https://raw.githubusercontent.com/kevinchtsang/environment-asthma-attack-prediction/refs/heads/main/outputs/performance/thresholds_all_aucroc.svg?sanitize=true">



## Licence

Data is licensed under the *Creative Commons Attribution 4.0 International Public License.*

The starter code is licensed under the *MIT License.*