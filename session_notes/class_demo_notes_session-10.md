
# Demos: Session-10
Session 2023-02-14
# Tow more things on numpy

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

