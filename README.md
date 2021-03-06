# ASHRAE - Great Energy Predictor III - Top 5 winning solutions

This repository is for analysing all solutions, both winning and other public kernals, and summarizing their characteristics -- ML workflow, score comparison across different sites, building types, meter types, etc.

# Links
1. [Top 5 winning solutions - code and docs (submitted to Kaggle)](https://www.dropbox.com/sh/73iryui7t0w74ik/AAAY-yF87A2zrLdqHv11vFlsa?dl=0)
2. [Top 5 winning solutions - explainer videos](https://www.dropbox.com/sh/tmnhkmy33vs3uya/AACVU-CcwyqGwApEvhNmSH4Qa?dl=0)

### First rank solution
 - [Code](../blob/master/solutions/rank-1/)
 - [Solution summary document (.docx)]()
 - [Solution summary presentation (.pdf)]()
 - [Sulution summay in Kaggle discussion board](https://www.kaggle.com/c/ashrae-energy-prediction/discussion/124709)
 - [Solution explainer video]()
 
### Second rank solution
 - [Code](../blob/master/solutions/rank-2/)
 - [Solution summary document (.pdf)](../blob/master/solutions/rank-2/ASHRAE%20-%20Great%20Energy%20Predictor%20III%20solution.pdf)
 - [Solution summary presentation (.pdf)]()
 - [Sulution summay in Kaggle discussion board](https://www.kaggle.com/c/ashrae-energy-prediction/discussion/123481)
 - [Solution explainer video]()
 
### Third rank solution
 - [Code](../blob/master/solutions/rank-3/)
 - [Solution summary document (.pdf)](../blob/master/solutions/rank-3/model_summary.pdf)
 - [Sulution summay in Kaggle discussion board](https://www.kaggle.com/c/ashrae-energy-prediction/discussion/124984)
 - [Solution explainer video]()
 
### Fourth rank solution
 - [Code](../blob/master/solutions/rank-4/)
 - [Solution summary document (.pdf)](../blob/master/solutions/rank-4/MODEL%20SUMMARY.docx)
 - [Sulution summay in Kaggle discussion board](https://www.kaggle.com/c/ashrae-energy-prediction/discussion/124788)
 - [Solution explainer video]()

### Fifth rank solution
 - [Code](../blob/master/solutions/rank-5/)
 - [Solution summary document (.docx)](../blob/master/solutions/rank-5/ModelSummary.docx)
 - [Solution summary presentation (.pdf)](../blob/master/solutions/rank-5/ASHRAE_fifth_place_solution.pdf)
 - [Sulution summay in Kaggle discussion board](https://www.kaggle.com/c/ashrae-energy-prediction/discussion/127086)
 - [Solution explainer video]()

## Comparison
|    |   Final Rank | Team Name             |   Final Private Leaderboard Score | Preprocessing Strategy                                                     | Features Strategy Overview                                                                                                           | Modeling Strategy Overview                                                                                          | Post-Processing strategy                                               |
|---:|-------------:|:----------------------|----------------------------------:|:---------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------|
|  0 |            1 | Isamu & Matt          |                             1.231 | Removed anomalies in meter data and imputed missing values in weather data | 28 features, Extensively focused on feature engineering and selected                                                                 | LightGBM, CatBoost, and MLP models trained on different subsets of the training and public data                     | Ensembled the model predictions using weighted generalized mean.       |
|  1 |            2 | cHa0s                 |                             1.232 | Visual analytics and manual inspection                                     | Raw energy meter data, temporal features,  building metadata, simple statistical features of weather data.                           | XGBoost, LightGBM, Catboost, and Feed-forward Neural Network models trained on different subset of the training set | Weighted mean. (different weights were used for different meter types) |
|  2 |            3 | eagle4                |                             1.234 | Eliminated 0s in the same period in the same site                          | nan                                                                                                                                  | Keras CNN, LightGBM and Catboost                                                                                    | nan                                                                    |
|  3 |            4 | 不用leakage上分太难了 |                             1.235 | Not available                                                              | 23 features including raw data, aggregate, weather lag features, and target encoding. Features are selected using sub-training sets. | XGBoost (2-fold, 5-fold) and Light GBM (3-fold)                                                                     | Ensembled three models. Weights were determined using the leaked data. |
|  4 |            5 | mma                   |                             1.237 | Dropped long streaks of constant values and zero target values.            | Target encoding using percentile and proportion and used the weather data temporal features                                          | LightGBM in two steps -- identify model parameters on a subset and then train on the whole set for each building.   | Weighted average.                                                      |
