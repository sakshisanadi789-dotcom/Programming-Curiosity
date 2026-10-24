# What Happens When You Run Code?

## WHY?
Running a source file requires several layers to cooperate: the command interface, operating system, language runtime, and processor. Following the path explains why an error can occur before Python starts, while reading the file, or during the program's work.

## WHAT?
For `python app.py`, the command names a Python executable and passes `app.py` as an argument. The operating system starts Python as a process; the interpreter reads the file and executes its code.

## HOW?
1. The shell parses the command and resolves `python` using its command lookup rules, commonly the `PATH` environment variable.
2. The shell asks the operating system to start the Python executable with `app.py` in its argument list.
3. The OS creates a process, maps the executable and libraries into its virtual address space, and schedules its thread.
4. Python opens and parses the source. In CPython it compiles code to bytecode, then the Python virtual machine evaluates that bytecode.
5. The program calls libraries and OS services as needed. Text written to standard output is passed through the process's output handle to the terminal, where it becomes visible.

## WHERE?
The shell and Python process run on the local computer. The process's memory is managed by the OS, and the CPU executes native instructions from Python and its runtime. A program can also make requests to remote systems during execution.

## WHEN?
Some work happens at launch, such as executable lookup and process creation; other work happens as Python reaches each statement. Imports, input, network calls, and output may trigger additional file or OS activity.

## WHO?
The shell interprets the command, the OS creates and schedules the process, Python parses and executes the source, libraries provide functionality, and the CPU performs instructions. The terminal displays output but does not itself execute the Python program.

## WHAT IF?
If the command cannot be resolved, Python never starts. A syntax error prevents the affected source from running; an exception may stop execution later. The OS can report a process exit code, and a supervisor can detect an exit and restart the process. For a remote program, a timeout or missed heartbeat cannot always distinguish a crash from a slow or partitioned network.