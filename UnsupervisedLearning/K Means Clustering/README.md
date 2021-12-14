# K Means Clustering

This sub-repository mainly focuses on using K Means Clustering to solve classification problems. The **Principal Component Analysis (PCA)** is used to reduced the dimension of the dataset.

Contents of **K Means Clustering**

* [Image](https://github.com/cissyyang1014/DataScience_and_MachineLearning/tree/main/UnsupervisedLearning/K%20Means%20Clustering/Image): folder containing images used in README
* [Data](https://github.com/cissyyang1014/DataScience_and_MachineLearning/tree/main/UnsupervisedLearning/K%20Means%20Clustering/Data): folder containing all data files used in this module
  - [penguins.csv](https://github.com/cissyyang1014/DataScience_and_MachineLearning/blob/main/UnsupervisedLearning/K%20Means%20Clustering/Data/penguins.csv): Penguins Dataset
* [K Means Clustering_iris.ipynb](https://github.com/cissyyang1014/DataScience_and_MachineLearning/blob/main/UnsupervisedLearning/K%20Means%20Clustering/K%20Means%20Clustering_iris.ipynb): Jupyter notebook file containing
  * a. Building K Means Clustering algorithm from scratch
  * b. Performing K Means Clustering using Iris Dataset to classify the iris species
  * c. Using PCA to reduce the dimensions of the dataset and compare
* [K Means Clustering.ipynb](https://github.com/cissyyang1014/DataScience_and_MachineLearning/blob/main/UnsupervisedLearning/K%20Means%20Clustering/K%20Means%20Clustering.ipynb): Jupyter notebook file containing
  - a. Introduction of K Means Clustering algorithm
  - b. Building K Means Clustering algorithm from scratch
  - c. Performing K Means Clustering using Penguins Dataset to classify the penguins species
  - d. Using PCA to reduce the dimensions of the dataset and compare

![image](https://github.com/cissyyang1014/DataScience_and_MachineLearning/blob/main/UnsupervisedLearning/K%20Means%20Clustering/Image/k%20means.png)

### A Short Summary

# K Means Clustering

The goal of K means clustering is to partition a given dataset into a set of K groups/clusters. K is pre-defined by analyst. A large K means smaller groups with more granularity, while a lower K means larger groups with less granularity.

The output of the K means clustering is the "labels". The algorithm assigns each data point to one of the K groups based on the feature similarity. In K means clustering, each group is defined by the centroid for each group. The centroids are the center of the cluster, which finds the points closest to them and takes them to the cluster, and thus, minimize the sum of the squared distances to the cluster centroids.

### Algorithm
* Step 1: Randomly choose K distinct feature vectors as your starting "centroid", <img src="https://latex.codecogs.com/svg.image?c_1,&space;c_2,&space;...,&space;c_k" title="c_1, c_2, ..., c_k" />
* Step 2: Assign each feature vector to the closest centroid, <img src="https://latex.codecogs.com/svg.image?A_i=\begin{Bmatrix}&space;x:&space;x_i&space;\text&space;{&space;is&space;assigned&space;to&space;}&space;&space;c_i&space;\end{Bmatrix}" title="A_i=\begin{Bmatrix} x: x_i \text { is assigned to } c_i \end{Bmatrix}" />
* Step 3: Let <img src="https://latex.codecogs.com/svg.image?c_i&space;\rightarrow&space;&space;\frac&space;{1}{|A_i|}\sum_{x\in&space;A_i}&space;x" title="c_i \rightarrow \frac {1}{|A_i|}\sum_{x\in A_i} x" />
* Step 4: Repeat Step 2 and Step 3 until the centroids no longer move

### Loss Function

For each <img src="https://latex.codecogs.com/svg.image?A_i" title="A_i" />,

<img src="https://latex.codecogs.com/svg.image?L=\frac&space;{1}{2}&space;\sum_{x&space;\in&space;A_i}&space;(c_i-x)^2" title="L=\frac {1}{2} \sum_{x \in A_i} (c_i-x)^2" />, where <img src="https://latex.codecogs.com/svg.image?x" title="x" /> is a data point belonging to the cluster <img src="https://latex.codecogs.com/svg.image?A_i" title="A_i" />, and <img src="https://latex.codecogs.com/svg.image?c_i" title="c_i" /> is the centroid of the cluster <img src="https://latex.codecogs.com/svg.image?A_i" title="A_i" />.

### How to choose K value? 

Elbow Method.

Please read [K Means Clustering.ipynb](https://github.com/cissyyang1014/DataScience_and_MachineLearning/blob/main/UnsupervisedLearning/K%20Means%20Clustering/K%20Means%20Clustering.ipynb) to learn more details.

# Principal Component Analysis (PCA)

PCA is a technique to reduce the dimensionality of the large dataset. It transforms a large set of variables into a smaller one that still contains most of the information. 

To calculate PCA:

* Calculate the mean values of each variables
* Center the values in each variables by subtractiong the corresponding mean values
* Calculate the covariance matrix of the centered matrix
* Calculate the eigendecomposition of the covariance matrix


Please read [K Means Clustering.ipynb](https://github.com/cissyyang1014/DataScience_and_MachineLearning/blob/main/UnsupervisedLearning/K%20Means%20Clustering/K%20Means%20Clustering.ipynb) to learn more details.

---

### Datasets

There are two datasets used to implement K Means Clusteringn algorithm:
* Iris Dataset:

The Iris Dataset is loaded from sklearn.datasets. The data set consists of 50 samples from each of three species of Iris (Iris setosa, Iris virginica and Iris versicolor). Four features were measured from each sample: the length and the width of the sepals and petals, in centimeters.

* Penguins Dataset:

The Penguins Dataset contains size measurements for three penguin species observed on three islands in the Palmer Archipelago, Antarctica. These data were collected from 2007 - 2009 by Dr. Kristen Gorman's team. It consists of 344 rows and 7 columns. The three different species of penguins are Chinstrap, Adélie, and Gentoo penguins.
