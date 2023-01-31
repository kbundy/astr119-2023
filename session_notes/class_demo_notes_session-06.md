
# Demos: Session-06

## Optional "Run like a script or utility"

`__name__` is a special variable that gives the name of an imported module

	import function1
	print(function1.__name__)

	if __name__ == '__main__':
		aa = awesomeness(5)
		bb = awesomeness(aa)
		print(f'My function gives the answer: {bb:0.2}')

## Passing command-line arguments

	import sys
	a = float(sys.argv[1])
	b = float(sys.argv[2])

## Also, note you can access variables from imported modules

If you define a variable with function1.py and then `import function1`, the variable is accessible via

	var = function1.variable

----
## Loops 

Indexed for-loop, we will use the built-in function `range()`.  The variable then becomes a "loop index".
Most simply, `range(5)` will return an index that goes from 0 to 4, and increments by 1  
More generally, `range(start, stop-1, step=1)`

	for i in range(5):
		print(i)
		
	for i in range(2,6):
		print(i)
		
	for i in range(2,6,2):
		print(i)
		
	for i in range(2,6,0.5):
		print(i)

Last one fails, because the step size must be an integer

Example of a sum (show that it fails because `runningSum` is not originally defined)

	# Sum of all numbers from n=1-100
	#   We know that the sum should be: Sum = N*(N+1)/2
	N = 100
	for n in range(1,N+1):
		runningSum = runningSum + n
		
	print(runningSum)
	print(N*(N+1)/2)

----
## Lists

Using ipython.

List of strings

	planet_1 = 'WASP-39b'
	planet_2 = '51-Peg'
	planet_3 = 'Jupiter'
	
	planets = ['WASP-39b', '51-Peg', 'Jupiter', 'HD249508']
	
	type(planets)
	
Lists are "sequence containers," which means the order is impoortant and preserved.

We can access contents with an "index"

	print(planets[0])
	
Zero-indexed in python means the first element is zero.

	ivariable = 1
	print(f'The i-th planet in the list is {planets[ivariable]}')
	
	i = 0
	print(f'The {i}-th planet in the list is {planets[i]}')
	
The elements in the list can be of mixed type, but don't do this...
	
	planetStuff = [ 3.8e26, 'units: Joules, Watts, Kelvin, meters, kg', planets]
	
	# Note different types within this list
	type(planetStuff[0])
	type(planetStuff[1])
	
	# Indexing lists within lists
	planetStuff[2]
	planetStuff[2][1]
	
Typically, we don't do this.  Better organizational principle is to keep list elements of the same type.

### Lists and For-Loops

How many elements are in the container?

	len(planets)
	
Do something with the elements in the list using a for-loop:

	for k in range(len(planets)):
		print(f'Planet number {k+1} is {planets[k]}')

Even simpler, in python, you can sometimes leave out the index if you're just looping through the container.

	for thisPlanet in planets:
		print(f'Right now my for-loop is working on planet, {thisPlanet}')
		
### List Comprehension

Kinda unique to python.  

	radiusJupiterUnits = [2, 3, 1.5, 2.2]
	diameterJupiterUnits = [radius*2 for radius in radiusJupiterUnits]

### List Slicing and manipulation

Basic slicing.  Note that the slice [0:i] does not include [i].  It slices from [0] to [i-1]

	aa = [0, 1, 2, 3, 4, 5, 6, 7, 8]
	aa[0:4]

And what is the final element?  Two ways:

	aa[7]  # If we know there is a 7th place in the index
	
	aa[-1] # Useful when we don't know the number of elements, and want to check the end
	
	aa[-3]
	
List concatenation and repitition:

	bb = aa + aa
	
	aa*2
	
Note that it does not multiply the list by x2.  (We need numpy arrays for this)

### List methods

Methods are 

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

