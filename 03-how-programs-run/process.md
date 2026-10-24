# Process

## WHY?
An operating system needs a managed unit for running a program, assigning it resources, and keeping its activity separate from other programs. That unit is a process.

## WHAT?
A process is a running instance of a program, with its own virtual address space and operating-system resources. A program file is passive; a process exists while the operating system is executing it.

## HOW?
When you enter `python app.py`, a shell parses the command and locates Python using its command search rules, commonly `PATH`. The shell asks the operating system to start the Python executable with `app.py` as an argument. The OS creates a process, loads the executable, and gives it resources; Python then reads and executes the script. Exact launch details vary by OS and shell.

## WHERE?
The process runs under the operating system on a computer. Its virtual memory may map to physical RAM and, under pressure, some pages may be backed by storage. A process can access remote services but remains a local process.

## WHEN?
Processes are created when applications or commands are launched and end when they exit, are terminated, or crash. A server may keep a process running to handle many requests over time.

## WHO?
The shell starts the requested command; the operating system creates and schedules the process; the Python interpreter executes the script. Users or supervisors can observe, signal, or stop a process according to permissions.

## WHAT IF?
If Python cannot be found, the shell reports a command-resolution error. If the script fails, Python may exit with an error and status code. The OS can also terminate a process for resource exhaustion or an external signal; logs and exit status help diagnose the cause.