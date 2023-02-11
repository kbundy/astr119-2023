
# Demos: Session-10
Session 2023-02-14
____

# `jupyter` notebooks

From the command line: `jupyter notebook`.  
To install jupyter: `conda install -c anaconda jupyter`

A new way to develop a kind of scientific logbook, with embedded scripted code.  Works within a web browser, so it's easy to make portable and share.

But beware, it is good for development, but problematic for production.  Easy to get lost on when/where variables are defined.  Easy to lose saved changes.  Easy to make things that cannot be reproduced later.  So, this of `jupyter` like `iPython`, a useful tool to use with your standard coding setup, especially when you want to add comments/notes to code and figures.

1. Show code within cells, `shift-enter` execute one cell at a time..
2. Multiple cells, execute all

To auto-update based on file changes:

	%load_ext autoreload
	%autoreload 2

# Two more things on numpy

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
# Plotting

Please make sure you have `matplotlib` installed.  Try `conda install matplotlib`



## matplotlib in jupyter

Easiest interface to plotting tools: `import matplotlib.pyplot as plt`

From IPython, life is easier if you initiate with `%matplotlib`.  
In a jupyter notebook, initiate with `%matplotlib inline`

### Basic plot example

	x = np.arange(0, 2*np.pi, 2*np.pi/10)
	
	# Start location, stopping location (included), and number of elements
	x = np.linspace(0, 2*np.pi, 10)
	
	y = np.cos(x)
	z = np.sin(x)
	
	plt.plot(x,y)
	plt.plot(x,z)  # Overplots the on the same figure
	plt.show()
	
Now let's indicate the data points, with different symbols (markers) for each curve

	plt.plot(x, y, marker='+')
	plt.plot(x, z, marker='o')
	
Then increase the number of data points; then we can remove the markers and make more of a smooth curve.

Labeling the axes

	plt.xlabel('angle [rad]')
	plt.ylabel('value')
	
Adding labels to the data

	plt.plot(x, y, marker='+', label='cosine')
	plt.plot(x, z, marker='o', label='sine')
	plt.legend()
	
### Plot customizations

Linestyle

	plt.plot(x, y, marker='+', label='cosine', linestyle='-')
	plt.plot(x, y, marker='o', label='sine', linestyle='--')
	
Line thickness

	plt.plot(x, y, marker='+', label='cosine', linestyle='-', linewidth=2)
	plt.plot(x, y, marker='o', label='sine', linestyle='--', linewidth=2)

Change font size

	plt.xlabel('angle [rad]', fontsize=14)
	plt.ylabel('angle [rad]', fontsize=14)
	plt.legend(fontsize=15)
	
Change limits

	plt.xlim(0, 2*np.pi)  # This should really be a tuple
	plt.ylim((-1,1))      # Like this...
	
Change figure size.  Before anyother functions, we need to specifically define the Figure window by adding a call to `plt.figure`:

	plt.figure(figsize=(8,6))

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

