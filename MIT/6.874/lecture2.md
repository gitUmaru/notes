# Optimizing Feedforward Networks

## What is ML
* [Shalev-Shwartz and Ben-David, 2014]: “Learning is the process of converting experiencee into expertise or knowledge.”
* [Mohri et al., 2012]: “Machine learning can be broadly defined as computational methods using experience to improve performance or to make accurate predictions.” 
* [Murphy, 2012]: “The goal of machine learning is to develop methods that can automatically detect patterns in data, and then to use the uncovered patterns to predict future data or other outcomes of interest.” 
* [Hastie et al., 2001]: “[...] state the learning task as follows: given the value of an input vector x , make a good prediction of the output y , denoted by y_hat”

### Definition
A computer program is said to learn from **experience E** with respect to some **class of tasks T** and **performance measure P**, if its performance at tasks in T, as measured by P, improves with experience E.

![](https://i.imgur.com/kOQxeTX.png)

### Terminology
* Input
	* features (in machine learning)
	• predictors (in statistics)
	• independent variables (in statistics)
	• regressors (in regression models)
	• input variables
	• covariates

* Output
	* labels (in machine learning)
	• responses (in statistics)
	• dependent variables (in statistics)
	• regressand (in regression models)
	• target variables

$$f: X \to Y$$
$$f(x;\theta) = \hat y$$

### Types of ML
| Classifcation | Regression | Unsupervised Learning |
|---------------|------------|-----------------------|
|        ![](https://i.imgur.com/9EUjzPE.png) |          ![](https://i.imgur.com/fUGEQfl.png)  |     ![](https://i.imgur.com/sgBTgKo.png) |


### Objective Function
An **objective function** $J(\Theta)$ is the function that you optimize when training machine learning models. It is usually in the form of (but not limited to) one or combinations of the following:

**Loss / cost / error function L(y_hat , y ):**
	Classification
		• 0-1 loss
		• cross-entropy loss
		• hinge loss
	Regression
		• mean squared error (MSE, L2norm)
		• mean absolute error (MAE, L1norm)
		• Huber loss (hybrid between L1 and L2 norm)
	Probabilistic inference
		• Kullback-Leibler divergence (KL divergence)

**Likelihood function / posterior:**
	• negative log-likelihood (NLL) in maximum
	likelihood estimation (MLE)
	• posterior in maximum a posteriori estimation
	(MAP)

**Regularizers and constraints**

* L1 regularization $|| \Theta||_1 = \lambda  \sum_{i=1}^N |\theta_i|$
* L1 regularization $|| \Theta||_2^2 = \lambda  \sum_{i=1}^N \theta_i^2$
* max-norm $|| \Theta||_2^2 \leq c$

#### Loss Functions for Classifications

![](https://i.imgur.com/ES5c82o.png)


![](https://i.imgur.com/QdT0ecu.png)

#### Loss Functions for Regression
**Mean squared error:**

Probabilistic interpretation:
	LMSE = NLL, under the assumptation that the noise is normally distributed, with constant mean
	and variance

**Mean absolute error**


#### Empirical Risk Minization
**Expected risk** (loss) associated with hypothesis h(x ):

$$\mathcal{R}_{\mathtt{exp}} (h) = \mathbb{E}(\mathcal{L} ( h(x), y ))  = \int_{\mathcal X\times \mathcal Y} \mathcal L (h(x) , y) p(x,y) dxdy$$

Minimize Rexp(h) to find optimal hypothesis h:

$$ h = {\arg \min}_{h\in F} \mathcal{R}_{\mathtt{exp}} (h) $$

But the issue is that we don't know the distribution of p(x,y) and that F is too large

#### Gradient Descent

![](https://i.imgur.com/EOmiWJ4.png)

Simple chain rule stuff, but not sure how to do for global min/max

### Training and Eval
**Training set (Straining):**
	• set of examples used for learning
	• usually 60 - 80 % of the data
**Validation set (Svalidation):**
	• set of examples used to tune the model hyperparameters
	• usually 10 - 20 % of the data
**Test set (Stest):**
• set of examples used only to assess the performance of fully-trained model
• after assessing test set performance, model must not be tuned further
• usually 10 - 30 % of the data

#### Confusion matrix and derived metrics


![](https://i.imgur.com/gYXRJHT.png)

#### ROC Performance

![](https://i.imgur.com/Yz1WbLH.png)


AuROC is a common metric for comparing classification methods
TPR = TP / (TP + FN)
FPR = FP / (FP + TN)
**Problematic when we have an unbalanced dataset (example more positives than negatives)**

**PR Curves Performances**

Precision = PPV = TP / (TP + FP) = 1 - FDR
Recall = TPR = TP / (TP + FN)
**Useful when datasets are unbalanced**

ROC and PRC curves are complementary

#### Regression Metric 1 - Pearson Correlation
* Pearson correlation coefficient is r
* r 2 is the fraction of linearly explained variance
$$r = \frac{(x - \bar x)}{|| x ||} \cdot \frac{(y - \bar y)}{||y||}$$

#### Regression Metric 2 - Spearman Rank Correlation

* Pearson correlation of observation ranks
	* For ties assign fractional ranks by average rank in ascending order

#### Regression Metric 3 - Hypothesis Testing

![](https://i.imgur.com/qm3bQP0.png)

* t is distributed as Student’s t-distribution with n −2 degrees of freedom under the null hypothesis
	* n is the number of observations 
	* $t = r \frac{n-2}{1-r^2}$
	* Alternatively we can permute values to observe the empirical distribution of null correlations
* Two sided tests are used when we are testing for a difference without regard to direction
	* Two sided tests allocate half the area to each direction
	* Thus they are more strict if you only wish to test in one direction

![](https://i.imgur.com/CWPo8ie.png)

![](https://i.imgur.com/hMO8FYQ.png)

**CORRELATION IS NOT CAUSATION**


## Traditional NN
Deep learning -> many layers of abstraction

**Convolutional Filter**

![](https://i.imgur.com/3bBoEnz.png)



#### Inspirations from Biology

![](https://i.imgur.com/d9RYqex.png)

![](https://i.imgur.com/sclxRn1.png)

Given an input, multiply it by a weight and check to see if it crosses some activation threshold

* TRUE
	* Return value to next neuron
* FALSE
	* Return nothing

Introduce nonlinearity in activation functions so that we can capture non-linear trends. Instead of linearizing all of our data.

* Sigmoid
* Softplus
* ReLU

Learn the function that converts pixels of an image to classifcaiotn of cat/person/etc.
* How do I adjust the weights so that it learns this function

### Gradient Based Learning

$$w^t \leftarrow w^{t-1} - \epsilon \left( \frac{\partial E}{\partial w} + \lambda w^{t-1}\right) + \eta \Delta w^{t-1}$$

where
• Gradient descent: $\frac{\partial E}{\partial w}$ = partial derivative of error E wrt w
• $\epsilon$ = learning rate (e.g. <0.1), needed to not overshoot the optimal solution
• $\lambda$ = weight decay, penalizes large weights to prevent overfitting
• $\eta$ = momentum, based on magnitude+sign of previous update $\Delta w^{t-1}$; when direction of update is consistent -> faster convergence

#### Using only a subset of samples at a time:
• ***Stochastic* gradient descent (SGD)**: speed up computation
	• Randomly sample subset of samples
	• Update the weights using only that subset
• **On-line learning**: Update gradient using only 1 training data point each time


HOWEVER, The steepest gradient is not necessarily toward the optimum point

![](https://i.imgur.com/6RVjWzZ.png)


## Backpropogation

![](https://i.imgur.com/reZIWsZ.png)



## Model Capacity

### Definition
The **capacity** (Vapnik-Chervonenkis dimension) of a model describes how many points can be correctly predicted when they are produced by an adversary

* Not just parameters, but also what type of functions that I can come up with

The capacity of non-parametric models isdefined by the size of their training set
* k-nearest neighbor (KNN) regression computes its
output based upon the k “nearest” training
examples
* Often the best method, and certainly a baseline to beat

The **generalizability** of a model describes its ability to perform well on previously unseen inputs

We need to control model complexity for good generalization

We can regularize our parameters

Parameter regularization instead of controlling model complexity; trade off complexity for generazability

![](https://i.imgur.com/sKqdTsz.png)

[Demo](http://cs.stanford.edu/people/karpathy/convnetjs/demo/classify2d.html)


* We can do drop out too
* Clamping
	* Forcing lower level dimensiosn
* Add noise