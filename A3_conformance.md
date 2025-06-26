# Appendix 3
# Conformance

There are two aspects of conformance to this language Standard : conformance by a program written in the language, and conformance by an implementation which processes such programs. 

A program is said to conform to this Standard only when 

- each statement contained therein is a syntactically valid instance of a statement specified in this Standard, 
- each statement has an explicitly valid meaning specified herein, and
- the totality of statements compose an instance of a valid program which has an explicitly valid meaning specified herein. 

An implementation is said to conform to this Standard only when 

- it accepts and processes programs conforming to this Standard,
- it reports reasons for rejecting any program which does not conform to this Standard,
- it interprets errors and exceptional circumstances according to the specifications of this Standard,
- its interpretation of the semantics of each statement of a standard-conforming program conforms to the specification in this Standard, 
- its interpretation of the semantics of a standard-conforming program as a whole conforms to the specifications in this Standard,
- it accepts as input, manipulates, and can generate as output numbers of at least the precision and range specified in this Standard, and
- it is accompanied by a reference manual which clearly defines the actions taken in regard to features which are called "undefined" or "implementation-defined" in this Standard. 

This Standard does not include requirements for reporting specific syntactic errors in the text of a program. Implementations conforming to this Standard may accept programs written in an enhanced language without having to report all constructs not conforming to this Standard. However, whenever a statement or other program element does not conform to the syntactic rules given herein, either an error shall be reported or the statement or other program element shall have an implementation-defined meaning.

[Back](./)