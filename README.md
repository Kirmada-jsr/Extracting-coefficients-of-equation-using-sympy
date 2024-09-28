 # Extracting Coefficient Values Using two Methods.

This small project is a short note on how SymPy creates multiple instances of object which have the same name and type and in such cases it can be difficult to refer to a specific variable. 
It is specifically troublesome when an instance is created by sympy itself. Troubleshooting in this case can be a nightmare.

The problem we'll analyze is to create a plane object using sympy and extract the coefficients of the equation of the plane when wriiten in the form of ax + by + cz + d = 0. 

## Creating a plane and from it an equation

To create a plane we can use the `Plane()` from SymPy. Then using the `.equation()` method from sympy we can create the equation from this plane. Then calling the `as_coefficients_dict()` method on the equation object, we can get a `defaultdict` of class `int`. The initialization of defaultdict with `int` is the reason the whenever a new key is initialized without a value, the default value is set to zero.

Now, we cannot extract the coefficient directly from the dict because we don't have the object that has the same hash value as the actual key. So we have two ways:
1. We can collapse the coefficient values of the instances that have the same string representation as the variable who's coefficient we want to extract. In our case there would be only one key whose string representation would match to the variable we are looking for.
2. Another way to approach the problem is to duplicate the symbol object so that it has the same hash value as the key. Then using this duplicated symbol, we can access the values of the coefficients.

Both of these methods are given in the jupyter notebook attached with all the relevant information as markdown and comments. 
The for loop in the function for collapsing the values of coefficienst based on the string representation can be hard to understand and hence, an explanation of the segments of the line of code are given in get_coeff.md 
