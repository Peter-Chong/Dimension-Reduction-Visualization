# Dimension Reduction Visualization

<img src="https://github.com/Peter-Chong/Dimension-Reduction-Visualization/blob/main/Images/F1.large.jpg" width="900" height="230" />

## Table of Contents  

<!--ts-->
   * [Dimension Reduction Approaches](#dimension-reduction-approaches)
   * [Principal Component Analysis (PCA)](#Principal-Component-Analysis-PCA)
   * [t-distributed Stochastic Neighbor Embedding (t-SNE)](#t-distributed-Stochastic-Neighbor-Embedding-t-SNE)
   * [Uniform Manifold Approximation and Projection (UMAP)](#Uniform-Manifold-Approximation-and-Projection-UMAP)
   * [Linear Discriminant Analysis (LDA)](#Linear-Discriminant-Analysis-LDA)
   * [Comparison](#comparison)
   * [Code and Resources Used](#code-and-resources-used)
<!--te-->

## Dimension Reduction Approaches

There are two main types of dimension reduction techniques. Either by choosing the most important features or combine the existing features to create new features. In this repository, we will be using the latter technique on Fashion MNIST dataset. This technique can further be broken down into two different methods, linear and non-linear (manifold learning). 

* **Linear:** This method transforms the data to a low dimension space as a linear combination of the original variables. This is applicable when the data is in a linear subspace and the original variables will be replaced by a smaller set of variables. 
* **Non-linear (manifold learning):** This method is applied when the original high dimensional data contains non-linear relationships. The lower dimensional representation of the data will be achieved while preserving the original distances between the data points.

## Principal Component Analysis (PCA)

<img src="https://github.com/Peter-Chong/Dimension-Reduction-Visualization/blob/main/Images/pca_2d.png" />

The aim of PCA is to derive new variables that are linear combinations of the original variables. It maximizes the variance and produces uncorrelated projected distribution. PCA can be computed by performing eigendecomposition on the covariance matrix. The eigenvectors represent the principal axes of maximum variance subspace and the eigenvalues represent the variance of projected inputs along the principal axes. In our data, the first two principal components explained 36% of the variation.

<img src="https://github.com/Peter-Chong/Dimension-Reduction-Visualization/blob/main/Images/pca_explained_var.png" />

* **Advantages of PCA:**
  * Easy to implement

* **Disadvantages of PCA:**
  * If data is non-linear, it will not well
  * It is difficult to interpret as principal components are linear combinations of the original features
  * Does not work well on categorical variables

## t-distributed Stochastic Neighbor Embedding (t-SNE)

## Uniform Manifold Approximation and Projection (UMAP)

## Linear Discriminant Analysis (LDA)

## Comparison

## Code and Resources Used

**Programming Language:** Python  
**Packages:** NumPy, pandas, plotly, scikit-learn  
**Data Source:**
https://www.kaggle.com/zalando-research/fashionmnist  
**Resources:**  
* https://towardsdatascience.com/dimensionality-reduction-for-data-visualization-pca-vs-tsne-vs-umap-be4aa7b1cb29  
* V.S, S., & Surendran, S. (2015). A Review of Various Linear and Non Linear Dimensionality Reduction Techniques.  
* Roweis, S. T. (2000). Nonlinear Dimensionality Reduction by Locally Linear Embedding. Science, 290(5500), 2323–2326.
