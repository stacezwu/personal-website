+++
title = "Custom C Compiler"
date = "2020-06-17"

[extra]
subtitle = "We built a C to MIPS compiler in C++"
date = "June 2020"
abstract = "Starting with a C to Python compiler, and building to a partial C to MIPS assembly compiler. The project is written in C++ with a Yacc parser."
+++

# About the Project

## Translator

In the first deliverable we built a parser for a subset of the C programming language and a C++ compiler which can be used to generate Python code.

The compiler/ translator for this part supports the following constructs:

_Variables:_
- Local integer variables (though not nested scopes)
- Global integer variables
- No variable shadowing

_Functions:_
- Definition of functions taking 0 or more integer parameters and with void or integer return type
- Explicit support for main special functionality

_Statements:_
- if
- if-else
- while
- return
- sequences

_Expressions:_
- Decimal integer constants
- Integer arithmetic: `*`,`+`,`-`
- Logical operations: `&&`,`||`
- Comparison operations: `<`,`==`
- Invocation of functions
- Assignment (but only as a direct expression statement)

## MIPS Compiler

For this part of the project, we used the parser and C++ logic we had in place from the translator, and extended it to build a compiler which generates MIPS assembly code.

We started by implementing a simpler feature-set initially, to be able to compile:

* a file containing just a single function with no arguments
* variables of `int` type
* local variables
* arithmetic and logical expressions
* if-then-else statements
* while loops

Once those constructs where working, we moved on to handling progressively more and more complex programs which include:

* files containing multiple functions that call each other
* functions that take up to four parameters
* for loops
* arrays declared globally (i.e. outside of any function in your file)
* arrays declared locally (i.e. inside a function)
* reading and writing elements of an array
* recursive function calls
* the `enum` keyword
* `switch` statements
* the `break` and `continue` keywords
