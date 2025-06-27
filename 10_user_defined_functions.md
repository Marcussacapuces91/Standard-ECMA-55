# User defined functions
## General Description

In addition to the implementation supplied functions provided for the convenience of the programmer (see 9), BASIC allows 
the programmer to define new functions within a program.

The general form of statements for defining functions is

    DEF FNx = expression 
    or DEF FNx (parameter) = expression

where x is a single letter and a parameter is a simple numeric-variable.

## Syntax 

1. def-statement = DEF numeric-defined-function parameter-list? equals-sign numeric-expression
2. numeric-defined-function = FN letter
3. parameter-list = simple-numeric-variable

## Examples 

```BASIC
    DEF FNF(X) = X^4 - 1        DEF FNP = 3.14159  
    DEF FNA(X) = A*X + B
```

## Semantics

A function definition specifies the means of evaluating the function in terms of the value of an expression involving the parameter appearing in the parameter-list and possibly other variables or constants. When the function is referenced, i.e. when an expression involving the function is evaluated, then the expression in the argument list for the function reference, if any, is evaluated and its value is assigned to the parameter in the parameter-list for the function definition (the number of arguments shall correspond exactly to the number of parameters). The expression in the function definition is then evaluated, and this value is assigned as the value of the function. 

The parameter appearing in the parameter-list of a function definition is local to that definition, i.e. it is distinct from any variable with the same name outside of the function definition. Variables which do not appear in the parameter-list are the variables of the same name outside the function definition. 

A function definition shall occur in a lower numbered line than that of the first reference to the function. The expression in a def-statement is not evaluated unless the defined function is referenced.

If the execution of a program reaches a line containing a def-statement, then it shall proceed to the next line with no other effect.

A function definition may refer to other defined functions, but not to the function being defined. A function shall be defined at most once in a program.

## Exceptions

None.
