INTRODUCTION

This notebook is intended to give an introduction for machine learning (ML) beginners on how to implement and optimize a simple artificial neural network (ANN) for data classification tasks.

To this end, I apply a state-of-the-art ML framework for building and training deep learning models - the Keras API for TensorFlow 2 - to one of the most famous data sets for ML beginners: the Kaggle competition "Titanic: Machine Learning from Disaster". The goal of this challenge is to create a ML model that predicts which passengers survived the Titanic tragedy. 

Despite the thousands of notebooks that have been uploaded for this Kaggle competition, most contributions just apply an ANN model that somehow works but neither show how to optimize nor how to evaluate an ANN model.

In the notebook, I explain how one can optimize the hyperparameters of an ANN using GridSearch and cross-validation. Moreover, I discuss in detail how to evaluate the quality of an ANN, analyzing e.g. the confusion matrix and the feature importance. 

In general, we will see that a simple ANN performs very well as a classifier on the titanic dataset (top 2% on the competition leaderboard and with 83.3% test score one of the best ANNs published for this competition) and outperfomrs strong ensemble methods like Random Forests and Gradient Boosting (80.8% test score, see Appendix).

Besides the detailed introduction to modeling with ANNs, the notebook includes standard techniques for feature analysis and engineering and shows how to prepare the data for modeling using pipelines.

I hope you enjoy the notebook and, of course, I am always happy to get some comments and feedback.

So let's get started...
 
 

The notebook has also been published on Kaggle:
https://www.kaggle.com/dantefilu/a-keras-neural-network-nn-83-3-test-score
 


    

DATA OVERVIEW

The input data has been split into two groups and can be found in the folder 'input':

    training set (train.csv)
    test set (test.csv)

The training set contains the target feature 'Survived' and is used to build the machine learning models.
The test set is used to see how well the model performs on unseen data. The predictions for the test set (for which the target feature 'Survived' is unknown) 
have been sent to Kaggle for the evaluation of the test score.

The output data is stored in the folder 'output'. It contains the passenger IDs of  the test data and the respective survival status - 0 for 'dead' and 1 for 'survived'.
There are four output files:

    survived_dnn.csv (predictions of the optimized ANN)
    survived_dnn_opti.csv (predictions after GridSearch optimization - allows testing)
    survived_rf.csv (predictions of the Random Forest model, see appendix I)   
    survived_gb.csv (predictions of the Gradient Boosting model, see appendix II)
    

