## Overview:
Alphabet Soup, a philanthropic institution renowned for its backing of more than 34,000 ventures in previous years, has turned to advanced deep learning methodologies and neural networks to gauge the potential viability of applicants seeking financial support.

## Results: 
- Data Processing:
  The dataset underwent an initial preprocessing phase aimed at removing irrelevant information, which involved eliminating the EIN and NAME columns from the model. Following this step, the remaining columns were earmarked as features for the model, while the NAME column was later reintroduced during testing. To address considerable variability, both the CLASSIFICATION and APPLICATION_TYPE columns were amalgamated into a broader category labeled 'Other'. Subsequently, the dataset was partitioned into distinct training and testing sets. The target variable, "IS_SUCCESSFUL," was defined, with a value of 1 signifying success and 0 indicating failure. Further scrutiny of application data involved binning based on CLASSIFICATION values. Each distinct value was used as a threshold to group together "rare" categorical variables under the umbrella term 'Other'. Rigorous validation checks were then conducted to ensure the efficacy of this binning process. Categorical variables were encoded using the 'pd.get_dummies()' technique.

- Compiling, Training, and Evaluation the Model:
  For every model, a Neural Network was utilized, consisting of three layers in total, each with multiple layers. The number of hidden nodes in each layer was determined based on the features present in the dataset.

  ```python

```
