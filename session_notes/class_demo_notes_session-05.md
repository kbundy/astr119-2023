
# Demos: Session-05

## IPYTHON: auto Reload edited files

	(base) monolith:~:> ipython profile create
	Open ~/.ipython/profile_default/ipython_config.py and append
	c.InteractiveShellApp.extensions = ['autoreload']     
	c.InteractiveShellApp.exec_lines = ['%autoreload 2']

## Functions
### Docstrings
- Add a dosctring to `function1.py`
- Open ipython, `from function1 import awesomeness`
- `help(awesomeness)` and `awesomeness?` 

Show that the docstring updates after we save the file, `function1.py`

### Multiple parameters
`def awesomeness(x, a=5):`

- The order matters if we don't label the input variable
- Order doesn't matter if we provide all labels

## loops 
	for i in [0,1,2,3]:
		print(i)

	for i in [0,1,2,3]:
		print(i*2)

The brackets mean a "list" we'll talk about thie more later  

	for item in [0,1,'hello',3]:
		print(item*2)


## if / else
	aa = 2
	if aa > 3:
		print('it is bigger')
	else:
		print('nope, smaller')




