# Introduction

## Overview
An introduction to the **applications of machine learning** to tasks in **life sciences**

### Background
* Calculus, Linear Algebra
* Probabbility, Programming
* Introductory Biology

### Why DL in LS
* Enabled by the convergence of three things:
	* Inexpensive, high quality, collection of datasets
		* Seq
		* Imaging
		* Documents
	* New ML methods (incl ensemble)
	* High performance GPU ML implementations
		* CUDA, cudnn, etc
* Result is completely transformative

### Why Computational Biology
* Lots of data (* lots of data)

> Many layers of abstraction in bio that are hard ot grasp manually; highly complex non-linear relations with biological data to reveal non-surface level/deeper insights 

* Why would a computer scientist study biology?
	* *Is there any other way?!*


* There are rules
	* Let computation drive experimentation rather than computation being at the service of the hypotheses


## Extracting Signal from Noise

![](https://i.imgur.com/xab6qZ2.jpg)


## Some AI, ML and DL Stuff

### Living Breathing Field
This subject is still rapidly growing, so the best way to learn this material is to dive head first into the literaure and explore! Read, read, read!

![](https://i.imgur.com/rQDF7Z1.png)


### Statistical Perspective

![](https://i.imgur.com/kRB19Oe.png)


* There is observed part of the universe and the hidden part
	* Making inferences on the hidden part using the observed part

$$P(H|D) = \frac{P(Data|Hypothesis)P(Hypothesis)}{P(Data)}$$
Using data to predict liklihood of some hypothesis

![](https://i.imgur.com/wSzRvcx.png)


If we know the model of the world, we can extract/generate some data.

$$P(x_i|u_j) = \frac{1}{\sqrt{2\pi}} \exp\left\{   - \frac{(x_i - u_j)^2}{2}  \right\}$$

Infer clusters of objects; this is a generative approach to learning


We can also talk about discriminative approach to learning like SVM

### Biological Inspiration

![](https://i.imgur.com/5yfHQZc.png)

