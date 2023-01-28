
# Demos: Session-05

## IPYTHON: auto Reload edited files

Run 2 commands every time you start ipython:

	%load_ext autoreload
	%autoreload 2

Or (better), add to a environmental profile variable

	(base) monolith:~:> ipython profile create
	Open ~/.ipython/profile_default/ipython_config.py and append
	c.InteractiveShellApp.extensions = ['autoreload']     
	c.InteractiveShellApp.exec_lines = ['%autoreload 2']

- Ideally, we find and edit the profile from the command line (it's a hidden file)
- Otherwise, we have to know that on a Mac, to see hidden files in an open-file dialog, we need `shift`+`command`+`dot`

## Functions
### Docstrings
- Add a dosctring to `function1.py`
- Open ipython, `from function1 import awesomeness`
- `help(awesomeness)` and `awesomeness?` 

Show that the docstring updates after we save the file, `function1.py`

### Multiple parameters
`def awesomeness(x, a=5):`

- You don't have to supply an input for `a` if you don't want to (defaults to 5)
- The order matters if we don't label the input variable
- Order doesn't matter if we provide all labels


## if / else
Add an if/else statement to `testFunctionCall.py`  
Example  

	aa = 2
	if aa > 3:
		print('it is really awesome')

	else:
		print('not awesome enough')


----
## Loops 
	for item in [0,1,2,3]:
		print(item)

	for item in [0,1,2,3]:
		print(item*2)

The brackets mean a "list" we'll talk about this more later  

	for item in [0,1,'hello',3]:
		print(item*2)

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
# For Next time...

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

## Break loop at specified precision: `%` Modulus, `abs`, and Break

### Example of determining whether a number is even or odd.  
Use if/else  

`%` is the modulus operator (the remainder)

	3%2  # remainder is 1
	5%2  # remainder is 1
	6%2  # remainder is 0

### Check and `break`
Test achieved precision with built-in `abs()`
If we're done, we can break with special command `break` which breaks out of the loop

