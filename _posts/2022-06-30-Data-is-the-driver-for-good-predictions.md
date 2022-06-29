2022-06-30

# Data is the driver for good predictions

To make good predictions, you need data that contains features with predictive power.

The data should have the following characteristics:

### Abundant
The more relevant and useful examples in your dataset, the better your model will be.

### Consistent and reliable
Having data that is consistently and reliably collected will produce a better model. For example, an weather model will benefit from data gathered over many years from the same reliable instruments.

### Trusted
Understand where your data will come from. Will the data be from trusted sources you control, like logs from your product, or will it be from sources you don't have much insight into, like the output from another system?

### Available
Make sure all inputs are available at prediction time in the correct format. If it will be difficult to obtain certain feature values at prediction time, omit those features from your datasets.

### Correct
In large datasets it is inevitable that some labels will have incorrect values, but if more than a small percentage of labels are incorrect, the model will produce poor predictions.

### Representative
The datasets should be as representative of the real world as possible. In other words, the datasets should accurately reflect the events, user behaviors, and/or the phenomena of the real world being modeled.
Training on unrepresentative datasets can cause poor performance when the model is asked to make real-world predictions.

If you can not get the data you need in the required format, your model will make poor predictions.
