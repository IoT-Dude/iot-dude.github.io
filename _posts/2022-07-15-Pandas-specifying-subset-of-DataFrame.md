
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

v1.2
