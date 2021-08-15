# Dimension Reduction Visualization

<img src="https://github.com/Peter-Chong/Dimension-Reduction-Visualization/blob/main/Images/F1.large.jpg" width="900" height="230" />

## Table of Contents  

<!--ts-->
   * [Problem Statement](#problem-statement)
   * [Project Overview](#project-overview)
   * [Dimension Reduction Approaches](#dimension-reduction-approaches)
   * [Principal Component Analysis (PCA)](#Principal-Component-Analysis-PCA)
   * [Linear Discriminant Analysis (LDA)](#Linear-Discriminant-Analysis-LDA)
   * [t-distributed Stochastic Neighbor Embedding (t-SNE)](#t-distributed-Stochastic-Neighbor-Embedding-t-SNE)
   * [Uniform Manifold Approximation and Projection (UMAP)](#Uniform-Manifold-Approximation-and-Projection-UMAP)
   * [Comparison of Techniques](#Comparison-of-Techniques)
   * [Code and Resources Used](#code-and-resources-used)
<!--te-->

## Problem Statement

With high dimensional data, we are faced with some of the following problems:
 - High computational cost
 - Difficult to visualize
 - Curse of dimensionality (Occurs when number of features >> number of rows)

## Project Overview

We will be using four different dimensionality reduction techniques on Fashion MNIST dataset.

| Dimension Reduction Technique | Year Released | Linearity | Type |
| :---: | :---: | :---: | :---: |
| PCA | 1930 | Linear | Unsupervised |
| LDA | 1936 | Linear | Supervised |
| t-SNE | 2008 | Non-Linear | Unsupervised |
| UMAP | 2018 | Non-Linear | Both |

## Dimension Reduction Approaches

There are two main types of dimension reduction techniques. Either by choosing the most important features or combine the existing features to create new features. In this repository, we will be using the latter technique. This technique can further be broken down into two different methods, linear and non-linear (manifold learning). 

* **Linear:** This method transforms the data to a low-dimension space as a linear combination of the original variables. This is applicable when the data is in a linear subspace and the original variables will be replaced by a smaller set of variables. 
* **Non-linear (manifold learning):** This method is applied when the original high-dimensional data contains non-linear relationships. The lower-dimensional representation of the data will be achieved while preserving the original distances between the data points.

## [Principal Component Analysis (PCA)](https://nbviewer.jupyter.org/github/Peter-Chong/Dimension-Reduction-Visualization/blob/main/Algorithms/PCA.ipynb)

<img src="https://github.com/Peter-Chong/Dimension-Reduction-Visualization/blob/main/Images/pca_2d.png" />

PCA is a linear dimensionality reduction technique. The aim of PCA is to derive new variables that are linear combinations of the original variables. It maximizes the variance and produces uncorrelated projected distribution. PCA can be computed by performing eigendecomposition on the covariance matrix. The eigenvectors represent the principal axes of maximum variance subspace and the eigenvalues represent the variance of projected inputs along the principal axes. In our data, the first two principal components explained 36% of the variation.

<img src="https://github.com/Peter-Chong/Dimension-Reduction-Visualization/blob/main/Images/pca_explained_var.png" />

* **Advantages of PCA:**
  * Easy to implement

* **Disadvantages of PCA:**
  * Does not work well if data is non-linear
  * Does not work well on categorical variables
  * It is difficult to interpret as principal components are linear combinations of the original features

## [Linear Discriminant Analysis (LDA)](https://nbviewer.jupyter.org/github/Peter-Chong/Dimension-Reduction-Visualization/blob/main/Algorithms/LDA.ipynb)

<img src="https://github.com/Peter-Chong/Dimension-Reduction-Visualization/blob/main/Images/lda.png" />

LDA is a supervised linear dimensionality reduction technique. LDA can be achieved by using two calculations. First, we calculate the distance between the mean of different classes or known as between-class variance. Second, we calculate the variance of each class which is known as within-class variance. The aim of LDA is to maximize between-class variance and minimize within-class variance. 

* **Advantages of LDA:**
  * Easy to implement

* **Disadvantages of LDA:**
  * Requires a label column as it is a supervised dimension reduction technique
  * Requires normal distribution assumption on features
  * Does not work well if data is non-linear

## [t-distributed Stochastic Neighbor Embedding (t-SNE)](https://nbviewer.jupyter.org/github/Peter-Chong/Dimension-Reduction-Visualization/blob/main/Algorithms/t-SNE.ipynb)

<img src="https://github.com/Peter-Chong/Dimension-Reduction-Visualization/blob/main/Images/tsne_2d.png" />

t-SNE is a non-linear dimensionality reduction technique and it comprises three main stages. Firstly, t-SNE construct a probability distribution over pairs of points in the original (high) dimension. Similar points are assigned with a higher probability while dissimilar points are assigned with a lower probability. Secondly, t-SNE defines another probability distribution over the points over the points in a low dimension. Lastly, it minimizes the KL divergence between the two distributions with respect to the locations of the points. 

Since our data has a high number of features (784) and it is highly recommended to use another dimensionality reduction method such as PCA to reduce the number of dimensions, we will be using PCA to reduce it to 50 principal components / features. 

* **Advantages of t-SNE:**
  * Handles non-linear data
  * Preserve local structure well

* **Disadvantages of t-SNE:**
  * Computational complexity of O(n^2)
    * Can be improved using Barnes-Hut approximation to O(nlogn)
    * Or reduce the number of dimensions beforehand by using other dimension reduction tools such as PCA or TruncatedSVD
  * Needs to hypertune the parameters such as perplexity and max_iter
  * It can only be embedded into 2 or 3 dimensions, hence it is only good for visualization and not dimension reduction
  * Does not preserve the global structure

## [Uniform Manifold Approximation and Projection (UMAP)](https://nbviewer.jupyter.org/github/Peter-Chong/Dimension-Reduction-Visualization/blob/main/Algorithms/UMAP.ipynb)

<img src="https://github.com/Peter-Chong/Dimension-Reduction-Visualization/blob/main/Images/umap_unsup.png" />

UMAP is a state-of-the-art non-linear dimensionality reduction technique and at its core, works similarly to t-SNE. Both of the algorithms use graph layout algorithms to arrange data in low dimensional space. UMAP first constructs a high-dimensional graph representation of the data. Then, it optimizes a low dimensional graph to be as structurally similar to the high dimensional graph as possible. Instead of using a perplexity value in t-SNE, UMAP defines nearest neighbors and minimum distance. The nearest neighbor will affect the influence given to global versus local information and minimum distance will affect how compactly packed the local parts are.

By using the labels, UMAP can utilize them and create a supervised dimension reduction. 

<img src="https://github.com/Peter-Chong/Dimension-Reduction-Visualization/blob/main/Images/umap_sup.png" />

* **Advantages of UMAP:**
  * Significantly faster than t-SNE
  * Capture global structure well
  * UMAP supports unsupervised, supervised and semi-supervised dimension reduction

* **Disadvantages of UMAP:**
  * It is a new technique, the libraries and best practices have yet to be robust

## Comparison of Techniques

### Supervised Dimension Reduction

<img src="https://github.com/Peter-Chong/Dimension-Reduction-Visualization/blob/main/Images/lda_small.png" width="412" /><img src="https://github.com/Peter-Chong/Dimension-Reduction-Visualization/blob/main/Images/umap_sup_small.png" width="412" height="208" />

### Unsupervised Dimension Reduction

<img src="https://github.com/Peter-Chong/Dimension-Reduction-Visualization/blob/main/Images/pca_small.png" width="275" /><img src="https://github.com/Peter-Chong/Dimension-Reduction-Visualization/blob/main/Images/tsne_small.png" width="275" /><img src="https://github.com/Peter-Chong/Dimension-Reduction-Visualization/blob/main/Images/umap_unsup_small.png" width="275" height="139"/>

### Run Time

| Dimension Reduction Technique | Type | Run Time |
| :---: | :---: | ---: |
| LDA | Supervised | 13.97s |
| UMAP | Supervised | 82.31s |
| PCA | Unsupervised | 5.98s |
| t-SNE | Unsupervised | 1180.41s |
| UMAP | Unsupervised | 70.56s |

## Code and Resources Used

**Programming Language:** Python  
**Packages:** NumPy, pandas, plotly, scikit-learn  
**Data Source:**
https://www.kaggle.com/zalando-research/fashionmnist  
**Resources:**  
* https://pair-code.github.io/understanding-umap/
* https://towardsdatascience.com/dimensionality-reduction-for-data-visualization-pca-vs-tsne-vs-umap-be4aa7b1cb29
* V.S, S., & Surendran, S. (2015). A Review of Various Linear and Non Linear Dimensionality Reduction Techniques.  
* Roweis, S. T. (2000). Nonlinear Dimensionality Reduction by Locally Linear Embedding. Science, 290(5500), 2323–2326.
