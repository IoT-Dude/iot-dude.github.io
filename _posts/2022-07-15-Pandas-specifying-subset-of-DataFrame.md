
# Specifying a subset of a DataFrame

Pandas provide multiples ways to isolate specific rows, columns, slices or cells in a DataFrame.

print("Rows #0, #1, and #2:")

print(my_dataframe.head(3), '\n')

​

print("Row #2:")

print(my_dataframe.iloc[[2]], '\n')

​

print("Rows #1, #2, and #3:")

print(my_dataframe[1:4], '\n')

​

print("Column 'temperature':")

print(my_dataframe['temperature'])

Rows #0, #1, and #2:
   temperature  activity  adjusted
0            0         3         5
1           10         7         9
2           20         9        11 

Row #2:
   temperature  activity  adjusted
2           20         9        11 

Rows #1, #2, and #3:
   temperature  activity  adjusted
1           10         7         9
2           20         9        11
3           30        14        16 

Column 'temperature':
0     0
1    10
2    20
3    30
4    40
Name: temperature, dtype: int64


v1.0
