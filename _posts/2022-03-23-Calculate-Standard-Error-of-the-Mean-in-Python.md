2022-03-23 

# How to Calculate the Standard Error of the Mean in Python

The standard error of the mean is a way to measure how the spread out values are in a dataset.
<br>
It is calculated as:

### Standard error of the mean = s / √n

where:

s: sample standard deviation
<br>
n: sample size



## Two methods
I will explain two methods you can use to calculate the standard error of the mean for a dataset in Python.
Note that both methods produce the exact same results.

sem() function from the SciPy Stats library (https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.sem.html)
std() function from the NumPy library (https://numpy.org/doc/stable/reference/generated/numpy.std.html)


## Method 1: Use SciPy

The first way to calculate the standard error of the mean is to use the sem() function from the SciPy Stats library.

The following code shows how to use this function:


from scipy.stats import sem

#define dataset 
<br>
data = [3, 4, 4, 5, 7, 8, 12, 14, 14, 15, 17, 19, 22, 24, 24, 24, 25, 28, 28, 29]

#calculate standard error of the mean 
sem(data)

2.001447

The standard error of the mean turns out to be 2.001447.


## Method 2: Use NumPy

Another way to calculate the standard error of the mean for a dataset is to use the std() function from NumPy.

Note that we must specify ddof=1 in the argument for this function to calculate the sample standard deviation as opposed to the population standard deviation.

The following code shows how to do so:


import numpy as np

#define dataset
<br>
data = np.array([3, 4, 4, 5, 7, 8, 12, 14, 14, 15, 17, 19, 22, 24, 24, 24, 25, 28, 28, 29])

#calculate standard error of the mean 
<br>
np.std(data, ddof=1) / np.sqrt(np.size(data))

2.001447

Once again, the standard error of the mean turns out to be 2.001447.


## How to Interpret the Standard Error of the Mean

The standard error of the mean is simply a measure of how spread out values are around the mean. 
There are two things to keep in mind when interpreting the standard error of the mean:


1. The larger the standard error of the mean, the more spread out values are around the mean in a dataset.

To illustrate this, consider if we change the last value in the previous dataset to a much larger number:

from scipy.stats import sem

#define dataset 
data = [3, 4, 4, 5, 7, 8, 12, 14, 14, 15, 17, 19, 22, 24, 24, 24, 25, 28, 28, 150]

#calculate standard error of the mean 
sem(data)

7.171022

Notice how the standard error jumps from 2.001447 to 6.978265. This is an indication that the values in this dataset are more spread out around the mean compared to the previous dataset.

2. As the sample size increases, the standard error of the mean tends to decrease.

To illustrate this, consider the standard error of the mean for the following two datasets:

from scipy.stats import sem 

#define first dataset and find SEM
data1 = [1, 2, 3, 4, 5]
sem(data1)

0.7071068

#define second dataset and find SEM
data2 = [1, 2, 3, 4, 5, 1, 2, 3, 4, 5]
sem(data2)

0.471404

The second dataset is simply the first dataset repeated twice. Thus, the two datasets have the same mean but the second dataset has a larger sample size so it has a smaller standard error.

