# Neural_Network_Charity_Analysis
## Purpose 
The purpose of this exercise was to implement and optimize a neural network for Alphabet Soup to predict which investments would be successful investments. 

## Results 
### Data Preprocessing
* The targeted variable for this the exercise was the IS_SUCCESSFUL metric in the charity.csv. 4
* The feature variables in this data were APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT.
* To identification variables, EIN and NAME, were removed form the dataset, as they had no bearing on whether an investment was successful or not. 

### Compiling, Training, and Evaluating the Model
* The base model was defined in AlphabetSoupCharity.ipynb using tensorflow.keras.model.Sequential and tetensorflow.keras.layers.Dense with the following parameters:
    - Training duration (epochs): 10 - Justification: no significant change in accuracy or loss at around 6 epochs, and did not want to cause overfitting of the data. 
    - Hidden Layer Function: Relu - Justification: ideal for looking at positive nonlinear classification data, which this data is. 
    -  Number of Layers: 2 - Justification: having an extra hidden layer allows the data to train on active input values instead of additional input data.
    - Number of neurons: 1st layer: 80/ 2nd layer: 30 
    - Output Layer : Sigmoid - Justification: normalizes the data to a probability between 0 and 1 which is good for binary classification data such as this data. 
    - Bucketing of Application_type and Classification : 200 - Justification: condense the amount of data creating less noisy data

* Results of base model : 
    - Accuracy : 0.59
    - Loss of 0.691

* Opitimization of base model is defined in AlphabetSoupCharity_Optimization.ipynb
    - Training duration (epochs): increased to 30: to allow the model more training time and ability to learn more trends within the data
    - Number and types of layers : no change
    - Number of neurons: 1st layer changed to 82 / 2nd layer lowered to 20: 82 is closer to double the number of features (43)
    - Bucketing of Application_type and Classification : increased to 700 - Justification: condense the amount of data even further condensing the noise of the data and creates an evenly distributed dataset eliminating rare categories, allowing the model to learn trends more accurately

* Results of Optimized model:
    - Accuracy : 0.69
    - Loss : .767

### Summary
In summary, a deep neural network classification model is presented that predicts whether an investment applicant is successful with an accuracy of 69%. This accuracy does not meet the minimum requirement of 75%, and there is not a significant improvement. 


