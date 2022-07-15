
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

   
Row #2:<br>
   temperature  activity  adjusted<br>
2           20         9        11 <br>

   
Rows #1, #2, and #3:<br>
   temperature  activity  adjusted<br>
1           10         7         9<br>
2           20         9        11<br>
3           30        14        16 <br>

   
Column 'temperature':<br>
0     0<br>
1    10<br>
2    20<br>
3    30<br>
4    40<br>
Name: temperature, dtype: int64
</samp>

wwwwww


## How to create a DataFrame

Do the following:

Create an 3x4 (3 rows x 4 columns) pandas DataFrame in which the columns are named Eleanor, Chidi, Tahani, and Jason.
Populate each of the 12 cells in the DataFrame with a random integer between 0 and 100.


Output the following:
the entire DataFrame
the value in the cell of row #1 of the Eleanor column
Create a fifth column named Janet, which is populated with the row-by-row sums of Tahani and Jason.

To complete this task, it helps to know the NumPy basics covered in the NumPy UltraQuick Tutorial.


### A 3x4 NumPy array.

#my_data = np.array([[0, 3], [10, 7], [20, 9], [30, 14]])

my_data = np.random.randint(low=0, high=101, size=(3, 4))

​

### Create a Python list that holds the names of the two columns.

my_column_names = ['Eleanor' , 'Chidi', 'Tahani', 'Jason']

​

### Create a DataFrame.

df = pd.DataFrame(data=my_data, columns=my_column_names)

​

### Print the entire DataFrame

print(df)

   Eleanor  Chidi  Tahani  Jason
0       91     25      62     86
1       96     36      83     34
2       32     29      72     17

print(df.iloc[[1]]['Eleanor'])

1    96
Name: Eleanor, dtype: int64

print(df['Eleanor'][1])

96

### Create a fifth column named Janet, which is populated with the row-by-row sums of Tahani and Jason.

df['Janet'] = df['Tahani'] + df['Jason']

print(df) 

   Eleanor  Chidi  Tahani  Jason  Janet
0       91     25      62     86    148
1       96     36      83     34    117
2       32     29      72     17     89

#@title Double-click for a solution to Task 1.

​

### Create a Python list that holds the names of the four columns.

my_column_names = ['Eleanor', 'Chidi', 'Tahani', 'Jason']

​

### Create a 3x4 numpy array, each cell populated with a random integer.

my_data = np.random.randint(low=0, high=101, size=(3, 4))

​

### Create a DataFrame.

df = pd.DataFrame(data=my_data, columns=my_column_names)

​

### Print the entire DataFrame

print(df)

​

### Print the value in row #1 of the Eleanor column.

print("\nSecond row of the Eleanor column: %d\n" % df['Eleanor'][1])

​

### Create a column named Janet whose contents are the sum

### of two other columns.

df['Janet'] = df['Tahani'] + df['Jason']

​

### Print the enhanced DataFrame

print(df)

   Eleanor  Chidi  Tahani  Jason
0       74     58      20     95
1       65     70      52     61
2      100     41      69      8

Second row of the Eleanor column: 65

   Eleanor  Chidi  Tahani  Jason  Janet
0       74     58      20     95    115
1       65     70      52     61    113
2      100     41      69      8     77






<br>
v1.4
