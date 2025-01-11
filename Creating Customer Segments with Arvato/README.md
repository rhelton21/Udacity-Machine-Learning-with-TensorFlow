# Identify-Customer-Segments

Data clustering project using scikit-learn. Developed as final project in partial fulfillment of Udacity Nanodegree "Introduction to Machine Learning with TensorFlow".

## Project Description
#### Introduction
- Unsupervised learning techniques are applied to identify segments of population data that form the core customer base for a mail-order sales company in Germany.
- The population dataset has 85 features and 891221 entries. The customer dataset has 85 features and 191652 entries. 
- After preprocessing and feature scaling, a clustering model is created using the population dataset. This clustering model is used to cluster the customer dataset in order to identify over- and underrepresented customer segments compared to the general population.

#### Preprocessing
- The data is loaded and the missing or unknown values are evaluated (see 0).
- Missing or unknown values in the columns are investigated. To improve data quality, 4 clomns are dropped (see 1.1.2).
- Missing or unknown values in the rows are investigated. To improve data quality, rows with more than 10 missing or unknown values are dropped (see 1.1.3).
- The categorical features are evaluated. Binary categorical features with numeric values are kept without modification. Binary categorical features with non-numeric values are re-encoded. Multi-level categorical features are drop from the analysis (see 1.2.1).
- The mixed featured are evaluated. Two mixed features are separated into two dimensions. The remaining four mixed features are dropped for various reasons (see 1.2.2).
- A cleaning function is written to apply the above steps to clean and prepare the data for analysis (see 1.3).

#### Feature Transformation
- All occurrences of missing values encoded as np.nan are replaced by the mean of the corresponding column using the scikit-learn imputer function. The data is scaled using the scikit-learn StandardScaler function, scaling each feature to mean 0 and standard deviation 1. (see 2.1).
- Dimensionality reduction is performed using scikit-learn Principal Component Analysis (PCA), reducing the dataset from 66 features to 33 features while retaining approx. 90% of the information (see 2.2).

#### Clustering & Analysis
- k-means clustering is applied to the principal component space of the general population dataset. The number of clusters equals 10 reduces the average within-cluster distances without increasing computational cost too much (see 3.1).
- Correspondingly, the customer dataset is loaded, cleaned, imputed, scaled, principal component analysis is applied and clustering is applied to the principal component space of the customer dataset (see 3.2).
- The resulting predictions of the clustering model yields clustering centroids for each cluster. The centroids of each cluster allows to run an inverse transform to transform the centroids all the way back to the original feature space in order to compare the predictions of the different clusters to the original features space of the general population data (see 3.3).
- Finally, the clusters of the general population dataset and the customer dataset are compared to find, relative to the general population dataset, an overrepresented customer segment as well as an underrepresented customer segment (see 3.3).

#### Conclusion
- Cluster 5 is overrepresented in the customer dataset compared to the general population dataset. This overrepresented customer group is populated by middle-aged people, living in prosperous, high-income households and has a high share living in 1-2 family homes compared to the general population (see 3.3).
- Cluster 4 is underrepresented in the customer dataset compared to the general population dataset. This underrepresented customer group is quite younger, living in less affluent, lower income households and lives in highly densely populated areas compared to the general population (see 3.3).
- Cluster 9 is underrepresented in the customer dataset compared to the general population dataset. This underrepresented customer group is quite younger, living in comfortable to prosperous, average-income households and lives in lower densely populated areas compared to the general population (see 3.3).


## Project Files
- README.md: Project README
- Identify_Customer_Segments.ipynb: Jupyter Notebook project file containing the project


## Datasets
The datasets are not included as these are property of Bertelsmann Arvato Analytics.


## Python Version & IDE
- Python Version: 3.6
- IDE: Jupyter Notebook IDE hosted on Udacity Web Server.


## Python Modules
- numpy
- pandas
- matplotlib.pyplot
- seaborn
- sklearn.preprocessing
- sklearn.decomposition
- sklearn.cluster


## Bugs
No known bugs.


## Pending Tasks
No pending tasks.


## MIT License
Copyright (c) 2020 Udacity

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.