
# Demos: Session-14
Session 2023-02-28

## Review of data handling and `pandas`

### Interrogating data tables with pandas in ipython...

	import numpy as np
	import pandas as pd
	import import matplotlib.pyplot as plt
	% matplotlib
	
	# Load in exoplanets.csv.
	exodf = pd.read_csv('exoplanets.csv')
	
	# Plot histogram of semi-major axis
	plt.figure()
	exodf['A'].plot(kind='hist')  # Not very useful, range is too big
	
	# Plot the series of points
	plt.clf()  # Clear the figure
	exodf['A'].plot(marker='.')  # Darn, we have connecting lines
	
	plt.clf()
	exodf['A'].plot(marker='.', lw=0) # Remove the connecting lines
	# This plot shows where the measurements are in broad terms
	
	# Now plot a more revealing historgram by restricting the range
	plt.clf()
	exodf['A'][exodf['A'] < 10].plot(kind='hist')
	
	#  Hmm.. zoom in by restricting the range further
	plt.clf()
	exodf['A'][exodf['A'] < 4].plot(kind='hist')
	
	#  More bins and zooming in further
	plt.clf()
	exodf['A'][exodf['A'] < 2].plot(kind='hist', bins=20)  # Now we see something interesting
	
	# describe() provides a statistical summary of a data series
	exodf['A'].describe()
	
### An easy way to search through column names
`exodf.filter(regex='MSIN')`

### Multi-conditional indexes

	indx = exodf['A'] < 0.5
	indx       # Series of True, False
	len(indx)  # This is a Series with length equal to the length of the dataframe

	exodf[indx] # Just the ones with True
	len(exodf[indx]) 
	indx.sum()  # Fast way to count the number of True values
	
	# Combine multiple conditions
	indx2 = (exodf['A'] < 0.5) & (exodf['MSINI'] < 1)
	indx2.sum()
	exoCloseSmalldf = exodf[indx2]


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

