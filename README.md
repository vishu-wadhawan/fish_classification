# Classifying Fish Species with Sonar Data

**Vishu Wadhawan**

**University of Toronto**


**Department of Statistical Sciences**


# Folder Structure
| Folder          | Description | 
|----------------|----------|
| Code  | R Scripts for data analysis      | 
| Dataset |  Contains data about signal strenght and frequencies   |
| Exploratory Data Analysis | Preliminary data processing and visualization      | 
| Figures and Plots         | Contains files of the graphical summaries from the final report    | 
| Written Reports | Contains pdf versions of all the reports |


# Project Description

This project aims to build a classification model that identifys trout, whitefish, and bass based on sonar signal strength. It also seeks to pinpoint the key features that influence the model’s predictions and uncover the underlying relationships between sonar frequencies and fish. 



# Resources

The github repository with the original raw acousitc data can be found [Here](https://github.com/WidebandPingFest/FishTetherExperiment)

More information about variable description can be accessed at this [link](https://support.echoview.com/WebHelp/_Introduction/About_Echoview.htm)

# Data Wrangling
First download the [dataset](https://github.com/vishu-wadhawan/fish_classification/blob/main/Dataset/processed_AnalysisData.csv). For the analysis, only the frequencies emitted by the sonar instrument were retained as
predictor variables. The other variables were excluded, as they appeared to be more closely
related to the fish’s physical characteristics. This decision reduced
the dataset from the original 484 features to 425. Moreover, all the missing values were
removed from the data which reduced the number of observation to 10333. This modified
data set had 4101 trout, 2736 bass, and 3496 whitefish

# Methods

1) Sample a random subset of 2000 individuals from each of the fish species and combine
them into one data frame

3) Using the data, apply PCA, Kernel PCA with a radial kernel function, Random Forest,
and Lasso Regression


 - For PCA examine the variability explained by the components, the projected data,
and the loadings for the first few PC’s. Identify possible variables for feature selection.
The procedure for kernel PCA is essentially the same.

-  For Lasso Regression preform a 5-fold cross validation and compute the optimal tuning
parameter λ. After, train the model with the optimal tuning parameter and calculate
the prediction accuracy. Finally, evaluate the coefficients from the results of lasso
regression and compare them between the three species. Identify possible variables for
feature selection.

-  Apply the random forest to the training set and examine the Mean Decrease Gini index
for each of the features for feature selection.

3) After having identified valid subsets of features, apply KNN, SVM with linear kernel,
and SVM with gaussian kernel to the data set with the variables of interest. Apply a 50/50
train-test split and measure prediction accuracy using a confusion matrix
