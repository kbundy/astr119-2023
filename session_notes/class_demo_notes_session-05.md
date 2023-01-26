
# Demos: Session-05

## IPYTHON: auto Reload edited files

	(base) monolith:~:> ipython profile create
	Open ~/.ipython/profile_default/ipython_config.py and append
	c.InteractiveShellApp.extensions = ['autoreload']     
	c.InteractiveShellApp.exec_lines = ['%autoreload 2']

- Ideally, we do this from the command line
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
## Loops 
	for item in [0,1,2,3]:
		print(item)

	for item in [0,1,2,3]:
		print(item*2)

The brackets mean a "list" we'll talk about this more later  

	for item in [0,1,'hello',3]:
		print(item*2)

Indexed for-loop, we will use the built-in function `range()`
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

Example of a sum:

	# Sum of all numbers from n=1-100
	N = 100
	for n in range(1,N+1):
		runningSum = runningSum + n



----

