## The get_coeff()

`return sum(v for k, v in coeff_dict.items() if isinstance(k, Symbol) and str(k) == symbol_str)`

The get_coeff function has a single line which does a lot of things at the same time, here is a breakdown:
1. `for k, v in coeff_dict.items()`: iterates through every key-value pair in the dictionary coeff_dict. 
2. `if isinstance(k, Symbol)`: checks if the key **k** is of the instance Symbol or not.
3. `and str(k) == symbol_str`: checks if the string representation of **k** matches the symbol whose coefficient we want to find. The symbol_str is passed as a parameter when the function is called.
4. `sum(v ...)`: If the conditions in 2 **and** 3 get fulfilled, the value is added to the sum. 

The conditions given in 2 and 3 can only be matched if the symbol was created by the sympy or if you tried to access the value of the coefficient previously using `name_of_dict[key]`. In this case,
the dictionary would have a new key created of the same name and even type if your `key` was of the same type. But its value would be intialized to 0. So actual coefficient + 0 = actual coefficient. 

**Note**: If your code has some method or any line that adds another symbol of the same type and string name to the dictionary containing the symbol then and that key is mapped to a non zero value, then this method would fail as the sum would have the value of second non zero instance.  
