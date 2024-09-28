# Collapsing-multiples-instances-in-sympy-using-hashes.
This small project is a short note on how SymPy creates multiple instances of object which have the same name and type and in such cases it can be difficult to refer to a specific variable. 
It is specifically troublesome when an instance is created by sympy itself. Troubleshooting in this case can be a nightmare.

The problem we'll analyze is to create a plane object using sympy and extract the coefficients of the equation of the plane when wriiten in the form of ax + by + cz + d = 0. 
