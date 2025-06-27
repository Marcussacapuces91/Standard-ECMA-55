# Implementation supplied functions
## General Description

Predefined algorithms are supplied by the implementation for the evaluation of commonly used numeric functions. 

## Syntax

1. numeric-supplied-function = ABS / ATN / COS / EXP / INT / LOG / RND / SGN / SIN / SQR / TAN 

## Examples 

None. 

## Semantics 

The values of the implementation-supplied functions, as well as the number of arguments required for each function, are described below. In all cases, X stands for a numeric expression. 

| Function                 | Function value                                                                                                                                                                                             |
|--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `ABS(X)`                 | The absolute value of X.                                                                                                                                                                                   |
| `ATN(X)`                 | The arctangent of X in radians, i.e. the angle whose tangent is X. The range of the function is<br>`-(pi/2) < ATN(X) < (pi/2)`<br>where pi is the ratio of the circumference of a circle to its diameter.  |
| `COS(X)`                 | The cosine of X, where X is in radians.                                                                                                                                                                    |
| `EXP(X)`                 | The exponential of X, i.e. the value of the base of natural logarithms (e = 2,71828...) raised to the power X; if EXP(X) is less than machine infinitesimal, then its value shall be replaced by zero.     |
| `INT(X)`                 | The largest integer not greater than X; e.g.<br>`INT(1.3) = 1` and `INT(-1.3) = -2`                                                                                                                        |
| `LOG(X)`                 | The natural logarithm of X; X must be greater than zero.                                                                                                                                                   |
| `RND`                    | The next pseudo-random number in an implementation-supplied sequence of pseudo-random numbers uniformly distributed in the range 0 <= RND < 1 (see also [20](20_randomize_statement.md)).                  |
| `SGN(X)`                 | The sign of X: -1 if X < 0, 0 if X = 0 and +1 if X > 0.                                                                                                                                                    |
| `SIN(X)`                 | The sine of X, where X is in radians.                                                                                                                                                                      |
| `SQR(X)`                 | The nonnegative square root of X; X must be nonnegative.                                                                                                                                                   |
| `TAN(X)`                 | The tangent of X, where X is in radians.                                                                                                                                                                   |

## Exceptions

- The value of the argument of the LOG function is zero or negative (fatal).
- The value of the argument of the SQR function is negative (fatal).
- The magnitude of the value of the exponential or tangent function is larger than machine infinity (nonfatal, the recommended recovery procedure is to supply machine infinity with the appropriate sign and continue).

## Remarks 

The RND function in the absence of a randomize-statement (see [20](20_randomize_statement.md)) will generate the same sequence of pseudo-random numbers each time a program is run. This convention is chosen so that programs employing pseudo-random numbers can be executed several times with the same result. 

It is recommended that, if the value of the exponential function is less than machine infinitesimal, implementations report this as an underflow and continue.
