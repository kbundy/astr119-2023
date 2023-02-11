
# Demos: Session-09
Session 2023-02-09

## NumPy from SciPy
https://scipy.org

Numpy: 1) n-dimensional arrays, 2) Functions (broadcasting) on arrays, 3) More math (random numbers, Fourier transforms, linear algebra)

Follow along:
	import numpy as np  # If necessary conda install numpy
	
	# Make an ndarray from a list
	a = np.array([1,2,3,4])
	type(a)
	
	a.ndim  # This is an "instance" or attribute (not a function)
	a.size
	
	# 2D array
	b = np.array([[1,2,3,4], [5,6,7,8]])  # Notice number of square brackets
	b
	
	b.ndim
	b.size  # Total number of elements
	b.shape # rows x columns
	
	c = np.array([x**2 for x in range(10)])
	
Create an array of zeros, then fill it in later.  This is much faster than appending.

	d = np.zeros([2,4])
	d
	
	e = np.ones([6,2])
	e

Create an array with arange

	arr = np.arange(10, 100, 10)  # From 10 to 100 in steps of 10
	
	arr = np.arange(0.1, 0.9, 0.01)
	
Array access and slicing

	arr = np.arange(1,10)
	arr[2]
	arr[2] = 40  # Replace values
	
	arr[0:4]
	
	# With multiple dimensions
	a = np.array([np.arange(5), np.arange(5)])
	a.shape
	
	a[1,3]  # pick out an element
	
	a[1, 2:]  # pick out a slice
	
Random numbers and "broadcasting" (element-wise operations)

	a = np.random.random([3,5])
	
	b = np.ones([3,5])
	
	# broadcasting
	c = a+b
	np.sqrt(c)  # Not the same as the math module function
	
Functions can operate on arrays.  Sometime they are built-in to array objects.

	np.max(c)  # What is the max value?
	c.max()    # What is the max value?
	
	c.argmax()  # What index (slot) in the array has the maximum value?
	

**DO ARRAY EXERCISE**: Rework `lists_exercises_starter.py` to work with numpy arrays instead of lists

Boolean indexing, true/false

	a = np.arange(20)
	a
	alow = a < 8
	a[alow]
	
## Numpy saving arrays to file

	np.savetxt('filename.txt', arr)
	arr = np.loadtxt('filename.txt')
	
	# For larger files and compression
	np.save()
	np.savez()
	np.load()

----
## Integers and Floats
In ipython:

	x = 2
	y = 2.0
	type(x)
	type(y)
	
So, warning, this will fail: 

	N=100
	for n in range(100/2):
		print(n)
	
And just see what is: `type(100/2)` is `int`

Convert between types with `float(2)` and `int(2.0)`.  
What about `int(2.3)`?  
What about `int(2.9)`?  
And also to strings with `str(2.0)`  

## Stop at specified precision: `%` Modulus, `abs`, and Break

### Example of determining whether a number is even or odd.  
Use if/else  

`%` is the modulus operator (the remainder)

	3%2  # remainder is 1
	5%2  # remainder is 1
	6%2  # remainder is 0

### Check and `break`
Test achieved precision with built-in `abs()`
If we're done, we can break with special command `break` which breaks out of the loop

