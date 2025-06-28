---
prev: A1_organisation_of_the_standard.html
next: A3_conformance.html
---

# Appendix 2<br>Method of Syntax Specification

The syntax, through a series of rewriting rules known as "productions", defines syntactic objects of various types, such
as "program" or "expression", and describes which strings of symbols are objects of these types. 

In the syntax, upper-case letters, digits, and (possibly hyphenated) lower-case words are used as "metanames", i.e. as
names of syntactic objects. Most of these metanames are defined by rewriting rules in terms of other metanames. In order
that this process terminate, certain metanames are designated as "terminal" metanames, and rewriting rules for them are
not included in the syntax. All terminal metanames occur for the first time and are defined in 
[Section 4](4_characters_and_strings.md). It should be noted in particular that all upper-case letters are terminal 
metanames which denote themselves. 

We illustrate further details of the syntax by considering some examples. In Section 12 we find the production 

    gosub-statement = GO space* SUB line-number

which indicates that a "gosub-statement" consists of the letters G, O, any number of spaces, S, U, and B followed by a 
line number.

What is a "line-number"? In [Section 5](5_programs.md), the production 

    line-number = digit digit? digit? digit?

indicates that a "line-number" is a "digit" followed by up to three other "digits" (the question mark is a syntactic 
operator indicating that the object it follows may or may not be present). 

What is a "digit"? [Section 4](4_characters_and_strings.md), the production

    digit = 0/1/2/3/4/5/6/7/8/9 

indicates that a "digit" is either a "0", a "1", ... or a "9" (the solidus is a syntactic operator meaning "or" and is
used to indicate that a metaname can be rewritten in one of several ways). Since the digits are terminal metanames (i.e.
they do not occur on the left-hand side of any production), our decipherment of the syntax for the "gosub-statement"
comes to an end. The semantics in Section 4 identify the digits in terms of the characters they represent.

An asterisk is a syntactic operator like the question-mark, and it indicates that the object it follows may occur any
number of times, including zero times, in the production. 

For example

    integer = digit digit*

indicates that an "integer" is a "digit" followed by an arbitrary number of other "digits".

Parentheses may be used to group sequences of metanames together. 

For example

    variable-list = variable (comma variable)* 

defines a "variable-list" to consist of a "variable" followed by an arbitrary number of other "variables" separated by
"commas". 

When several syntactic operators occur in the same production, the operators "?" and "*" take precedence over the
operator "/". 

Spaces in the syntax are used to separate hyphenated lower-case words from each other. Special conventions are observed
regarding spaces in BASIC programs (see [Section 5](5_programs.md)). The syntax as described generates programs which
contain no spaces other than those occurring in remarks, in certain string constants, or where the presence of a space
is explicitly indicated by the metaname "space". 

Additional spaces may be inserted to improve readability provided that the restrictions imposed in 
[Section 5](5_programs.md) are observed.
