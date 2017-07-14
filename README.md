Cgam
----

# Introduction

Cgam is a stack-based programming implemented in Go that can be used for code golfing. It's derived from [Cjam](https://sourceforge.net/projects/cjam/), but has some major differences.

## Stack-base languages

Stack-based languages works on a stack that grow and shrink. The operations avaliable for these languages are commonly push, pop or run an operation on one or more values. But languages like cjam (and of course, cgam) provide more operations for operating on the stack and also on values. Stack-based languages usually uses the [Reverse-Polish notation](https://en.wikipedia.org/wiki/Reverse_Polish_notation) syntax, which elliminates the need for braces and making the syntax much more simpler.

In Cjam or Cgam, the common operations would be pushing a value, rotating the stack, calling a function (or procedure, in a more exact way), popping a value, etc.

## A brief intro for Cjam

In Cjam, there are 26 variables for each upper case letters other than the stack. It uses predefined operators to operate on the stack and the values. It has 5 basic types: integers, doubles, characters, lists (and strings, which are lists of characters), and blocks. Blocks are actually procedures, which consists of many operators. Value literals and variables are pushed onto the stack. If a variable is a block, it is executed when pushed. Other than the Reverse-Polish Notation, Cjam also has infix operators, which has help from the parser to help them complete more tasks.

## Difference from Cjam
1. Cjam uses `;` to pop a value from the stack. Cgam Use `;` for line comment
2. Cjam uses `o` to output a string representation of a value (`str()` in Python, not `repr()`) and no newline, and `p` to print the value representation (`repr()` this time) and a newline. Cgam uses `o` for the `os` module, and `p` to function the same as the Cjam `o` operator.
3. Cjam uses `\`` for converting a value to its value representation string (`repr()`), but in Cgam, it is used for popping a value from the stack, and `v` is used for a value representation.
4. `.` in Cjam is used on two lists like:
```python
    [a[i:i+1] *op* b[i:i+1] for i in range(max(len(a), len(b)))]
```
and `:` is used to assign a value to a variable, or do `map` or `fold` operations on a list.

In Cgam, this 2 are switched, and like `.`, `:` can also be followed by a block literal.
5. In Cgam, variables can have names longer than one character.
6. In Cgam, more modules (or extended operators) are added (`os`, `regex`, `xfer`).
7. In Cgam, user defined modules can be added.
8. In Cgam, namespaces are added to simplify invoking the extended operators.

**NOTE:** Some features above are still not available at the moment, as the project is still IN DEVELOPMENT!

## Some rationales for making the changes
1. Why long variable names?

Well, this may be taken from [Paradoc](https://github.com/betaveros/paradoc/), another stack-based language derived from Cjam, but long-named variables make the program much easier to understand, just like when you compare a compressed js file and an uncompressed one. Among other things, Cgam can be a easy way to jot down the code, but also keeping the original variable names.

2. Why more modules?

I don't even know exactly why myself ... But somehow I want to make it more like a general programming language but not just for some simple functions. Anyway, those modules shouldn't bother your code golfing!

3. Why use ... Go?

Sorry, I just want to practise myself in using this language. Go is a faster language compare to Java (the startup for Cjam is slow), but it also has wrapped types and operations compare to C.

# Building and usage

Nothing special, just clone the code and `go build cgam.go`! (Sorry, I haven't familiar myself with `go get` and file splitting in Go ...) Running `./cgam` will then take you to the REPL. (Running file and CLI arguments will soon be supported.)
