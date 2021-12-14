# Gradient Descent

This sub-repository mainly focuses on using Gradient Descent to solve linear regression problems.

Contents in **Gradient Descent**
* [Image](https://github.com/cissyyang1014/DataScience_and_MachineLearning/tree/main/SupervisedLearning/Gradient%20Descent/Image): folder containing images used in README
* [Data](https://github.com/cissyyang1014/DataScience_and_MachineLearning/tree/main/SupervisedLearning/Gradient%20Descent/Data): folder containing datasets
  - [penguins.csv](https://github.com/cissyyang1014/DataScience_and_MachineLearning/blob/main/SupervisedLearning/Gradient%20Descent/Data/penguins.csv): Penguins Dataset
* [Gradient_Descent.ipynb](https://github.com/cissyyang1014/DataScience_and_MachineLearning/blob/main/SupervisedLearning/Gradient%20Descent/Gradient_Descent.ipynb): Jupyter notebook containing 
  - 1) Introduction of Gradient Descent algorithm
  - 2) Implement:
    * Part 1: 
      * Build the Gradient Descent algorithm from scratch
      * Find a best linear model for a data with 4 data points using the algorithm.
    * Part 2: 
      * Build the Gradient Descent algorithm from scratch
      * Perform the Gradient Descent to find a linear regression model to predict the body mass of penguin by the flipper length
      * Compare the built algorithm with the *LinearRegression* tool from sklearn

![image](https://github.com/cissyyang1014/DataScience_and_MachineLearning/blob/main/SupervisedLearning/Gradient%20Descent/Image/GD_2.png)

### A Short Summary

# Gradient Descent

The general idea of Gradient Descent is to tweak parameters iteratively in order to find the local minimum of a function, <img src="https://latex.codecogs.com/svg.image?min_{x&space;\in&space;{R^{n}}}&space;f(x)" title="min_{x \in {R^{n}}} f(x)" />.

To find the local minimum of a function using Gradien Descent, steps should be taken proportionally to the opposite of the gradient of the function at the current point. The iterative method updates <img src="https://latex.codecogs.com/svg.image?x" title="x" /> as 

<img src="https://latex.codecogs.com/svg.image?x_{n&plus;1}&space;=&space;x_{n}-\alpha&space;\triangledown&space;f(x_{n})" title="x_{n+1} = x_{n}-\alpha \triangledown f(x_{n})" />, where <img src="https://latex.codecogs.com/svg.image?\alpha" title="\alpha" /> is the step length and <img src="https://latex.codecogs.com/svg.image?\triangledown&space;f(x_n)" title="\triangledown f(x_n)" /> is the gradient of <img src="https://latex.codecogs.com/svg.image?f(x_n)" title="f(x_n)" />.

### Algorithm

When using the Loss function <img src="https://latex.codecogs.com/svg.image?L(w,b)=&space;\frac&space;{1}{2M}&space;\sum_{i=1}^{M}{(wx^i&space;&plus;b&space;-y^i)^2}" title="L(w,b)= \frac {1}{2M} \sum_{i=1}^{M}{(wx^i +b -y^i)^2}" />:

* Step 1: Randomly choose intial <img src="https://latex.codecogs.com/svg.image?w" title="w" /> and <img src="https://latex.codecogs.com/svg.image?b" title="b" /> (<img src="https://latex.codecogs.com/svg.image?w" title="w" />, <img src="https://latex.codecogs.com/svg.image?b" title="b" /> = np.random.rand(2))

* Step 2: Set the MAX_ITER and COUNT

* Step 3: While COUNT < MAX_ITER do 

    - <img src="https://latex.codecogs.com/svg.image?w&space;=&space;w&space;-&space;\alpha&space;\times&space;\frac{\partial&space;L(w,&space;b)}{\partial&space;w}" title="w = w - \alpha \times \frac{\partial L(w, b)}{\partial w}" />
    - <img src="https://latex.codecogs.com/svg.image?b&space;=&space;b&space;-&space;\alpha&space;\times&space;\frac{\partial&space;L(w,&space;b)}{\partial&space;w}" title="b = b - \alpha \times \frac{\partial L(w, b)}{\partial w}" />
    - COUNT += 1

Please read [Gradient_Descent.ipynb](https://github.com/cissyyang1014/DataScience_and_MachineLearning/blob/main/SupervisedLearning/Gradient%20Descent/Gradient_Descent.ipynb) to learn more details.

---
### Datasets

There are two datasets used to implement Gradient Descent algorithm:
* An manually picked 4 data points 
* Penguins Dataset:

The Penguins Dataset contains size measurements for three penguin species observed on three islands in the Palmer Archipelago, Antarctica. These data were collected from 2007 - 2009 by Dr. Kristen Gorman's team. It consists of 344 rows and 7 columns. The three different species of penguins are Chinstrap, Adélie, and Gentoo penguins.
