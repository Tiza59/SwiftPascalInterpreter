# Pascal interpreter written in Swift
Simple Swift interpreter for the Pascal language inspired by the [Let’s Build A Simple Interpreter](https://ruslanspivak.com/lsbasi-part1/) article series.

## Scructure

### Lexer

The [Lexer](https://github.com/igorkulman/SwiftPascalInterpreter/blob/master/SwiftPascalInterpreter/SwiftPascalInterpreter/Lexer.swift) reads the Pascal program as `String` (a sequence of characters) and converts it into a sequest of [Tokens](https://github.com/igorkulman/SwiftPascalInterpreter/blob/master/SwiftPascalInterpreter/SwiftPascalInterpreter/Model/Token.swift). You can see the result by trying it our in the Playground or on the [unit tests](https://github.com/igorkulman/SwiftPascalInterpreter/blob/master/SwiftPascalInterpreter/SwiftPascalInterpreterTests/LexerTests.swift).

### Parser

The [Parser](https://github.com/igorkulman/SwiftPascalInterpreter/blob/master/SwiftPascalInterpreter/SwiftPascalInterpreter/Parser.swift) reads the sequence of tokens produced by the Lexer and builds an [Abstract Syntax Tree representation (AST for short)](https://github.com/igorkulman/SwiftPascalInterpreter/blob/master/SwiftPascalInterpreter/SwiftPascalInterpreter/Model/Token.swift) of the Pascal program according to the [grammar](https://github.com/igorkulman/SwiftPascalInterpreter/blob/master/grammar.md). 

You can see what the AST looks like in the [unit tests](https://github.com/igorkulman/SwiftPascalInterpreter/blob/master/SwiftPascalInterpreter/SwiftPascalInterpreterTests/ParserTests.swift) or in the Playground where you can also use the `printTree()` method on any AST to see its visual representation printed into the console.

### Interpreter

The [Interpreter](https://github.com/igorkulman/SwiftPascalInterpreter/blob/master/SwiftPascalInterpreter/SwiftPascalInterpreter/Interpreter.swift) reads the AST representing the Pascal program from Parser and interprets it. It can handle basic Pascal programs with declarations and arithmetics on integers and reals. 

At the end of the Pascal program interpretation you can check the resulting memory state (see [unit tests](https://github.com/igorkulman/SwiftPascalInterpreter/blob/master/SwiftPascalInterpreter/SwiftPascalInterpreterTests/InterpreterTests.swift)) or print it in the Playground using `printState()`.

## Try it out

There is a Swift playground in the project where you can try out the lexer, parser and the interpreter. The lexer shows the tokens recognized, the parses prints the abstract syntax tree of the program and interpreter prints the resulting memory state.

![Playground](https://github.com/igorkulman/SwiftPascalInterpreter/raw/master/playground.png)
