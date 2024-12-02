# Synthea Capstone Project
In this capstone project for the Stony Brook University Data Science Bootcamp program, a predictive model of yearly medical encounter costs was developed. 18 unique healthcare related datasets with information on 5000 synthetic patients were generated from [Synthea](https://github.com/synthetichealth/synthea), a patient population simulator. 

A final dataset for modeling was constructed by combining several types of healthcare records including yearly medical encounter costs, observations/measurements, procedures, medications, and patient demographics. The data was cleaned and exploratory data analysis was performed to discover underlying trends in the data. Additionally, various data imputation techniques were assessed to address missing values.

Once the dataset was ready, the data was split into training and testing sets and numerous machine learning models were developed, including dummy regression, linear regression, ridge regression, lasso regression, random forest, and gradient boosting. The performance of these models were analyzed by comparing R-squared, mean absolute error (MAE), and mean squared error values (MSE). The random forest model was selected as the final model, and its performance was assessed on the entire dataset.

The results of the final random forest model and steps to run locally are listed below.


## Results
Random Forest Model Performance Compared to Dummy Regressor
| Metric | Value | Percent Change from Dummy Regressor |
| ----------- | ----------- | ----------- |
| Training R squared | 0.9475 | 100.00% |
| Testing R squared | 0.6404 | 100.10% |
| Training MAE | 4,236.62 | 615.57% |
| Testing MAE | 6,439.04 | 180.10% |
| Training MSE | 63,764,250.97 | 1642.05% |
| Testing MSE | 410,288,724.39 | 174.13% |   

Random Forest Model Performance on Final Dataset
| Metric | Value |
| ----------- | ----------- |
| R squared | 0.9495 |
| MAE | 2,379.54 |
| MSE | 60,360,773.59 |

Some of the most important features used by this model to predict yearly medical costs include number of doctor's visits, number of medical procedures performed, DALY (disability-adjusted life year, a metric used to measure overall disease burden of a population), BMI (body mass index), pain severity, age, and number/cost of medications.

## How to Run
1. Clone/download zip of repository.
1. Extract `data.7z` into `/data` folder.
1. Ensure the following dependencies are installed from the `requirements.txt` file.
1. Run the following files in order:
   1. [Synthea_data_wrangling.ipynb](source/Synthea_data_wrangling.ipynb)
   1. [Synthea_EDA.ipynb](source/Synthea_EDA.ipynb)
   1. [Synthea_preprocessing_modeling.ipynb](source/Synthea_preprocessing_modeling.ipynb)
1. These files will generate intermediary csv files in the `/data` folder. The final model is pickled and saved to the `/output` folder.
