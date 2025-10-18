# Linear Regression
Linear regression is a statistical technique used to find the relationship between variables.  
![[Pasted image 20250811184739.png]]
**Loss** is a numerical metric that describes how wrong a model's predictions are.  
When choosing the best loss function, consider how you want the model to treat outliers.  

**Note the relationship between the model and the data:**
- **MSE**: The model is closer to the outliers but further away from most of the other data points.
- **MAE**: The model is further away from the outliers but closer to most of the other data points.

---

## Hyperparameters vs Parameters
Hyperparameters are variables that control different aspects of training. Three common hyperparameters are:
- **Learning rate**
- **Batch size**
- **Epochs** : One full pass over the entire training data.

In contrast, **parameters** are the variables, like the weights and bias, that are part of the model itself.  
In other words:
- **Hyperparameters**: values that you control
- **Parameters**: values that the model calculates during training

---

## Learning Rate
The learning rate determines the magnitude of the changes to make to the weights and bias during each step of gradient descent.

$$
w_{\text{new}} = w_{\text{old}} - \alpha \cdot \frac{\partial L}{\partial w}
$$
---

## Stochastic
Stochastic: the property of being well-described by a random probability distribution.

---
## Gradient Descent
**Gradient descent** is a mathematical technique that iteratively finds the weights and bias that produce the model with the lowest loss.

**Correlation Matrix** determines which features correlate with the label. 
### Covariance:
It is the measure of how two variables change together.
$$
\text{Cov}(X, Y) = \frac{\sum_{i=1}^{n} (X_i - \bar{X}) (Y_i - \bar{Y})}{n - 1}
$$
**Correlation** is the scaled version of *Covariance* that always lies between 1 and -1.
**Pearson's correlation coefficient**
$$r_{XY} = \frac{\text{Cov}(X, Y)}{\sigma_X \cdot \sigma_Y}
$$
## Normal Equations
Direct method to find the value that minimizes the loss function using mathematics.
$$
X^TX\theta = X^TY
$$

# Logistic Regression

1. Logistic regression is a regression model designed to predict the probability of a given outcome.
2. Logistic regression models use **Log Loss** as the loss function instead of squared loss.
$$
LogLoss = \sum_{(x,y)\epsilon D}-ylog(y') - (1-y)log(1-y')
$$
3. **Regularization** — a mechanism for penalizing model complexity during training — is extremely important in logistic regression modelling.

---

##  Sigmoid Function
1. Sigmoid means "S-shaped".
2. `z` is defined as the log of the ratio of the probabilities of the two possible outcomes: `y` and `1 – y`.
$$
f(x) = \frac{1}{1 + e^{-x}}
$$

---
## Regularization 

# Classification
Classification is the task of predicting which of a set of classes (categories) an example belongs to
## Confusion Matrix

![[Pasted image 20250811202138.png]]**Accuracy** is the proportion of all classifications that were correct, whether positive or negative.

The **true positive rate (TPR),** or the proportion of all actual positives that were classified correctly as positives, is also known as **recall**.

The **false positive rate (FPR)** is the proportion of all actual negatives that were classified *incorrectly* as positives, also known as the **probability of false alarm**.

**Precision** is the proportion of all the model's positive classifications that are actually positive.

# Generative Discriminant Analysis (GDA)

# Naive Bayes
## Laplace Smoothing

---


# Working with numerical data
## *Feature Vectors:*
Feature vector as the floating-point values comprising one example.
Feature vectors seldom use the dataset's _raw values_. Instead, you must typically process the dataset's values into representations that your model can better learn from.
You must determine the best way to represent raw dataset values as trainable values in the feature vector. This process is called **feature engineering**.
### Normalizing: 
1. Linear Scaling 
$$
x' = \frac{x-x_{min}}{x_{max}- x_{min}}$$
2. Z-score scaling
$$x' = \frac{x-\mu}{\sigma}$$
3. Log scaling 
$$x' = ln(x)$$
4. Clipping: It is a technique to minimize the influence of extreme outliers, it caps the value of outliers to a specific maximum 
### Binning:  
Bins or Buckets 
**Quantile bucketing** creates bucketing boundaries such that the number of examples in each bucket is exactly or nearly equal. Quantile bucketing mostly hides the outliers.
### Polynomial Transform
Allows linear model to handle non-linearities

# Working with categorical data 
## Numbers can also be categorical data 
## Encoding 
**Encoding** means converting categorical or other data to numerical vectors that a model can train on.
### Vocabulary Encoding 
### One-hot encoding
- Each category is represented by a vector (array) of N elements, where N is the number of categories.
- Exactly one of the element has the value 1.0 all the remaining have the value 0.0
- When the number of categories is high, one-hot encoding is usually a bad choice
### Embeddings 
### Problems with categorical data
1. Human raters
2. Machine raters
3. High Dimensionality 
### Feature crosses 
Combine multiple features into a new synthetic feature 
# Neural Network 