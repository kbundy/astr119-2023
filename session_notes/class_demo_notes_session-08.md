
# Demos: Session-08
Session 2023-02-07

## More on Lists

### List Comprehension

Making a new list.  Kinda unique to python.  The syntax sounds like the way Yoda speaks: "Fear, anger, agression..."

	radiusJupiterUnits = [2, 3, 1.5, 2.2]
	diameterJupiterUnits = [radius*2 for radius in radiusJupiterUnits]
	
For operations like this, we will mostly be using numpy arrays (coming soon).

### List Slicing and manipulation

Basic slicing.  Note that the slice [0:i] does not include [i].  It slices from [0] to [i-1]

	aa = [0, 1, 2, 3, 4, 5, 6, 7, 8]
	aa[0:4]

And what is the final element?  Two ways:

	aa[7]  # If we know there is a 7th place in the index
	
	aa[-1] # Useful when we don't know the number of elements, and want to check the end
	
	aa[-3]
	
You can slice through strings:

	planets[1][2:5]
	
List concatenation and repitition:

	bb = aa + aa
	
	aa*2
	
Note that it does not multiply the list by x2.  (We need numpy arrays for this)

### List methods

Methods are built-in functions that belong to a particular variable.  Type `variable.` then hit tab to see options.

	planets.sort()  # Sorts the list "in-place"
	platets.pop()   # Removes the last item
	planets.append('mercury')  # Add a new item to the list
	planets.remove('jupiter')  # Remove an item from the list
	planets.count('mercury')  # Number of times a list item appears
	planets.index('jupiter')  # Returns the first list index that matches the supplied value
	
The `copy` method.  A new assignment points to a new variable to the same object.

	planets2 = planets
	planets2.pop()  # Removes the last item 
	planets  # Note that the last item is also removed
	
	planets2 = planets.copy()
	
Tuples are like lists but with curved (parantheses) brackets.  They are immutable.  They are more efficient (faster) to work with and provide safety.

Creating a new list by appending vs. list comprehension

	aa = []
	for i in range(10):
		aa.append(i**2 + 5*i)
		
	bb = [(i**2 + 5*i) for i in range(10)]
	
**DO LIST EXERCISE**: Find `planet_vitals.py` and `lists_exercises_starter.py` in Slack #class-materials

----
## NumPy from SciPy
https://scipy.org

Numpy: 1) n-dimensional arrays, 2) Functions (broadcasting) on arrays, 3) More math (random numbers, Fourier transforms, linear algebra)

Follow along:
	import numpy as np  # If necessary conda install numpy
	
	# Make an ndarray from a list
	a = np.array([1,2,3,4])
	type(a)
	
	a.ndim  # This is an "instance" or property (not a function)
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
	
	e = 

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

