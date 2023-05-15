# Early-Stopping-Hyperparameters-prediction
Predicting the eval accuracy of hyperparameters using LSTMs

## Introduction

DNN model training takes time. In hyperparameter tuning (i.e., finding the best values for some hyperparameters for a DNN model), we would need to train the DNN model repeatedly on each of the hyperparameter values and run the test. It would take even more time.

The objective of this project is to see whether we can predict the final accuracy of a DNN model for given hyperparameters values, without training the DNN model completely. In another word, can we tell how good the hyperparamter values are by just observing the results in the first small number of training eporches of the DNN model? If we can do that, it can save a lot of time in hyperparameter tuning. 
 
The method we want to try in this project is to build a Machine Learning model (called accModel) to make the prediction. For a given DNN X and a set of k hyperparameters H=<h1, h2, ..., hk> to tune, the input to the accModel includes (i) a sample hyperparameter vector Hi=<h1i, h2i, ..., hki>, where hki is the sample value of the kth hyperparameter; (ii) the observed training and validation loss values and accuracy values in the first E epochs; (iii) a positive integer M (M>E). The output of the accModel is the predicted validation accuracy of DNN X after M eporchs of training with Hi as the hyperparameter vector. 

## Installation

- Clone the repository on your local machine.
- Download the standard libraries like tensorflow. Since this project is made on google colab, the version used is 2.12.0.
- Run the cells of the notebook -'EarlyStopping.ipynb' to get the required results.
  - Change the folder paths used.
  - If you do not want to perform hyperparameter tuning you can skip the cell that creates the different models and use tf.keras.models.load_model(src) to load the best model stored in the 'final_model' folder of this repository.
  - The various functions used for data creation as well as prediction are described in the notebook.

