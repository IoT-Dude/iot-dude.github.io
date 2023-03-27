# sci-kit learn and SimpleImputer() function

Often while doing data analysis we encounter some columns or rows denoted as “nan”. For dealing with such issues we replace the nan values with average of the column , and sometime with most frequent word.

For all those task we have a function SimpleImput in sklearn.



### sklearn.impute.SimpleImputer

class sklearn.impute.SimpleImputer(*, missing_values=nan, strategy='mean', fill_value=None, verbose='deprecated', copy=True, add_indicator=False, keep_empty_features=False)[source]

**    Univariate imputer for completing missing values with simple strategies.

**    Replace missing values using a descriptive statistic (e.g. mean, median, or most frequent) along each column, or using a constant value.

[Read more in the User Guide](https://scikit-learn.org/stable/modules/impute.html#impute)


What is the use of SimpleImputer?
Univariate imputer for completing missing values with simple strategies. Replace missing values using a descriptive statistic (e.g. mean, median, or most frequent) along each column, or using a constant value.


v1.0
