Video Link: https://youtu.be/kKWsJGKcMvo



These notes summarize the techniques for encoding numerical data through Discretization (Binning) and Binarization as discussed in the sources.
1. Discretization (Binning)
Discretization is the process of transforming continuous numerical variables into discrete variables by creating a set of continuous intervals called bins
.
Why Use Binning?
Handling Outliers: Outliers can be grouped into the first or last bin, treating them similarly to other values in that range and reducing their extreme impact
.
Improving Data Spread: It can help make the distribution of data more uniform or spread out
.
Simplification: In some cases, representing data as categories (e.g., "1M+ downloads" vs "10k+ downloads") provides a better representation for machine learning models than raw numbers
.
Types of Binning
The sources categorize binning into three main types:
Unsupervised Binning:
Equal Width (Uniform) Binning: The entire range of data is divided into bins of equal size
. The width is calculated as: (Max - Min) / Number of Bins
.
Equal Frequency (Quantile) Binning: Each bin contains approximately the same percentage (e.g., 10%) of the total population
. This is often the default strategy because it improves the value spread and handles outliers well
.
K-Means Binning: This uses the K-Means clustering algorithm to group data points into clusters
. It is particularly useful when the data naturally forms distinct groups or clusters
.
Supervised Binning:
Decision Tree Binning: Uses decision trees to create bins (not covered in detail in the provided text)
.
Custom Binning:
Users create bins based on domain knowledge
. For example, dividing age into categories like "Child," "Adult," and "Retired"
. This is typically done using libraries like Pandas rather than Scikit-Learn
.
Implementation in Scikit-Learn
The KBinsDiscretizer class is used for these techniques
. Key parameters include:
n_bins: The number of intervals to create
.
strategy: 'uniform', 'quantile', or 'kmeans'
.
encode: 'ordinal' (to keep the order) or 'onehot'
.

--------------------------------------------------------------------------------
2. Binarization
Binarization is a special case of discretization where numerical values are converted into binary values (0 or 1) based on a specific threshold
.
How it works: Any value below or equal to a set threshold becomes 0, and any value above the threshold becomes 1
.
Common Use Case: Image Processing, such as converting a colour or greyscale image into black and white by setting a pixel threshold
.
Implementation: Scikit-Learn provides the Binarizer class
. It requires a threshold parameter to determine the cut-off point
.
