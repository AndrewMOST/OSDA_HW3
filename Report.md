# OSDA Big HW report

## Datasets used
### Rain in Australia
https://www.kaggle.com/datasets/jsphyg/weather-dataset-rattle-package?rvi=1

The target is to predict whether rain would fall over a selected areaa, based on the data from the previous day and historical observations.
The dataset contains over 145000 rows and 23 columns, including numerical and categorical data.
For the purpose of speeding up calculations, both in classical model analysis and FCA, the data was truncated, and no more than 10000 rows were used.
In classical model analysis, categorical data was left in and encoded with OneHot encoding, whereas for FCA the categorical columns were dropped, leaving only numerical data.

### Smoking and drinking
https://www.kaggle.com/datasets/sooyoungher/smoking-drinking-dataset?rvi=1

The objective is to predict whether a person is a smoker, or is a drinker, with the other respective column being a feature, along with 21 numerical and categorical columns.
Different from the Rain dataset, categorical features (apart from the sex) describe numerical data, just split into discrete container categories. The dataset includes almost a million rows,
however, like with the Rain dataset, the data was sampled. For the purposes of the models used, this much data is redundant, and again, no more than 10000 rows were left for analysis.

### Motorcycle habits
https://www.kaggle.com/competitions/motorcyclehabitprediction

This dataset was created by a person I know, and submitted to Kaggle as part of a competition. The competition has since finished, but the results achieved in classical model analysis are comparable to the submissions on Kaggle.
The objective is to predict whether a person would choose to ride a motodcycle, based mainly on the weather data for that day. The data spans one year, with 256 rows combining into the train set, and 109 into the test set respectively.
The data contains only numerical columns, so all of them were left in for both analyses.

## Data preparation and models
For preparation and classifying with classical models, the code was provided in HW2. The report is linked here:

https://github.com/AndrewMOST/OSDA_HW3/blob/main/OSDA%20HW2.pdf

For FCA, see this file:

https://github.com/AndrewMOST/OSDA_HW3/blob/main/OSDA_HW3.ipynb

## Results
### Classical models
The results of analysis by classical models suggests that all of the datasets are sufficient enough for classification, judged by the accuracy and f1-scores which are quite close to the submissions on Kaggle.
The models used sometimes resulted in scores significantly different from each other, although gridsearch was used for all of them on all datasets to find optimal parameters.
Moreover, the scores difference is inconsistent between datasets, which suggests that different models can perform better or worse compared to their adversaries on different data.
However, some trends remain consistent, as the boosting models provide the best results across the board, which makes sense, considering how popular they are for analysing tabular data.

![image](https://github.com/AndrewMOST/OSDA_HW3/assets/43444023/36b5965a-8256-4a54-acb3-e857d8ae41ea)

### FCA
The FCA models performed reeeeeally badly, not getting far off from random predictions.
Moreover, the code provided in the repository seems to contain mistakes, evident from the accuracy being 0 with non-zero alpha values (or, more accurately, with values of alpha >= 1).
Although cross-validation was used, the FCA algorithm still turned out to be quite specific and cannot be reliably used to make predictions on sensitive data.

Results for Rain in Australia:

![image](https://github.com/AndrewMOST/OSDA_HW3/assets/43444023/7aa51e7b-ea34-4776-b732-042bc72e9600)

Results for Motorcycle habits:

![image](https://github.com/AndrewMOST/OSDA_HW3/assets/43444023/d62b4d55-2e5b-4eaf-aac5-b40d3d08f7d0)

Results for Smoking And Drinking:

![image](https://github.com/AndrewMOST/OSDA_HW3/assets/43444023/4bf6f853-f4d4-4260-ad5e-cab52bc34c85)
