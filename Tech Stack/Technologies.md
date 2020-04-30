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