# Randomize Statement

## General Description

The randomize-statement overrides the implementation-predefined sequence of pseudo-random numbers as values for the RND
function, allowing different (and unpredictable) sequences each time a given program is executed.

## Syntax

1. randomize-statement      = RANDOMIZE

## Examples 
```BASIC
RANDOMIZE
``` 

## Semantics

Execution of the randomize-statement shall generate a new unpredictable starting point for the list of pseudo-random
numbers used by the RND function (see [9](9_implementation_supplied_functions.md)).

## Exceptions 

None. 

## Remarks

In the case of implementations which do not have access to a randomizing device such as a real-time clock, the 
randomize-statement may be implemented by means of an interaction with the user.

[Back](./)