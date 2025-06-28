---
prev: 11_let_statement.html
next: 13_for_and_next_statements.html
---

# Control Statement

## General Description

Control statements allow for the interruption of the normal sequence of execution of statements by causing execution to
continue at a specified line, rather than at the one with the next higher line number.

### The goto-statement

    GO TO line-number 

allows for an unconditional transfer.

### The if-then-statement

    IF expl rel exp2 THEN line-number

where "expl" and'texp2" are expressions and "rel" is a relational operator, allows for a conditional transfer.

### The gosub and return statements

    GO SUB line-number 
    RETURN

allow for subroutine calls.

### The on-goto-statement

    ON expression GO TO line-number, ..., line-number

allows control to be transferred to a selected line.

### The stop-statement

    STOP

allows for program termination.

## Syntax

1. goto-statement = GO space* TO line-number 
2. if-then-statement = IF relational-expression THEN line-number  
3. relational-expression = numeric-expression relation numeric-expression / string-expression equality-relation
   string-expression 
4. relation = equality-relation / less-than-sign / greater-than-sign / not-less / not-greater
5. equality-relation = equals-sign / not-equals  
6. not-less = greater-than-sign equals-sign 
7. not-greater = less-than-sign equals-sign 
8. not-equals = less-than-sign greater-than-sign 
9. gosub-statement = GO space* SUB line-number  
10. return-statement = RETURN 
11. on-goto-statement = ON numeric-expression GO space* TO line-number (comma line-number)*
12. stop-statement = STOP

## Examples

```BASIC
    GO TO 999                   IF X > Y+83 then 200 
    IF A$ <> B$ THEN 550        ON L+1 GO TO 300,400,500
```

## Semantics 
 
A goto-statement indicates that execution of the program is to be continued at the specified line-number.

If the value of the relational-expression in an lf-then-statement is true, then execution of the program shall continue
from the specified line-number; if the value of the relational-expression is false, then execution shall be continued in
sequence i.e. with the statement on the line following that containing the if-then-statement.

The relation "less than or equal to" shall be denoted by `<=`. Similarly, "greater than or equal to" shall be denoted by
`>=`, while "not equal to" shall be denoted by `<>`.

The relation of equality holds between two strings if and only if the two strings have the same length and contain
identical sequences of characters.

The execution of the gosub-statement and the return-statement can be described in terms of a stack of line-numbers (but
may be implemented in some other fashion). Prior to execution of the first gosub-statement by the program, this stack is
empty. Each time a gosub-statement is executed, the line number the gosub-statement is placed on top of the stack and of
the program is continued at the line specified in the gosub-statement. Each time a return-statement is executed, the
line-number on top of the stack is removed from the stack and execution of the program is continued at the line 
following the one with that line-number. 
 
It is not necessary that equal numbers of gosub-statements and return-statements be executed before termination of the 
program.

The expression in an on-goto-statement shall be evaluated and rounded to obtain an integer, whose value is then used to
select a line-number from the list following the GOTO (the line-numbers in the list are indexed from left to right,
starting 1). Execution of the program shall continue at the statement with the selected line-number.

All line-numbers in control-statements shall refer to lines in the program.

The stop-statement causes termination of the program.

## Exceptions

- An attempt is made to execute a return-statement without having executed a corresponding gosub-statement (fatal).
- The integer obtained as the value of an expression in an on-goto-statement is less than one or greater than the number
  of line-numbers in the list (fatal).
