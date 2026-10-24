# Interpreter

## WHY?
An interpreter lets a language's programs run without requiring the user to manually translate every instruction into machine code. It can provide portability and interactive development, depending on the implementation.

## WHAT?
An interpreter is a program that executes another program. “Interpreted” describes an execution approach, not necessarily the absence of compilation: interpreters often parse source or execute bytecode produced by a compiler.

## HOW?
In the common CPython implementation, Python source is parsed and compiled to code objects containing bytecode, which the Python virtual machine evaluates. CPython may cache bytecode in `__pycache__`; this is an implementation detail, not a universal requirement of Python.

## WHERE?
The interpreter itself is a native process running under the operating system. The program's Python code runs inside that process through the interpreter and its runtime libraries.

## WHEN?
Interpreters are useful for scripting, interactive shells, portability, and rapid iteration. Implementations may compile parts of a program ahead of time or just in time for performance.

## WHO?
The Python implementation executes the language semantics; CPython is the most widely used implementation, but PyPy and other implementations have different internals. The operating system runs the interpreter executable.

## WHAT IF?
If Python reports a syntax error, execution of that source cannot proceed as written. A runtime exception can occur after execution begins. A traceback shows the call path and error location, while not necessarily identifying the underlying design mistake by itself.