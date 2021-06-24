# Dimension Reduction Visualization

## Table of Contents  

<!--ts-->
   * [Importance of Dimension Reduction](#importance-of-dimension-reduction)
   * [Importance of Visualization](#importance-of-visualization)
   * [Dimension Reduction Approaches](#dimension-reduction-approaches)
   * [Code and Resources Used](#code-and-resources-used)
<!--te-->

## Importance of Dimension Reduction

* Irrelevant features will worsen the performance of some machine learning algorithm
* Avoids overfitting
* Reduce storage space
* By reducing the dimension down to 2D or 3D allow us to visualize the data

## Importance of Visualization

* It allows us to comprehend the huge amount of data
* We might be able to notice properties that were not discovered before
* We can form hypotheses based on the visualization

## Dimension Reduction Approaches

There are two main types of dimension reduction techniques. Either by choosing the most important features or combine the existing features to create new features. In this repository, I will be using the latter technique only. It can further be broken down into two methods, linear and non-linear (manifold learning). 

* **Linear:** This method transforms the data to a low dimension space as a linear combination of the original variables. This is applicable when the data is in a linear subspace and the original variables will be replaced by a smaller set of variables. 
* **Non-linear (manifold learning):** This method is applied when the original high dimensional data contains non-linear relationships. The lower dimensional representation of the data will be achieved while preserving the original distances between the data points.


## Code and Resources Used

**Programming Language:** Python  
**Packages:** NumPy, pandas, plotly, scikit-learn  
**Resources:**
https://towardsdatascience.com/dimensionality-reduction-for-data-visualization-pca-vs-tsne-vs-umap-be4aa7b1cb29  
