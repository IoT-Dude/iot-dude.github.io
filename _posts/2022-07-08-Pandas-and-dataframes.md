20220708

# Dataframes and Pandas API

DataFrames are the central data structure in the pandas API. This post is not a comprehensive DataFrames tutorial - it's just a very quick introduction to the parts of Pandas and dataframes (<b>df</b>) required to do data analysis.

A DataFrame is similar to an in-memory spreadsheet. Like a spreadsheet:

A DataFrame stores data in cells.
A DataFrame has named columns (usually) and numbered rows.


## Import NumPy and pandas modules

Run the following code cell to import the NumPy and pandas modules.

<pre>
import numpy as np
import pandas as pd
</pre>



## Creating a DataFrame

The following code cell creates a simple DataFrame containing 10 cells organized as follows:

5 rows
2 columns, one named temperature and the other named activity

The following code cell instantiates a pd.DataFrame class to generate a DataFrame. The class takes two arguments:

The first argument provides the data to populate the 10 cells. The code cell calls np.array to generate the 5x2 NumPy array.
The second argument identifies the names of the two columns.

### Create and populate a 5x2 NumPy array.

<pre>my_data = np.array([[0, 3], [10, 7], [20, 9], [30, 14], [40, 15]])</pre>

​

### Create a Python list that holds the names of the two columns.

<pre>my_column_names = ['temperature', 'activity']</pre>

​

### Create a DataFrame.

<pre>my_dataframe = pd.DataFrame(data=my_data, columns=my_column_names)</pre>


### Print the entire DataFrame

<pre>print(my_dataframe)</pre>


temperature activity <br>
0            0         3<br>
1           10         7<br>
2           20         9<br>
3           30        14<br>
4           40        15<br>



<table>
    <tr>
	 <th>Row</th>
       	 <th>temperature</th>
      	  <th>activity</th>
   </tr>
   <tr>
	<td>0</td>
	<td>0</td>
	<td>3</td>
   </tr>
   <tr>
	<td>1</td>
    	<td>10</td>
    	<td>7</td>
    </tr>
    <tr>
	<td>2</td>
	<td>20</td>
	<td>9</td>
    </tr>
    <tr>
	<td>3</td>
    	<td>30</td>
    	<td>14</td>
    </tr>
    <tr>
	<td>4</td>
    	<td>40</td>
    	<td>15</td>
    </tr>
</table> 




## Adding a new column to a DataFrame

You may add a new column to an existing pandas DataFrame just by assigning values to a new column name. For example, the following code creates a third column named adjusted in my_dataframe:

### Create a new column named adjusted.

<pre>
my_dataframe["adjusted"] = my_dataframe["activity"] + 2
</pre>
​

### Print the entire DataFrame
<pre>
print(my_dataframe)
</pre>
   temperature  activity  adjusted<br>
0            0         3         5<br>
1           10         7         9<br>
2           20         9        11<br>
3           30        14        16<br>
4           40        15        17<br>







v1.4
