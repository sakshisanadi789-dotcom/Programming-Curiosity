# Compiler

## WHY?
A compiler translates a program into another form so it can be checked, optimized, or executed efficiently. It also helps detect many errors before the program runs.

## WHAT?
A compiler is a tool that transforms source code into a target representation, such as machine code, bytecode, or another language. Compilation does not by itself guarantee that a program is correct or secure.

## HOW?
A compiler typically parses source into a syntax tree, checks language rules and types, then generates and optionally optimizes a target form. Build tools may also link compiled modules and libraries into an executable.

## WHERE?
Compilation can happen on a developer's computer, in a build server, on a device, or just in time while a program runs. The resulting program may execute somewhere else if the target platform is compatible.

## WHEN?
Ahead-of-time compilation is common for native applications. Bytecode compilation and just-in-time compilation are common in managed runtimes. Many language implementations combine compilation and interpretation.

## WHO?
Compiler authors implement a language and target platform. Developers invoke compilers directly or through build tools and inspect diagnostics when translation fails.

## WHAT IF?
If the compiler rejects a program, its diagnostics point to a translation or validation problem. If compilation succeeds, runtime errors and logical bugs are still possible; testing remains necessary.