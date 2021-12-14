# Linear Regression

This sub-repository is mainly focused on using Linear Regression algorithm on the time series financial data.

Contents of **Linear Regression**

* [Image](https://github.com/cissyyang1014/DataScience_and_MachineLearning/tree/main/SupervisedLearning/Linear%20Regression/Image): folder containing images used in README
* [Linear_Reression.ipynb](https://github.com/cissyyang1014/DataScience_and_MachineLearning/blob/main/SupervisedLearning/Linear%20Regression/Linear_Regression.ipynb): Jupyter notebook file containing
  * a. Introduction of Linear Regression
  * b. Building Linear Regression algorithm from scratch and implement Linear Regression in two different time series data (Ethereum price and Bitcoin price), and predict the future prices
  * c.  Feature Engineering

![image](https://github.com/cissyyang1014/DataScience_and_MachineLearning/blob/main/SupervisedLearning/Linear%20Regression/Image/linear-regression-in-machine-learning.png)

### A Short Summary

# Linear Regression

In machine learning, linear regression is used to find the mathematical equation that best explains the relationship between the response variable (<img src="https://latex.codecogs.com/svg.image?\mathbf{Y}" title="\mathbf{Y}" />) and the predictors (<img src="https://latex.codecogs.com/svg.image?\mathbf{X}" title="\mathbf{X}" />). The matrix notation of linear model is 

<img src="https://latex.codecogs.com/svg.image?\mathbf{Y}=\mathbf{X}\mathbf{\beta}&plus;\mathbf{\epsilon}" title="\mathbf{Y}=\mathbf{X}\mathbf{\beta}+\mathbf{\epsilon}" />, where <img src="https://latex.codecogs.com/svg.image?\beta" title="\beta" /> is unknown model parameter, and <img src="https://latex.codecogs.com/svg.image?\epsilon" title="\epsilon" /> is random error.

### Method of Least Squares

The goal of the model fitting with Least Squares is to minimize the sum of squared errors (SSE). The estimate of <img src="https://latex.codecogs.com/svg.image?\mathbf{Y}" title="\mathbf{Y}" /> by this model is <img src="https://latex.codecogs.com/svg.image?\hat{Y}=&space;\mathbf{X}\hat{\beta}=\mathbf{X}\left(&space;\mathbf{X}^{T}\mathbf{X}&space;\right)^{-1}\mathbf{X}^{T}\mathbf{Y}" title="\hat{Y}= \mathbf{X}\hat{\beta}=\mathbf{X}\left( \mathbf{X}^{T}\mathbf{X} \right)^{-1}\mathbf{X}^{T}\mathbf{Y}" />.

The hat matrix is defined as <img src="https://latex.codecogs.com/svg.image?H=\mathbf{X}\left(&space;\mathbf{X}^{T}\mathbf{X}&space;\right)^{-1}\mathbf{X}^{T}" title="H=\mathbf{X}\left( \mathbf{X}^{T}\mathbf{X} \right)^{-1}\mathbf{X}^{T}" />, 
which composed solely from the sample values of the predictor variables.

Please read [Linear_Reression.ipynb](https://github.com/cissyyang1014/DataScience_and_MachineLearning/blob/main/SupervisedLearning/Linear%20Regression/Linear_Regression.ipynb) to learn more details.

---

### Datasets

There are two datasets used to implement Linear Regression algorithm:
* Ethereum price
* Bitcoin price

Both Ethereum price and Bitcoin price are extracted from [yahoo finance](https://finance.yahoo.com/) using [pandas-datareader](https://pydata.github.io/pandas-datareader/), which is a powerful tool that can extract data from various Internet sources into a panda DataFrame.
