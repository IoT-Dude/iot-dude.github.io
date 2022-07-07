2022-07-04

# NumPy Intro
NumPy is a Python library for creating and manipulating vectors and matrices.
This  is not an exhaustive tutorial on NumPy, rather, just enough on how to use NumPy.


## Import NumPy module

Run the following code cell to import the NumPy module:

import numpy as np 



<br>
## Populate arrays with specific numbers

Call np.array to create a NumPy matrix with your own hand-picked values. For example, the following call to np.array creates an 8-element vector:

one_dimensional_array = np.array([1.2, 2.4, 3.5, 4.7, 6.1, 7.2, 8.3, 9.5])

print(one_dimensional_array)

[1.2 2.4 3.5 4.7 6.1 7.2 8.3 9.5]


You can also use np.array to create a two-dimensional matrix. To create a two-dimensional matrix, specify an extra layer of square brackets. For example, the following call creates a 3x2 matrix:

two_dimensional_array = np.array([[6, 5], [11, 7], [4, 8]])

print(two_dimensional_array)

[[ 6  5]
 [11  7]
 [ 4  8]]

To populate a matrix with all zeroes, call np.zeros. To populate a matrix with all ones, call np.ones.
Populate arrays with sequences of numbers

<br>
## You can populate an array with a sequence of numbers:

sequence_of_integers = np.arange(5, 12)

print(sequence_of_integers)

[ 5  6  7  8  9 10 11]

Notice that np.arange generates a sequence that includes the lower bound (5) but not the upper bound (12).
Populate arrays with random numbers

NumPy provides various functions to populate matrices with random numbers across certain ranges. For example, np.random.randint generates random integers between a low and high value. The following call populates a 6-element vector with random integers between 50 and 100.

random_integers_between_50_and_100 = np.random.randint(low=50, high=101, size=(6))

print(random_integers_between_50_and_100)

[54 99 80 93 99 77]

Note that the highest generated integer np.random.randint is one less than the high argument.

To create random floating-point values between 0.0 and 1.0, call np.random.random. For example:

random_floats_between_0_and_1 = np.random.random([6])

print(random_floats_between_0_and_1) 

[0.96096426 0.39609994 0.79568561 0.43593043 0.87265427 0.61238418]



## Mathematical Operations on NumPy Operands

If you want to add or subtract two vectors or matrices, linear algebra requires that the two operands have the same dimensions. Furthermore, if you want to multiply two vectors or matrices, linear algebra imposes strict rules on the dimensional compatibility of operands. Fortunately, NumPy uses a trick called broadcasting to virtually expand the smaller operand to dimensions compatible for linear algebra. For example, the following operation uses broadcasting to add 2.0 to the value of every item in the vector created in the previous code cell:

random_floats_between_2_and_3 = random_floats_between_0_and_1 + 2

print(random_floats_between_2_and_3)

[2.96096426 2.39609994 2.79568561 2.43593043 2.87265427 2.61238418]

The following operation also relies on broadcasting to multiply each cell in a vector by 3:

random_integers_between_150_and_300 = random_integers_between_50_and_100 * 3

print(random_integers_between_150_and_300)

[162 297 240 279 297 231]


## Task 1: Create a Linear Dataset

Your goal is to create a simple dataset consisting of a single feature and a label as follows:

Assign a sequence of integers from 6 to 20 (inclusive) to a NumPy array named feature.
Assign 15 values to a NumPy array named label such that:

label = (3)(feature) + 4

For example, the first value for label should be:

label = (3)(6) + 4 = 22

feature = np.arange(6, 21) # write your code here

print(feature)

# label = (3)(6) + 4 = 22  är (3*6) + 4

label = (3 * feature) + 4   # write your code here

print(label)

[ 6  7  8  9 10 11 12 13 14 15 16 17 18 19 20]
[22 25 28 31 34 37 40 43 46 49 52 55 58 61 64]


wwwwitle Double-click to see a possible solution to Task 1.

feature = np.arange(6, 21)

print(feature)

label = (feature * 3) + 4

print(label)


## Task 2: Add Some Noise to the Dataset

To make your dataset a little more realistic, insert a little random noise into each element of the label array you already created. To be more precise, modify each value assigned to label by adding a different random floating-point value between -2 and +2.

Don't rely on broadcasting. Instead, create a noise array having the same dimension as label.


## P other ways

noise = np.random.uniform(low=-2, high=2, size=(15))    # write your code here

print(noise)

label = label + noise    # write your code here

print(label)

[ 0.07522686  0.78460896  1.89837997 -0.45187456  0.66152759  0.38899877
 -1.58159291  1.75080164 -1.53598879 -0.84622127 -1.08731479 -0.12682767
 -0.76087933  0.08740774  0.72989164]
[19.7183993  27.49413257 26.75727466 29.78973762 37.0878221  32.90192633
 36.19104924 46.18095677 43.6453461  45.64727543 51.72552522 51.0961742
 57.7286994  63.34011848 66.588743  ]


wwww

​


noise = (np.random.random([15]) * 4) - 2

print(noise)

label = label + noise 

print(label)

[ 1.45685299  1.72357467 -1.87316479  0.21432152  0.83833136 -1.1253276
  1.03632451 -0.75470276 -1.43310608 -1.53560591  0.72934407 -0.84020332
  0.87876512 -1.41706242 -0.06717227]
[21.17525229 29.21770724 24.88410986 30.00405914 37.92615346 31.77659873
 37.22737376 45.42625401 42.21224002 44.11166952 52.4548693  50.25597088
 58.60746453 61.92305606 66.52157074]

​

NumPy is quite nifty!


v1.21
