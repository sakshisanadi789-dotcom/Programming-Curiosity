# How Code Runs

## WHY?
Processors execute simple machine instructions, not human ideas. Programming languages and their runtimes bridge that gap, letting people express higher-level logic while tools translate it into executable operations.

## WHAT?
Source code is the text a programmer writes. Depending on the language, tools may compile it to native machine code, translate it to bytecode, interpret it, or combine these approaches. A runtime supplies services such as object management, libraries, and exception handling.

## HOW?
For a typical compiled path, tools parse and check source code, translate it, and produce an executable. At launch, the operating system loads that executable into a process. For an interpreted path, an interpreter reads or compiles source into an internal form and executes it. In either case, `if` selects a path, loops repeat instructions, and function calls transfer control and pass arguments according to the language's rules.

## WHERE?
Execution happens in a process managed by an operating system, using CPU instructions and memory. Some work may also be sent to a GPU, another device, or a remote server.

## WHEN?
Compilation may happen ahead of time, when a program starts, or while it runs. The exact choice depends on the language implementation and deployment model; “compiled” and “interpreted” are not always mutually exclusive categories.

## WHO?
The programmer supplies the source and inputs. Language tools translate or interpret it, the operating system creates and manages the process, and the CPU executes instructions. Libraries and runtime components participate along the way.

## WHAT IF?
Invalid source may be rejected before execution or fail at runtime. Bugs can produce incorrect results, and resource limits or operating-system errors can stop a process. Debuggers, tests, logs, and crash reports help locate which stage failed.