# Classifying Fish Species with Sonar Data

**Vishu Wadhawan**

**University of Toronto**


**Department of Statistical Sciences**


# Folder Structure

In order to navigate this repository refer to the folder structure below. 


| Folder          | Description | 
|----------------|----------|
| Code  | R Scripts for data analysis      | 
| Dataset |  Contains data about signal strength and frequencies   |
| Exploratory Data Analysis | Preliminary data processing and visualizations      | 
| Figures and Plots         | Contains files of the graphical summaries from the final report    | 
| Written Reports | Contains pdf versions of all reports |


# Project Description

This project aims to build a classification model that identifys trout, whitefish, and bass based on sonar signal strength. It also seeks to pinpoint the key features that influence the model’s predictions and uncover the underlying relationships between sonar frequencies and fish. 


# Data Description 

The sonar data was collected by a group of researchers at the Algonquin Provincial Park. Their processed data set included 14575 observations and 484 features. Each row (i.e observation) corresponds to a single fish from a particular species which equates to 7248 trout, 4285 whitefish, and 3042 small mouth bass. Some notable features of the data include weight, girth, length, and the reflected signal strength (dB) from an emitted sound frequency. The emitted pulses from from the sonar instrument are labelled "F258" and "F259" (F for frequency) for example and they range from 46 KHz to 259.6 KHz; amounting to 425 different frequencies. One important aspect of this data set is that each fish is similar in size with respect to their specific species. The length of trout ranges from 343 mm to 648 mm, the length of the whitefish ranges from 220 mm to 446 mm, and finally the bass lengths range from 190 mm to 479 mm. Moreover, there are a significant number of missing responses for certain sound frequencies, though no columns have entirely missing data. Specifically, the trout species has up to 2400 missing entries for several sound frequencies while both whitefish and bass have $<$ 1000 missing entries in only a few categories. 
# Resources

The github repository with the original raw acousitc data can be found [Here](https://github.com/WidebandPingFest/FishTetherExperiment)

More information about variable description can be accessed at this [link](https://support.echoview.com/WebHelp/_Introduction/About_Echoview.htm)

# Data Wrangling
First download the dataset from [Dataset Folder](https://github.com/vishu-wadhawan/fish_classification/tree/main/Dataset). For the analysis, only keep the frequencies emitted by the sonar instrument as features (from 45 KHz to 259.6 Khz). This reduced the dataset from 484 features to 425. Next, remove all the missing values from the data, this reduces the number of observations down to 10333. The data set should now have 4101 trout, 2736 bass, and 3496 whitefish.

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
