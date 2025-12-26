# Introduction
**Javascript** is a dynamically-typed, high-level scripting language. This gives it the ability to be a powerful language for beginners. Here is a quick overview of those terms:
1. **Dynamically-typed**: Variables are initiated without requiring the type of the variable to be specified. Variables are also able to change their types throughout the program, allowing for them to be flexible.
2. **High-level**: Unlike more complex, low-level languages like C, Javascript provides many abstractions, meaning the programmer doesn't have to write as much code.
3. **Scripting**: Scripting languages are usually interpreted languages, meaning they are typically interpreted and run during runtime rather than before runtime like most compiled languages. Although this makes the process longer, modern JavaScript engines automatically optimize performance, making JavaScript a great tool for automation and various scripts.

Don't worry if you don't entirely understand these terms, as they aren't relevant when learning the language, but are helpful when understanding it or comparing it to other programming languages.

# A Basic Javascript "Hello World" Program
Below is a simple javascript program which prints the text "Hello World" to the standard output or console.
```js
console.log("Hello World");
```

Now let's break this down, piece by piece.
1. `console`
	- In javascript, there are things called objects. Objects are like containers which store data such as variables, functions, or other things. In this line of code, `console` is an object which we are accessing.
2. `.log(`
	- Whenever you want to access a member of an object, there are two ways to do so: Dot notation and Bracket Notation. Dot notation (`object_name.member`) is used in this piece to access a function titled `log` from the object `console`.
	- Since `log` is a function, we use parentheses () to specify the parameters passed to it. The function `log` that is a member of `console` can take one or more parameters, each being printed to the console.
	- By using the left parenthesis, we specify that the next value will be a parameter passed to the function. We can pass parameters to a function like so: `func_name(param1, param2);`
3. `"Hello World"`
	- Whenever something is a surrounded by quotes (like this: `"example"`), the interpreter will know that it is text, or as Javascript refers to it, a "string."
	- When creating strings in Javascript, there is one very important rule; you must escape special characters inside the string. Say we have a string like `"He said "Hi!" "`. Javascript will split this into three parts: `"He said"`, `Hi!`, and `""`.  We don't want that, so we must escape the special character (in this case the double quote) with a backslash. This means the correct version would be: `"He said \"Hi!\""`. As you can see in that version, all inside quotes are escaped, which would make this valid string.
4. `);`
	- This is the last part of the line. The right parenthesis indicates there are no more function parameters to be passed.
	- Although not completely required, I recommend using semicolons to end lines. These are two valid lines: `function_i_am_running()` and `function_i_am_running();`, the only difference being one ends with a semicolon and the other does not. There is one case where a semicolon is required. This case is when two expressions are in the same line; `first_expression; second_expression`. This is the correct way to put two expressions on the same line.

You can test this program by finding a Javascript interpreter, or running it online through a website like https://onecompiler.com/javascript. I recommend you paste the original code in and then fidget with it to produce your own unique outputs. Printed strings should show on the "console" section.

If you don't completely understand this line, don't worry! Objects, Functions, and Javascript Grammar will be further explained in later lessons.
