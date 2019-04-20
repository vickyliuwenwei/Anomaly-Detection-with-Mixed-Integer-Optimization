# Anomaly Detection
Using Mixed Integer Optimization to solve traditional anomaly detection problems, by detecting outliers with relative Euclidean Distance from the median.

## Data:
### Unlabled Data:
We use publicly available data used traditionally for anomaly detection with machine learning methods, and compare relative performance with such datasets.

### Labeled Data:
We use publicly available data to run logistic regression or robust logistic regression, and compare our performance to check if it's better to remove outlier first prior to regression or simultaneously running regression and removing outliers.

## Method:
### Method for Unlabled Data:
For the unlabled datasets, we minimize sum of relative euclidean distance of all data points to the median.
We have taken 2 approaches to use unlabled data and compare performances:
#### Method 1:
We detect outlier and remove all possible outliers. It works well with synthetic datasets, but not as well if we use real world datasets.
#### Method 2:
We identify outliers by their relative distance from the median. First detect 0.01% of possible outliers, and remove. Then recalculate median, and re-detect outlier, and remove. Iterate until number of outliers are close to supposed number of outliers.

### Method of Labled Data:
For labled datasets, we have takend 2 approaches as well. As 1 approach is to remove outlier first and run regression, and the second approach is to simultaneously remove outlier and run regressino.
#### Method 1:
We first detect outlier, and remove outlier, and then run regression and compare with regression without removing outliers. Mostly, the performance is better if outlier is removed. However, it may not always be the case, since outliers in the training data might not be outliers in the testing data.
#### Method 2:
We detect outlier and run regression simultaneously. For some of the labled data, the performance is significantly better, for some they are not. Due to the nature that some datasets will have outliers in the training acting as outliers as well in the testing data, and thus the accuracy is not so well in the real-world dataset if all data too far away from the median are removed.

Please see the detailed PDF of my approach linked:
