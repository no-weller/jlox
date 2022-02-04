# Interpreter jlox
This will be my first attempt to create a own interpreter for a programming language

# The grammar for jLox expressions
* Literals: Numbers, strings, Booleans, and `nil`
* Unary expressions: A prefix `!` to perform logical not, and `-` to negate a number
* Binary expressions: The infix arithmetic `(+,-,*,/)` and logic operators `(==,!=,<,<=,>,>=)`
* Parentheses: A pair of `(` and `)` wrapped around an expression

Leads to a grammar like so:
```
expression  -> literal | unary | binary | grouping ;
literal     -> NUMBER | STRING | "true" | "false" | "nil" ;
grouping    -> "(" expression ")" ;
unary       -> ( "-" | "!" ) expression ;
binary      -> expression operator expression ;
operator    -> "==" | "!=" | "<" | "<=" | ">" | ">=" | "+" | "-" | "*" | "/"
```
In addition to quoted strings for terminals that match exact lexemes, Lux `CAPITALIZE` terminals that are single lexeme whose text representation may vary. `NUMBER` is any number literal, and `STRING` is any string literal. The same is done for `IDENTIFIER`.