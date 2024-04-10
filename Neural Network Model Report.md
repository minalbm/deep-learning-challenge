## Overview:
Alphabet Soup, a philanthropic institution renowned for its backing of more than 34,000 ventures in previous years, has turned to advanced deep learning methodologies and neural networks to gauge the potential viability of applicants seeking financial support.

## Results: 
- Data Processing:
  The dataset underwent an initial preprocessing phase aimed at removing irrelevant information, which involved eliminating the EIN and NAME columns from the model. Following this step, the remaining columns were earmarked as features for the model, while the NAME column was later reintroduced during testing. To address considerable variability, both the CLASSIFICATION and APPLICATION_TYPE columns were amalgamated into a broader category labeled 'Other'. Subsequently, the dataset was partitioned into distinct training and testing sets. The target variable, "IS_SUCCESSFUL," was defined, with a value of 1 signifying success and 0 indicating failure. Further scrutiny of application data involved binning based on CLASSIFICATION values. Each distinct value was used as a threshold to group together "rare" categorical variables under the umbrella term 'Other'. Rigorous validation checks were then conducted to ensure the efficacy of this binning process. Categorical variables were encoded using the 'pd.get_dummies()' technique.

- Compiling, Training, and Evaluation the Model:
  For every model, a Neural Network was utilized, consisting of three layers in total, each with multiple layers. The number of hidden nodes in each layer was determined based on the features present in the dataset.

```python
# Define the model - deep neural net, i.e., the number of input features and hidden nodes for each layer.
number_input_features = len( X_train_scaled[0])
hidden_nodes_layer1=7
hidden_nodes_layer2=14
hidden_nodes_layer3=21

nn = tf.keras.models.Sequential()

# First hidden layer
nn.add(tf.keras.layers.Dense(units=hidden_nodes_layer1, input_dim=number_input_features, activation='relu'))

# Second hidden layer
nn.add(tf.keras.layers.Dense(units=hidden_nodes_layer2, activation='relu'))

# Output layer
nn.add(tf.keras.layers.Dense(units=1, activation='sigmoid'))

# Check the structure of the model
nn.summary()
```

Comprising three layers, the training model encapsulated a sum of 477 parameters. During the initial trial, it attained a performance level of around 72%, narrowly missing the aimed threshold of 75%.

![image](https://github.com/minalbm/deep-learning-challenge/assets/143767061/614da9fb-8971-433d-afa6-7fe8406c9700)
![image](https://github.com/minalbm/deep-learning-challenge/assets/143767061/93ac988b-6c55-4927-9bc2-9eeca5415cb5)

- Optimization:
  Upon reintroducing 'NAME' into the dataset during the second iteration, performance saw a significant improvement, reaching 79% accuracy, surpassing the target by 4%. The model, consisting of a total of 3,298 parameters, showcased this enhancement.





