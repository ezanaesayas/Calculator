# A Calculator (or two)

In this project, I built a simple interactive calculator.  
The calculator is limited to integers (no floating-point numbers).

The main loop of our calculator is a “read/evaluate/print loop”, sometimes called a REPL. For example, if you interact with Python directly by invoking the interpreter, you will encounter Python's REPL. Ours is simpler, because the input langauge of our interpreter is simpler than Python, but it works in essentially the same way:

- Read a line of text, which should be in the input language of the calculator (RPN).

- Parse that text into an internal program data structure. For us, that structure is an object of class 
    Expr, defined in file expr.py. Class Expr has subclasses for many different kinds of expression, 
    including constants like 5, variables like x, and operations like addition, subtraction, and negation.

- Evaluate that expression structure to obtain a value. Each subclass of Expr has an eval method to
    evaluate itself. For example, a constant like 5 evaluates to itself. A variable like x is evaluated
    by looking for its value in a separate many object called the environment. Operations like addition
    evaluate themselves by applying an operation to their operands.

- Print the result

Interaction with ```rpncalc.py``` looks like this: 
```
Expression (return to quit):3 5 * x =
x = (3 * 5) => 15
Expression (return to quit):x 2 *
(x * 2) => 30
Expression (return to quit):
Bye! Thanks for the math!
```

Interaction with ```llcalc.py``` looks like this: 
```
Expression (return to quit): x = 3 * (5 + 2)
x = (3 * (5 + 2)) => 21
Expression (return to quit):y = 7 * 3
y = (7 * 3) => 21
Expression (return to quit):x + y
(x + y) => 42
Expression (return to quit):
Bye! Thanks for the math!
```


 







