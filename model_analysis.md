

# Charity Funding Model Analysis

## Overview

The purpose of this analysis is to take data from the charity funding inititative, and create a neural network Machine learning model that can analyze this data with a high degree of accuracy. This model will allow us to predict the effectiveness of the charity funding initiative and help guide future charity funding decisions to ensure two things:
* support as many charities that will have a high degree of success
* deny funding to charities that have a high chance of failure

The charity dataset had the following fields and metrics:

* EIN and NAME—Identification columns 
* APPLICATION_TYPE—Alphabet Soup application type 
* AFFILIATION—Affiliated sector of industry 
* CLASSIFICATION—Government organization classification 
* USE_CASE—Use case for funding 
* ORGANIZATION—Organization type 
* STATUS—Active status 
* INCOME_AMT—Income classification 
* SPECIAL_CONSIDERATIONS—Special considerations for application 
* ASK_AMT—Funding amount requested 
* IS_SUCCESSFUL—Was the money used effectively 


## Results

### What variable(s) are the target(s) for your model?

The target variable for the model was the "IS_SUCCESSFUL" column, which is a measure if the charity was successful after receieving funding

### What variable(s) are the features for your model?

The features of this model were made from the following metrics in the dataset:

* APPLICATION_TYPE          object
* AFFILIATION               object
* CLASSIFICATION            object
* USE_CASE                  object
* ORGANIZATION              object
* STATUS                     int64
* INCOME_AMT                object
* SPECIAL_CONSIDERATIONS    object
* ASK_AMT                    int64

Both APPLICATION_TYPE and CLASSIFICATION were adjusted to include >90% of the categories. Both were adjusted to have about 10 categories that contained most of the data in the dataset. INCOME_AMT was also adjusted into buckets that included into categories.

### What variable(s) should be removed from the input data because they are neither targets nor features?

Both EIN and NAME were excluded from our model because they are identifiers, and not important features to train or test on

### Compiling, Training, and Evaluating the Model

The initial model had two relu activated hidden layers with 8 and 5 neurons each respectively. So this model had an input layer that matched the amount of features in the data, 2 hidden layers, and an output layer with a sigmoid activation to represent the predicted result. The shape of this model was chosen to reduce the complexity as data was analyzed.

This initial model performed perfectly, with 100% accuracy and very low loss. I was surprised to see this, and I thought this might be a result of overfitting so I continned to adjust the model structure instead of the data that was being fed into the testing and training.

The following models were adjusted by:

model_b 
* two more hidden layers were added
* the shape of the hidden layers was in a pyramid format
* accuracy: similar
* loss: similar

model_c 
* two more hidden layers were added
* the shape of the hidden layers was front loaded and reduced each layer
* accuracy:similar, slightly lower (99.98)
* loss: worse

model_d 
* the two hidden layers remained the same shape, but the second hidden layer was adjusted to be sigmoid activated
* accuracy:similar, slightly lower (99.95)
* loss: worse

### Summary

Overall, the model performed exceptionally. 100% accuracy and .000006% loss is a very good model. 

This model could still be improved upon in the future. For example, if the feature importances were measured, we could adjust which features to test and train on, we could also adjust further the number of dummy categorical variables are being cut from the dataset. We would also mess with different model activations, or even go outside of tensorflow's keras module to compare it to different software like pytorch. In this project, I only adjusted the hidden layers within the same keras modeler, so the data itself could still be adjusted and might improve performance. There are also other ML models out there that could perform well, or help guide the active decision making process like a tree and leaf graph to help financial advisers walk charities through this process and even guide them on what shortcomings in their charity can be improved upon before reapplying for charity funding.



Initial Model Accuracy - History

![Initial Model Accuracy - History](../images/accuracy.png)


Initial Model Loss - History

![Initial Model Loss - History](../images/loss.png)



