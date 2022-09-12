# MODULE 10 CHALLENGE : Crypto Investments

In this challenge we are taking on the role of an advisor at a financial advisory firm. We want to propose a novel approach to assembling investment portfolios that are based on cryptocurrencies. We are aiming to include other factors that might impact the crypto market, doing more than just investigating returns and volitility. For this challenge we are tasked with creating a jupyter notebook that clusters cryptocurrencies by their performance in different time periods. Then plot the results so that we can visually show the performance to the board of directors.

We start this challenge by importing the data as a dataframe, using the 'read_csv' function. Then we move to preparing the dataframe for analysis by using the 'StandardScaler' module and the 'fit_transform' function. Then we take the index from the old dataframe and set it as the index of the new dataframe so that we can see the name of the coins.

To find the best value for 'k' using the original data we utilize a for loop to compute the inertia for each possible 'k' value in a given range. We then transfer that data from a list into a dictionary and then into a dataframe so that we can visualize the numbers via an Elbow Curve plot. The best 'k' value for this data would be set at 4.

To cluster each cryptocurrency with K=means using the original data we need to initialize a model, and we set the number of clusters to the best 'k' value that we calculated earlier. We then fit the module using the scaled data, and predict the clusters using that data to produce an array of cluster values. We then create a new dataframe and add the array of cluster values as a column. Once we have that column in place we can create a scatter plot and group the graph points by their values in the array of cluster values.

To reduce the features to three principal components we optimize the clusters by performing a principal component analysis. Instead of a K-means model we initialize a 'pca' model using the 'pca' module and the 'fit_transform' function, and create a dataframe based on that model. We then can calculate the explained variance ratio for each principal component to see how accurate our analysis is, and to determine how much information can be attributed to each principal component. With the 'pca' data we can create another pandas dataframe for further analysis and we would again take the index from the old dataframe and set it as the index of the new dataframe so that we can see the name of the coins.

We again find the best 'k' value for the 'pca' data by following the same steps and procedures. The best 'k' values for this particular challenge did not change when using PCA data versus the original scaled data.

We also cluster the cryptocurrencies from the 'pca' data by using the K-means model from before, following the same steps.

At the end of this analysis we compared each of the plots side-by-side to compare the results by using the (+) operator while using hvPlot. Doing this allows for us to see that the impact of using fewer features to cluster the data using K-means is that the scatter plots will portray a better visualition of the clusters, making them more defined.


---

## Technologies

This project leverages python 3.7 with the following packages:

* [Pandas](https://github.com/google/pandas) - Pandas is a powerfull tool for data analysis and manipulation. Pandas provides a plethora of useful functions that make it easy to express, analyze, and manipulate data.

* [Hvplot](https://github.com/google/hvplot) - This Module provides a high-level potting API that allows for users to easily generate a wide array of plot types. HvPlot's main benefit is that it allows for very interactive visualizations.

* [scikit-learn](https://scikit-learn.org/stable/) - This is a machine learning library for the python programming language. This library allows for the use of multiple machine learning models, tools, and algorithms.



---

## Installation Guide

Before running the application first install the following dependencies.

```
import pandas as pd
import hvplot.pandas
from pathlib import Path
from sklearn.cluster import KMeans
from sklearn.decomposition import PCA, KernelPCA
from sklearn.preprocessing import StandardScaler


```

---

## Usage

To use the Crypto Clustering application file simply clone the repository and open the crypto_investments.ipynb file in Jupyter Notebook.

Upon opening the file you will have the option to run the whole note book and that will provide you with all of the calculations, evaluations, and visualizations for the analysis of the cryptocrurrency data. With the implementation of the Voila library you will have access to all of the outputs of the code as a web application. Some screenshots of that in action can be seen below via this link

* [SCREENSHOTS](https://github.com/AdamCooke22/module_ten/tree/main/screenshots) 

## Contributors

Completed by Adam Cooke

---

## License

MIT

