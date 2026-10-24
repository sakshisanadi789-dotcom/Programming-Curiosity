# Stack and Heap

## WHY?
Runtimes need ways to organize temporary call state and longer-lived objects. “Stack” and “heap” describe common memory-management roles, not two separate kinds of physical RAM.

## WHAT?
The call stack tracks active function calls and their frames, including return information and local execution state. The heap is a region used for dynamically managed objects whose lifetimes do not necessarily match one function call.

## HOW?
A function call adds a frame; returning removes that call's frame. In Python, local names belong to a function scope, while referenced objects are managed by the runtime and can outlive the function if something else still refers to them. Exact placement and optimization are implementation details; it is too simple to say every local variable is always on the stack and every object always on the heap.

## WHERE?
Both structures are backed by a process's virtual memory. The operating system maps virtual pages to physical memory as needed; stack and heap are not fixed physical chips.

## WHEN?
Stack-like call state is useful for nested calls with last-in, first-out lifetimes. Heap allocation supports objects that need flexible lifetimes, shared references, or sizes not known at compile time.

## WHO?
The language runtime and compiler implement calls and allocation; the operating system supplies the process address space. Programmers influence these behaviors through recursion depth, object creation, and reference lifetimes.

## WHAT IF?
Excessive or unbounded recursion can exhaust the available call stack and raise an error. Excessive heap allocation can exhaust process memory. The remedies differ: reduce call depth for stack exhaustion, and reduce or release retained objects for heap pressure.