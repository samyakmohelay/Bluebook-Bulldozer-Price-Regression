# Bluebook-Bulldozer-Price-Prediction

In this notebook, we're going to predict the sale price of bulldozers.

<img src="https://github.com/samyakmohelay/Bluebook-Bulldozer-Price-Regression/blob/main/assets/bulldozer.png" width="650" height="400">

Since we're trying to predict a number, this kind of problem is known as a `regression problem`.

The data and evaluation metric we'll be using (root mean square log error or RMSLE) is from the Kaggle Bluebook for Bulldozers competition.

To work through these topics, we'll use pandas, Matplotlib and NumPy for data anaylsis, as well as, Scikit-Learn for machine learning and modelling tasks.

## 1. Problem Definition
For this dataset, the problem we're trying to solve, or better, the question we're trying to answer is,

> How well can we predict the future sale price of a bulldozer, given its characteristics previous examples of how much similar bulldozers have been sold for?

## 2. Data
The data is downloaded from the Kaggle [Bluebook for Bulldozers competition](https://www.kaggle.com/c/bluebook-for-bulldozers/data).

Looking at the dataset from Kaggle, we can know it's a time series problem. This means there's a time attribute to dataset.  
In this case, it's historical sales data of bulldozers. Including things like, model type, size, sale date and more.

There are 3 main datasets:

- **Train.csv** - Historical bulldozer sales examples up to 2011 (close to `4,00,000` examples with 50+ different attributes, including "SalePrice" which is the target variable).
- **Valid.csv** - Historical bulldozer sales examples from January 1 2012 to April 30 2012 (close to `12,000` examples with the same attributes as Train.csv).
- **Test.csv** - Historical bulldozer sales examples from May 1 2012 to November 2012 (close to `12,000` examples but missing the SalePrice attribute, as this is what we'll be trying to predict).

## 3. Evaluation
The evaluation metric for this competition is the RMSLE (root mean squared log error) between the actual and predicted auction prices.

For more on the evaluation of this project check: https://www.kaggle.com/c/bluebook-for-bulldozers/overview/evaluation

> Note: The goal for most regression evaluation metrics is to minimize the error. For example, our goal for this project will be to build a machine learning model which minimises RMSLE.

## 4. Features
Features are different parts of the data. During this step, we'll want to start finding out what we can about the data.

One of the most common ways to do this, is to create a data dictionary.

For this dataset, Kaggle provide a data dictionary which contains information about what each attribute of the dataset means. 
We can download this file directly from the Kaggle competition page (account required) or view it on Google Sheets.

With all of this being known, let's get started!

First, we'll import the dataset and start exploring. Since we know the evaluation metric we're trying to minimise, 
our first goal will be building a baseline model and seeing how it stacks up against the competition.

<img src="https://github.com/samyakmohelay/Bluebook-Bulldozer-Price-Regression/blob/main/assets/1.png" width="400" height="300">

<img src="https://github.com/samyakmohelay/Bluebook-Bulldozer-Price-Regression/blob/main/assets/2.png" width="400" height="300">

<img src="https://github.com/samyakmohelay/Bluebook-Bulldozer-Price-Regression/blob/main/assets/3.png" width="400" height="300">

## 5. Modelling

We've done enough EDA (we could always do more) but let's start to do some model-driven EDA.

<img src="https://github.com/samyakmohelay/Bluebook-Bulldozer-Price-Regression/blob/main/assets/4.png" width="600" height="300">

### Splitting data into train/validaton sets

<img src="https://github.com/samyakmohelay/Bluebook-Bulldozer-Price-Regression/blob/main/assets/5.png" width="600" height="300">

### Building an evaluation function

<img src="https://github.com/samyakmohelay/Bluebook-Bulldozer-Price-Regression/blob/main/assets/6.png" width="700" height="300">

## 6. Testing our model on a subset (to tune the hyperparameters)

<img src="https://github.com/samyakmohelay/Bluebook-Bulldozer-Price-Regression/blob/main/assets/7.png" width="700" height="300">

### Hyperparameter tuning with RandomizedSearchCV

<img src="https://github.com/samyakmohelay/Bluebook-Bulldozer-Price-Regression/blob/main/assets/8.png" width="700" height="500">

Finding the best model hyperparameters and Evaluating the randomized search model

![](https://github.com/samyakmohelay/Bluebook-Bulldozer-Price-Regression/blob/main/assets/9.png)

## 7. Making predictions on test data

<img src="https://github.com/samyakmohelay/Bluebook-Bulldozer-Price-Regression/blob/main/assets/10.png" width="600" height="500">

## 8. Feature Importance
Feature importance seeks to figure out which different attributes of the data were most importance when it comes to predicting the target variable (SalePrice).

![](https://github.com/samyakmohelay/Bluebook-Bulldozer-Price-Regression/blob/main/assets/11.png)
