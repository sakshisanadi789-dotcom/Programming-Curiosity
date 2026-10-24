# Threads

## WHY?
Threads let a process organize multiple flows of work that can make progress concurrently, such as serving requests while doing background work. They can share process data without separate process-level communication.

## WHAT?
A thread is a schedulable execution path within a process. Threads in one process share its address space and many resources, but each has its own call stack and execution state.

## HOW?
The operating system schedules threads on available CPU cores. On one core, it can switch between them; on multiple cores, threads may run in parallel. Shared mutable data needs coordination, such as locks or message passing, to avoid race conditions.

## WHERE?
Threads live inside a process and use its memory, while maintaining separate stacks. The OS and language runtime determine how threads map to native execution resources.

## WHEN?
Threads can help with concurrent I/O and workloads that benefit from parallel execution. For Python, behavior depends on the implementation and build: conventional CPython uses a Global Interpreter Lock that limits simultaneous execution of Python bytecode by threads, while I/O operations can still overlap; free-threaded CPython builds are also available.

## WHO?
The operating system schedules native threads, and the language runtime may manage or abstract them. Programmers decide how work is split and must protect shared state or avoid sharing it.

## WHAT IF?
Poor coordination can cause races, deadlocks, or inconsistent data. Adding threads does not automatically make a program faster; measure the workload and consider processes, asynchronous I/O, or simpler sequential code when they fit better.