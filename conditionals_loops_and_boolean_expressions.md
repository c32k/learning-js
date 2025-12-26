# Conditionals, Loops, and Boolean Expressions
Before examples and a proper explanation of each of the three topics covered in this document are given, provided is a brief explanation of each and their functionality in JavaScript. For those of you "Advanced" JavaScript coders, ternary operators are not covered here.

1. **Conditionals** - Statements which do something specifically if a *Boolean Expression*. Think of it as doing something depending on the answer to a yes/no question, except the answers are true or false. This is important in programming as it allows programmers to do certain things based on a *condition*. *Example: Making Coffee for a person after they answer "Yes" to "Do you want coffee?"*
2. **Loops** - Blocks of code that are executed several times, either based on a fixed count, or a condition. This is useful for repeatedly executing blocks of code without having to duplicate the code multiple times. You can even nest *Conditional* statements inside a loop to have a chance of different outcomes in each repetition of the loop! *Example: Making Coffee a set amount of times **OR** Making Coffee until someone says to stop (A condition is met).*
3. **Boolean Expressions** - Unlike *Loops* and *Conditionals*, *Boolean Expressions* are not *Statements*, meaning they do not perform a complete action unless they are implemented into a *Statement*. *Boolean Expressions* check something, which means they are evaluated into *true* or *false* and can be used in *Conditionals*. *Example: Checking if you have more than five cups of coffee made.*

Now that each topic is briefly explained, we can elaborate. Remember, if you don't understand something, do not hesitate to search it up or ask someone else to explain it!
# Conditionals
As explained previously, conditionals are statements which execute blocks of code if what is passed evaluates to true. Basic JavaScript holds  `if-else` statements.

`if-else` statements execute a block of code *If* something is true. Otherwise (*Else*) they will execute a block *If* something is false. Below is a simple `if` statement. You will notice that I write `condition` which is a placeholder for a *boolean expression*. 
```js
// if statement
if (condition) { // Boolean expression placed in parentheses
	// Code here executed if condition is true
}
```

In a basic `if` statement, there is the `if` keyword followed by parentheses and curly brackets. In the parenthesis, you put your boolean expression (covered later). If the boolean expression inserted in the parenthesis is checked and shown to be true, then the statements enclosed in the curly brackets will be executed. More examples will be shown in the *Boolean Expressions* section.

```js
// if-else statement
if (condition) {
	// Code here executed if condition is true
} else {
	// Code here executed if condition is false
}
```

This is an `if-else` statement. It is just a simple `if` statement with an additional `else` keyword attached after of the `if` statement's closing curly bracket. Whatever is in the `else` curly brackets will be executed if the condition in the `if` statement's parentheses is false.

```js
if (condition) {
	// If condition is true
} else if (second_condition) {
	// If second_condition is true
} else {
	// If neither condition is true
}
```

This is the final version of `if-else` statements. After the original `if` statement, you can add as many `else if` statements (which check if a different condition is true) as you want, however it is best to put them all before an `else` statement (if you add one). If you do add an `else` statement after multiple `else if` statements, then the code in the `else` statement will execute if neither the original `if` statement nor the additional `else if` statements are true. Remember, `else` and `else if` statements are optional after an `if` statement.

It is also a good practice to use a `switch-case` statement (covered next) instead of a long chain of an `if` statement and multiple `else if` statements afterwards.

An additional note is that when the code executed by if statements is one line, you can generally omit the curly brackets, although you should add a semicolon:

```js
if (condition) code;
else if (other_condition) other_condition_code;
else else_code;
```
## Switch-Case Statements
A section on `switch-case` statements was added here as although it doesn't typically fall under the category of the document topics, it is important to know and is similar to `if` statements.

In `switch-case` statements, a value is "switched" through different cases, and if the value is identical to the value specified in the case, the code block in the case is executed. This is a good alternative to a long chain of `else if` statements. Remember to always add `break;` at the end of each case to signify the end of the case, unless you intentionally want case fall-through.

```js
switch(value) {
	case value1:
		// Code executes if values equals value1
		break; // Breaks from checking other cases
	case value2:
		// Code executes if value equals value2
		break;
	case value3:
		// Code executes if value equals value3
		break;
	default:
		// Code executes if neither of the cases are met
		break;
}
```

This is a `switch-case` statement. It starts similarly to an if statement, except instead of a condition, a value is passed (such as a number or a string). Inside the curly brackets lie several cases, each prefixed by the `case` keyword, a value, and a colon. This allows for a programmer to check the value of a variable with simple syntax instead of a chain of `if` statements. As mentioned previously, the `break` keyword is included to exit out of the `switch` statement and prevent case fall-through. We can now use previously covered things to make a more sophisticated and realistic use of the `switch-case` statement:

