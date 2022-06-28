2022-06-23

# Python slicing

python
<br>
slice
<br>
sequence


The syntax is:

a[start:stop]  # items start through stop-1
<br>
a[start:]      # items start through the rest of the array
<br>
a[:stop]       # items from the beginning through stop-1
<br>
a[:]           # a copy of the whole array


There is also the step value, which can be used with any of the above:

a[start:stop:step] # start through not past stop, by step

<br>
The key point to remember is that the :stop value represents the first value that is not in the selected slice.
So the difference between stop and start is the number of elements selected (if step is 1, the default).
<br>
<br>
The other feature is that start or stop may be a negative number, which means it counts from the end of the array instead of the beginning. So:

a[-1]    # last item in the array
<br>
a[-2:]   # last two items in the array
<br>
a[:-2]   # everything except the last two items

Similarly, step may be a negative number:

a[::-1]    # all items in the array, reversed
<br>
a[1::-1]   # the first two items, reversed
<br>
a[:-3:-1]  # the last two items, reversed
<br>
a[-3::-1]  # everything except the last two items, reversed


Python is kind to the programmer if there are fewer items than you ask for.
<br>
If you ask for a[:-2] and a only contains one element, you get an empty list instead of an error. Sometimes you would prefer the error, so you have to be aware that this may happen.

<br>
Relationship with the slice object

A slice object can represent a slicing operation:

a[start:stop:step]
<br>
It is equivalent to:

a[slice(start, stop, step)]


Slice objects also behave slightly differently depending on the number of arguments, similarly to range(). Both slice(stop) and slice(start, stop[, step]) are supported.
To skip specifying a given argument, one might use None, so that e.g. a[start:] is equivalent to a[slice(start, None)] or a[::-1] is equivalent to a[slice(None, None, -1)].

While the :-based notation is very helpful for simple slicing, the explicit use of slice() objects simplifies the programmatic generation of slicing.


Examples and conclusion

The slice() function returns a slice object.
A slice object is used to specify how to slice a sequence. You can specify where to start the slicing, and where to end.
You can also specify the step, which allows you to e.g. slice only every other item.

Example 1.

Get the characters from position 2 to position 5 (not included):
<br>
b = "Hello, World!"
<br>
print(b[2:5])


Example 2.

Create a tuple and a slice object. Use the slice object to get only the two first items of the tuple:
<br>
a = ("a", "b", "c", "d", "e", "f", "g", "h")
<br>
x = slice(2)
<br>
print(a[x])
