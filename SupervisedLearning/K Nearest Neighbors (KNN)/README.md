# K Nearest Neighbors (KNN)

### Idea: 
Data with similar features "should" be close in space.

### Algorithm:
* Step 1: Choose k
* Step 2: Calculate the distance from your new point to every point in your training set (computational expensive)
* Step 3:
    - For Classification: of the k closest points predict the majority label
    - For Regression: predict the average label for the K closest points

### Calculate distance:

Two-Dimention formular:

$d(p, q) = \sqrt {(p_1-q_1)^2+(p_2-q_2)^2}$

n-Dimention formular:

$d(p, q) = \sqrt {(p_1-q_1)^2+(p_2-q_2)^2+...+(p_n-q_n)^2}=\sqrt {\sum \limits_{i=1}^{n}(p_i-q_i)^2}$



### How to choose K?
K should be odd for classification.

### How should we measure error?

$$E = \frac {1}{M} \sum \limits_{i=1}^{M} \left(y_i \ne \hat y_i \right)$$