```js
const direction = "NORTH"; // Marked constant as we don't change the value

switch(direction) {
	case "NORTH":
		// This case will be executed as direction is "NORTH"
		console.log("Direction is North!");
		break;
	case "EAST":
		console.log("Direction is East!");
		break;
	case "SOUTH":
		console.log("Direction is South!");
		break;
	case "WEST":
		console.log("Direction is West!");
		break;
}
```

# Loops
Loops are a great tool for programmers to repeat code without having to duplicate it. This document will cover the two most common loops: `for` and `while` loops. 

### For Loops
`for` loops are one of the most common loops used in JavaScript. There are different ways to use a `for` loop, but for now we will use the indexing method. This is great for repeating something a set amount of times or for indexing through an array.

```js
// For loop structure
for (initialization; condition; iteration) {
	// Code executed in the loop
}
```

This may look completely confusing, and that makes sense. Once you use it often, it is easy to remember and is not complicated. The `for` loop usually takes in three parameters separated by semicolons: the initialization, condition, and iteration. The initialization is run at the start of the loop and is usually for *initializing* our iterator, commonly named `i`. The variable `i` is meant to keep track of the index (which is especially useful when iterating through an array), and is often set to `0` at the start, as arrays are zero-indexed. The condition is the *Boolean Expression* evaluated before each iteration of the loop. This means before a new iteration of the loop, the condition is checked to be `true` before continuing. The iteration is typically a statement executed after an iteration is completed. This is usually for updating the counter or iterator, `i`. This might sound confusing, so it is best to see some examples!

1. Printing a number
```js
for (let i = 0; i<5; i++) {
	// Initialization: setting a variable i to zero before the loop runs
	// Condition: checking if i < 5 before each iteration
	// Iteration: Adding 1 to i after each iteration
	// After the loop executes, i is moved out of scope, so you can reuse it
	console.log(i); // Printing the current value of i
}
// Expected output:
// 01234
```

2. Iterating through an array
```js
const array = ['a', 'b', 'c', 'd', 'e'];
// Good practice: marking arrays as constant

for (let i = 0; i < array.length; i++) {
	// An array's length is accessible this way
	// name.length
	console.log(array[i]) // Using bracket notation to pass each index
}
// Expected output:
// abcde
```

### While Loops
In JavaScript, `while` loops are condition loops. This means they do something `while` a condition is `true`. So, just like `if` statements, you must pass a *Boolean expression* that is evaluated before the loop is executed. Here is the while loop structure:

```js
while(condition) {
	// Execute code while condition is true
}
```

Just like `if` statements, you can omit curly brackets if the code body in the while loop is a singular line, but add a semicolon at the end of the line like so:

```js
while(condition) code;
```

# Boolean Expressions
*Boolean Expressions* are not statements; they do little to nothing on their own, but can be incorporated into statements. *Booleans* – named after the mathematician George Boole (Inventor of Boolean Algebra) – can only hold one of two values: true or false. This means that *Boolean Expressions* are Expressions which evaluate to a boolean, or a true/false value. Because of this, *Boolean Expressions* are often used inside `if` statements as the condition. Below are the types of *Boolean Expressions* accompanied by examples:

```js
// Comparative Boolean Expressions
value > 123 // is true if value is greater than 123
value < 123 // is true if value is less than 123
value == 123 // is true if value is equal to 123
value != 123 // is true if value is not equal to 123
value <= 123 // is true if value is less than or equal to 123
value >= 123 // is true if value is greater than or equal to 123

value === 123 // strict equality (generally reccomended)
value !== 123 // strict inequality

// Variable Boolean Expressions
value // This checks if value is "truthy"
// Will work unless value is 0, "", '', null, undefined, NaN, etc.
// Any type of array or object, even an empty one, is "truthy"
!value // This checks if value is "falsy"
// Works usually if value is 0, "", '', null, undefined, NaN, etc.

// Compound Boolean Expressions
bool_expression && other_bool_expression // Works if both are true
bool_expression || other_bool_expression // Works if only one is true
// You can have more than two
bool_expr_1 && bool_expr_2 && bool_expr_3 // expr is short for expression
bool_expr_1 || bool_expr_2 || bool_expr_3
// You can also use parenthesis to make it double compound
(bool_expr_1 && bool_expr_2) || value > 3 // using previous example
(value > 3 && value < 6) || (value > 9 && value < 12)
```

Now, we can finally start using *Boolean Expressions* them in both *Conditionals* and *Loops*!
```js
let value = 10;

while(value < 20) value++;

for (let i = 0; i<5; i++) {
	value += i;	
}

if (value > 10) {
	console.log("Big number!");
} else if (value < 10) {
	console.log("Small number...");
} else {
	console.log("You shouldn't be seeing this");
}
```
