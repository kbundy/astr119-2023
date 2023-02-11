
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

____

# IPython and jupyter notebooks

From the command line: `jupyter notebook`.  
To install jupyter: `conda install -c anaconda jupyter`

A new way to develop a kind of scientific logbook, with embedded scripted code.  Works within a web browser, so it's easy to make portable and share.

But beware, it is good for development, but problematic for production.  Easy to get lost on when/where variables are defined.  Easy to lose saved changes.  Easy to make things that cannot be reproduced later.  So, this of `jupyter` like `iPython`, a useful tool to use with your standard coding setup, especially when you want to add comments/notes to code and figures.

1. Show code within cells, execute one at a time..
2. Multiple cells, execute all

To auto-update based on file changes:

	%load_ext autoreload
	%autoreload 2

# Plotting

Please make sure you have `matplotlib` installed.  Try `conda install matplotlib`

## matplotlib in jupyter

From IPython, life is easier if you initiate with `%matplotlib`.  
In a jupyter notebook, initiate with `%matplotlib inline`



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

