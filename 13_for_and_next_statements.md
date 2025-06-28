---
prev: 12_control_statement.html
next: 14_print_statement.html
---

# FOR and NEXT statements

## General Description

The for-statement and next-statement provide for the construction of loops. The general syntactic form of the 
for-statement and next-statement is

    FOR v = initial-value TO limit STEP increment 
    NEXT v

where "v" is a simple numeric variable and the "initial-value", "limit" and "increment" are numeric expressions; the
clause "STEP increment" is optional. 

## Syntax

1. for-block = for-line for-body 
2. for-body = block next-line 
3. for-line = line-number for-statement end-of-line 
4. next-line = line-number next-statement end-of-line
5. for-statement = `FOR` control-variable equals-sign initial-value `TO` limit (`STEP` increment)? 
6. control-variable = simple-numeric-variable
7. initial-value = numeric-expression 
8. limit = numeric-expression 
9. increment = numeric-expression 
10. next-statement = `NEXT` control-variable 

## Examples

```BASIC
    FOR I = 1 TO 10         FOR I = A TO B STEP -1
    NEXT I                  NEXT I
```

## Semantics

The for-statement and the next-statement are defined in conjunction with each other. The physical sequence of statements 
beginning with a for-statement and continuing up to and including the first next-statement with the same control
variable is termed a "for-block". For-blocks can be physically nested, i.e. one can contain another, but they shall not
be interleaved, i.e. a for-block which contains a for-statement or a next-statement shall contain the entire for-block 
begun or ended by that statement.

Furthermore, physically nested for-blocks shall not use the same control variable. 

In the absence of a `STEP` clause in a for-statement, the increment is assumed to be +1. 

The action of the for-statement and the next-statement is defined in terms of other statements, as follows:

    FOR v = initial-value TO limit STEP increment 
    (block) 
    NEXT v

is equivalent to:

            LET own1 = limit 
            LET own2 = increment 
            LET v = initial-value 
    line1   IF (v-own1) * SGN (own2) > 0 THEN line2 
            (block) 
            LET v = v + own2 
            GOTO line1 
    line2   REM continued in sequence

Here v is any simple-numeric-variable, own1 and own2 are variables associated with the particular for-block and not
accessible to the programmer, and linel and line2 are line-numbers associated with the particular for-block and not
accessible to the programmer. The variables own1 and own2 are distinct from similar variables associated with other
for-blocks. A program shall not transfer control into a for-body by any statement other than a return statement 
(see [12](12_control_statement.md)).

##  Exceptions

None.

## Remarks

Where arithmetic is approximate (as with decimal fractions in a binary machine), the loop will be executed within the
limits of machine arithmetic. No presumptions about approximate achievement of the end test are made. It is noted that
in most ordinary situations where machine arithmetic is truncated (rather than rounded), such constructions as 

    FOR X = 0 TO 1 STEP 0.1 

will work as the user expects, even though 0.1 is not representable exactly in a binary machine. If this is indeed the
case, then the construction 

    FOR X = 1 TO 0 STEP -0.1 

will probably not work as expected.

As specified above, the value of the control-variable upon exit from a for-block via its next-statement is the first 
value not used; if exit is via a control-statement, the control variable retains the value it has when the
control-statement is executed.

The variables "own1" and "own2" associated with a for-block are assigned values only upon entry to the for-block through
its for-statement.
