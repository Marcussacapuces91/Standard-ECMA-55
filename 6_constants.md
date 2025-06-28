---
prev: 5_programs.html
next: 7_variables.html
---

# Constants

## General Description 

Constants can denote both scalar numeric values and string values. 

A numeric-constant is a decimal representation in positional notation of a number. There are four general syntactic
forms of (optionally signed) numeric constants:

- implicit point representation                `sd...d`
- explicit point unscaled representation       `sd..drd..d`
- explicit point scaled representation         `sd..drd..dEsd..d`
- implicit point scaled representation         `sd..dEsd..d`
    
where: 

d is a decimal digit,<br>
r is a full-stop<br>
s is an optional sign, and<br> 
E is the explicit character E.<br>
A string-constant is a character string enclosed in quotation marks (see [4](4_characters_and_strings.md)).

## Syntax 

1. numeric-constant = sign? numeric-rep
2. sign = plus-sign / minus-sign
3. numeric-rep = significand exrad?
4. significand = integer full-stop? / integer? fraction 
5. integer = digit digit* 
6. fraction = full-stop digit digit* 
7. exrad = E sign? integer 
8. string-constant = quoted-string 

## Examples 

```BASIC
    1         500          -21.        .255        1E10
    5E-1      .4E+1 
    "XYZ"     "X - 3B2"    "1E10"
```

## Semantics

The value of a numeric-constant is the number represented by that constant. "E" stands for "times ten to the power"; if
no sign follows the symbol "E", then a plus sign is understood. Spaces shall not occur in numeric-constants. 

A program may contain numeric representations which have an arbitrary number of digits, though implementations may round 
the values of such representations to an implementation-defined precision of not less than six significant decimal
digits. Numeric constants can also have an arbitrary number of digits in the exrad, though nonzero constants whose
magnitude is outside an implementation-defined range will be treated as exceptions. The implementation-defined range
shall be at least IE-38 to 1E+38. Constants whose magnitudes are less than machine infinitesimal shall be replaced by 
zero, while constants whose magnitudes are larger than machine infinity shall be diagnosed as causing an overflow. 

A string-constant has as its value the string of all characters between the quotation marks; spaces shall not be 
ignored. The length of a string-constant, i.e. the number of characters contained between the quotation-marks, is 
limited only by the length of a line. 

## Exceptions 

The evaluation of a numeric constant causes an overflow (non-fatal, the recommended recovery procedure is to supply
machine infinity with the appropriate sign and continue). 

## Remarks 

Since this Standard does not require that strings with more than 18 characters be assignable to string variables (see
[7](7_variables.md)), conforming programs can use string constants with more than 18 characters only as elements in a 
print-list.

It is recommended that implementations report constants whose magnitudes are less than machine infinitesimal as 
underflows and continue.