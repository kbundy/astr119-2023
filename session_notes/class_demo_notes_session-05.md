# -------------------------
# Demos: Session-04
# -------------------------


# -----------------------------
# -- Demos lines for input from terminal and import modules --
name = input('What is your name? ')

# Notice it's a string and we can play string tricks
print(name*6)

# Let's try a number
# starLuminosityInSolarUnits = input('Luminosity of the star (in solar units) = ')

starLuminosityInSolarUnits = float(input('Luminosity of the star (in solar units) = '))

L_sun = 3.8e26 # Watts (J/s)
starLuminosityInWatts = starLuminosityInSolarUnits * L_sun

# This should fail (string conversion)
print(starLuminosityInWatts)


starLuminosityInSolarUnits = float(input('Luminosity of the star (in solar units) = '))

# print(starLuminosityInWatts)

print(f'The L is: {starLuminosityInWatts:0.2} Watts')



# -- Demos lines for import --
# there are many modules, both built-in and Anaconda, they can be "installed" and then imported
# Including your own!

# Use ipython
import math
math.?
math.pi

import math as ma
ma.pi

# You could do:
pi = math.pi

# how many digits?
print(f'{pi:0.200}')

# But this is better
from math import pi
pi


# And even
from math import pi as piTheNumberNotTheDessert

# This is not just a number, it's got other stuff "under the hood" -- it's an object
help(piTheNumberNotTheDessert)

from math import sqrt



# -----------------------------
# -- Functions --

# make a new test file demoblocks.py
a = 5
b = -2
x = 1.2

y = sqrt(a*x**2 + b*x)

print(f'My function returns {y}')


# need to import sqrt

# turn into a function with f(x)
#    Indent with tab or command+] and de-indent with command+[
def awesomeness():
	a = 5
	b = -2
	x = 1.2

	y = sqrt(a*x**2 + b*x)	
	print(f'My function returns {y}')

# import and call from a new script

# show that you need a return statement
def awesomeness(x):

# print inside the function or outside

# add a second input variable with a default value (a = 5)
def awesomeness(x, a=5):



# -----------------------------
# IPYTHON: auto Reload edited files
# -----------------------------
# (base) monolith:~:> ipython profile create
# Open ~/.ipython/profile_default/ipython_config.py and append
# c.InteractiveShellApp.extensions = ['autoreload']     
# c.InteractiveShellApp.exec_lines = ['%autoreload 2']




# -----------------------------
# -- loops --
for i in [0,1,2,3]:
	print(i)

for i in [0,1,2,3]:
	print(i*2)

# The brackets mean a "list" we'll talk about thie more later
for i in [0,1,'hello',3]:
	print(i*2)


# -----------------------------
# -- if / else --
aa = 2
if aa > 3:
	print('it is bigger')
else:
	print('nope, smaller')




