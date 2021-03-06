
# Specifying a subset of a DataFrame

Pandas provide multiples ways to isolate specific rows, columns, slices or cells in a DataFrame.

<pre>
print("Rows #0, #1, and #2:")
print(my_dataframe.head(3), '\n')

print("Row #2:")
print(my_dataframe.iloc[[2]], '\n')

print("Rows #1, #2, and #3:")
print(my_dataframe[1:4], '\n')

print("Column 'temperature':")
print(my_dataframe['temperature'])
</pre>

<samp>
Rows #0, #1, and #2:<br>
   temperature  activity  adjusted<br>
0            0         3         5<br>
1           10         7         9<br>
2           20         9        11<br> 
</samp>
   
<samp>   
Row #2:<br>
   temperature  activity  adjusted<br>
2           20         9        11 <br>
</samp>
   
<samp>   
Rows #1, #2, and #3:<br>
   temperature  activity  adjusted<br>
1           10         7         9<br>
2           20         9        11<br>
3           30        14        16 <br>
</samp>
   
<samp>   
Column 'temperature':<br>
0     0<br>
1    10<br>
2    20<br>
3    30<br>
4    40<br>
Name: temperature, dtype: int64
</samp>



## How to create a DataFrame

Do the following:

Create an 3x4 (3 rows x 4 columns) pandas DataFrame in which the columns are named Elin, Cybil, Tore, and Krille.
<br>
Populate each of the 12 cells in the DataFrame with a random integer between 0 and 100.


Output must be the following:
<br>
The entire DataFrame
<br>
The value in the cell of row #1 of the Elin column
<br>
Create a fifth column named Jane, which is populated with the row-by-row sums of Tore and Krille.


### A 3x4 NumPy array.

<pre>
my_data = np.array([[0, 3], [10, 7], [20, 9], [30, 14]])
my_data = np.random.randint(low=0, high=101, size=(3, 4))
</pre>

### Create a Python list that holds the names of the two columns.

<pre>
my_column_names = ['Elin', 'Cybil', 'Tore', 'Krille']
</pre>

### Create a DataFrame.
<pre>
df = pd.DataFrame(data=my_data, columns=my_column_names)
</pre>

### Print the entire DataFrame
<pre>
print(df)
</pre>
<samp>
   Elin  Cybil  Tore  Krille<br>
0       91     25      62     86<br>
1       96     36      83     34<br>
2       32     29      72     17
</samp>
  
<pre>
print(df.iloc[[1]]['Elin'])
</pre>
<samp>
1    96
Name: Elin, dtype: int64
</samp>

<pre>
print(df['Elin'][1])
</pre>

<samp>
96
</samp>


### Create a fifth column named Jane, which is populated with the row-by-row sums of Tore and Krille.

<pre>
df['Jane'] = df['Tore'] + df['Krille']
print(df) 
</pre>

<samp>
   Elin  Cybil  Tore  Krille  Jane<br>
0       91     25      62     86    148<br>
1       96     36      83     34    117<br>
2       32     29      72     17     89
</samp>


### Create a Python list that holds the names of the four columns.
<pre>
my_column_names = ['Elin', 'Cybil', 'Tore', 'Krille']
</pre>

### Create a 3x4 numpy array, each cell populated with a random integer.
<pre>
my_data = np.random.randint(low=0, high=101, size=(3, 4))
</pre>

### Create a DataFrame.
<pre>
df = pd.DataFrame(data=my_data, columns=my_column_names)
</pre>

### Print the entire DataFrame
<pre>
print(df)
</pre>

### Print the value in row #1 of the Elin column.
/pre>
print("\nSecond row of the Elin column: %d\n" % df['Elin'][1])
</pre>

### Create a column named Jane whose contents are the sum of two other columns.
<pre>
df['Jane'] = df['Tore'] + df['Krille']
</pre>


### Print the enhanced DataFrame
<pre>
print(df)
</pre>

<samp>
   Elin  Cybil  Tore  Krille<br>
0       74     58      20     95<br>
1       65     70      52     61<br>
2      100     41      69      8<br>
<br>
Second row of the Elin column: 65<br>
<br>
   Elin  Cybil  Tore  Krille  Jane<br>
0       74     58      20     95    115<br>
1       65     70      52     61    113<br>
2      100     41      69      8     77<br>
</samp>




<br>
<br>
v1.7
