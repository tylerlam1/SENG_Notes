# Python
Python is a easy-to-learn, powerful programming language. It has efficient high-level data structures and a simple yet effective approach to object-oriented programming. The Python interpreter is easily extended with new functions and data types implemented in C or C++. 

Python is an interpreted language, which means no compilation and linking is necessary. Statement grouping is done by indentation rather than brackets. No variable or argument declarations are necessary.

Python is extensible: If you know how to program in C it is easy to add a new built-in function or module to the interpreter, like linking Python programs to libraries that may be only available in binary form. 

## Interpreter
You can exit the interpreter by pressing `quit()`.  The first way to invoke the interpreter is to input a file (as an argument) as standard input. The interpreter reads and executes a script from that file. The second way of starting the interpreter `python -c command [arg]...`, which executes the statements command. This is analogous to the shell's `-c` option. It is usually advised to quote command in its entirety because this may make the interpeter confused. 

You can use arguments in the command line by using the `sys` module. They are assigned to the `argv` variable. For example, you can grab it by entering `sys.argv` in your code. 

Interactive mode is usually denoted by three greater-than signs `>>>`. Continuation lines it prompts with the second prompt, which uis denoted with three dots `...`. Inputs and outputs are distinguished by the prescence or absence of prompts. 

Division always returns a float. To do floor division, you can use the `//` operator. The modulus operator is done using `%`. Powers can be calculated using `**`. Assignments are done using a `=`. 

In interactive mode, the last printed expression is assigned to the variable `_`. The variable should be read only. By explicitly assigning a variable to it, you would create an independent local variable with the same name masking the built-in variable.

Strings in Python are enclosed in single quotes or double quotes, each producing the same result. `\` is used to escape quotes. `print()` produces a readable output. 

Python also knows some compound data types. The most versatile of these types is a *list*. A list is written as a comma-separated list of values between square brackets. For an example, see below.

```c
squares = [1,4,9,16,25]
```

Lists can be indexed and sliced, like in MATLAB. While strings are immutable in Python, lists are indeed mutable. You can also add new items at the end of the list in Python, using the `append()` function.

## Control Flow Tools
The following are control flows tools.

1. If statements - you can use `if` and `elif` statements. The else part is optional. For longer elif statements, a `switch` statement is more appropriate.
2. For statements - the `for` statement in Python acts more like a for-each statement. 
3. Range function - Range is useful for iterating over a sequence of numbers.
4. Break statement - Breaks out of a for or while loop
5. Else statement - A loop statement may also have a else clause, which is executed when the loop terminates through exhaustion of the iterable. You can think of this as a catch clause in a try-catch statement.
6. Continue - continues with the next iteration of the loop.
7. Pass statement - does nothing.

## Methods
When defining functions, the `def` keyword can be used. The first statement of the function body cn optionally be a string literal, also known as a *docstring*. 