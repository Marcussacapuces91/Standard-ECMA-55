# FOR and NEXT statements 
## General Description

The for-statement and next-statement provide for the construction of loops. The general syntactic form of the for-statement and next-statement is

    FOR v = initial-value TO limit STEP increment 
    NEXT v

where "v" is a simple numeric variable and the "initial-value", "limit" and "increment" are numeric expressions; the clause "STEP increment" is optional. 

## Syntax

1. for-block = for-line for-body 
2. for-body = block next-line 
3. for-line = line-number for-statement end-of-line 
4. next-line = line-number next-statement end-of-line
5. for-statement = FOR control-variable equals-sign initial-value TO limit (STEP increment)? 
6. control-variable = simple-numeric-variable
7. initial-value = numeric-expression 
8. limit = numeric-expression 
9. increment = numeric-expression 
10. next-statement = NEXT control-variable 

## Examples

    FOR I = 1 TO 10         FOR I = A TO B STEP -1
    NEXT I                  NEXT I

## Semantics

The for-statement and the next-statement are defined in conjunction with each other. The physical sequence of statements beginning with a for-statement and continuing up to and including the first next-statement with the same control variable is termed a "for-block". For-blocks can be physically nested, i.e. one can contain another, but they shall not be interleaved, i.e. a for-block which contains a for-statement or a next-statement shall contain the entire for-block begun or ended by that statement.

Furthermore, physically nested for-blocks shall not use the same control variable. 
