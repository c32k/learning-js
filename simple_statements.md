# Simple Statements
Statements in JavaScript execute something, whether it is defining a variable, calling a function, or performing operations. This is one of the longest documents as it defines basic statements in JavaScript. not all statements are defined as there is much more to cover, but these are the most commonly used ones.

## Defining Variables
In JavaScript, there are many ways to create a variable.
1. Assigning to an undeclared variable (not recommended)
	`var_name = value`
	- This is a bad way of creating a variable in JavaScript as it throws an error in strict mode and makes `var_name` an accidental global variable
2. Regular ES6 Declaration
	`let var_name = value;`
	- This is the standard method for defining variables as implemented in ES6 (EcmaScript 6). A semicolon is optional only in some cases, and is often recommended.
3. `var` declaration
	`var var_name = value;`
	- This method uses the old `var` keyword which was replaced by `let` in ES6 for defining variables. The `var` keyword still exists but is rarely used and has an effect on scope which makes it different from `let`.
4. Constant declaration
	`const var_name = value;`
	- This defines a constant variable. For basic primitive variables (such as numbers and strings), the value cannot be changed after declaration.
	- This is the standard way for declaring arrays or objects in JavaScript, but when an either is declared constant, it can still be modified, yet not assigned a new value;

Out of these, the Regular and Constant declarations are most common in programs. It is a good habit to use Constant declarations for variables that you know will not change or for arrays and objects. One *extremely important* thing is to not name variables after keywords. Naming a variable something like `let`, `var`, `const`, or any valid JavaScipt keyword will give you errors. 

**Naming Conventions**:
One important thing about writing a program is being consistent with naming conventions. The most popular naming conventions are `camelCase` and `snake_case`. If you choose one, it is better to stick with that. As you can see, many variables in this document use `snake_case`, so that will be the primary naming convention in these documents.


## Modifying Variables
Variables can further be modified after they are initialized or defined (check above for defining variables). There are multiple ways to modify a variable; you could reassign its value to a new one (only in non-constant variables), modify its existing value, or remove its value entirely.

1. Reassigning new value (with variables not defined `const`)
	`var_name = new_value;`
	- Reassigns the value of `var_name` to `new_value`
2. Modifying numbers' existing values with mathematical operators
	- This only works if the variable you are modifying exists and has a numerical value
	- `123` can be replaced with any real number
	- Addition: `number += 123;`
	- Subtraction: `number -= 123;`
	- Multiplication: `number *= 123;`
	- Division: `number /= 123;`
3. Reassigning variables to the result of mathematical operations
	- This only works if both `number` and `other_num` are defined and have numerical values (in the case of numbers)
	- Replace `123` and the variable names with your own to use this structure
	- Addition: `number = other_num + 123;`
	- Subtraction: `number = other_num - 123;`
	- Multiplication: `number = other_num * 123;`
	- Division: `number = other_num / 123;`
	- As you can see, this follows the structure for reassigning new values (`var_name = new_value;`), but turns `new_value` into an expression containing a mathematical operation
4. Reassigning variables to strings
	- To reassign a variable to a string, simply follow the `var_name = new_value;` structure, but replace `new_value` with a string. Remember to escape any special characters in the string to prevent errors
	- Since strings are immutable, this is also the only way to modify a string.
	- Examples:
		- `var_name = "Hello, World!";`
		- `var_name = "She said, \"Hello!\"";`
		- `var_name = "This character is replaced with a newline: \n";`
5. Adding to string values
	- JavaScript also supports using the `+=` operator to add to a string
	- For example, if we have a string `str` with the value `"a"`, then we can add to it like so: `str += new_characters;`
	- Examples:
		- `str += "bc";` will make append `"bc"` to `str`
		- `str += 123;` will append `"123"` to `str`
		- If we run both lines with `str` defined and set to `a`, this will result in `str`'s value being `"abc123"`.
6. Modifying Arrays
	- We can modify arrays using the bracket notation (`array[index_num] = value;`). This accesses the array value at `index_num` and sets it to `value`. It is important to remember that array indices start at 0, so the first element is always `array[0]`.
	- As JavaScript is dynamically typed, accessing/modifying a value outside of the length of the array is allowed, but is bad for performance and creates `undefined` values.
	- The array type is also an object, which allows for you to use some cool functions like `.push()` and `.pop()` to modify an array. We are briefly overviewing this here as it will later be discussed.
	- Examples:
		- `array[0] = 123;`
		- `array[1] = "Example";`
		- Add a new value at the end of an array: `array.push(value);` 
		- Delete the last value of an array: `array.pop();`

**Summary**
- Reassignment structure: `var_name = new_value`;
	- `new_value` could also be a mathematical expression (like `1 * 3` or `other_num + 2`)
- Array Value Reassignment structure: `array_name[index_num] = new_value;`
	- `index_num` starts at 0 to indicate the first element (`array_name[0]`)
- Mathematical operators for modifying numbers
	- Addition is `num_name += number;`
		- `num_name++;` could also be used for just adding 1
	- Subtraction is `numname -= number;`
		- `num_name--;` could also be used for just subtracting 1
	- Division is `num_name /= number;`
	- Multiplication is `num_name *= number;`
- Modifying strings
	- There are two ways to edit strings: reassignment and addition.
	- Reassignment:
		- `let str = "Hello";`
		- `str = "Hey";`
		- `str` is modified from `"Hello"` to `"Hey"`
	- Addition:
		- `let str = "H";`
		- `str += "ello";`
		- `str += 123;`
		- This adds the strings `"ello"` and `"123"` to `str`
- Modifying arrays
	- You must use bracket notation (`array[index_num] = value;`)
	- Array indices are zero-based, meaning the first item of an array will always be at the index of 0.
	- Arrays also have additional functions associated with them, and two are `.push()` and `.pop()`
	- Example (Change the first two elements to `123` and `"Example"` respectfully)
		- `array_name[0] = 123;`
		- `array_name[1] = "Example";`
		- Adding an item to an array: `array_name.push(item);`
		- Deleting the last item of an array: `array_name.pop();`
## Calling Functions
As defining and managing functions will be further explained, we will simply discuss calling them here. To call a function in JavaScript, you must append parentheses after the name of the function. You will place any function parameters in the parentheses. For example, say we have a function `add`, which takes in two parameters: *a* and *b*. 

**Normal Way ✅**
`add(10, 20);`
- This passes both parameters (*a* and *b*) into the parentheses to properly run the function
- When a function has multiple parameters, they are separated by a comma.
- If a string with a comma is passed as a parameter (eg: `"Hello, World!"`), the comma does not count towards splitting the parameters.

**Valid Way, but prone to errors ⚠️**
`add();`
- This calls the function properly, but does not pass any parameters.
- This won't trigger an error unless the `add` function uses the parameters *a* and *b* without checking if they are defined.
- This is the proper syntax for calling a function that takes no parameters

**Wrong Way ❌**
`add;`
- This does not call the function; it only references it.
- Parentheses after a function name are required as it signals to the interpreter that you are invoking it.
## Comments
JavaScript supports comments, which are ignored by the interpreter and allow users to explain their code.

1. Single-line comments
	- `// This is a single-line comment.`
2. Multi-line or inline comments
	- `/* Multi-line comment */`
	- `let var_name; /* Inline comment example */`
