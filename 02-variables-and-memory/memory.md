# Memory

## WHY?
Programs need temporary working space for instructions, values, and state. Memory makes active computation fast, while persistent storage keeps data after a program exits or power is removed.

## WHAT?
RAM is volatile working memory used by running programs and the operating system. Storage, such as an SSD, is designed to retain files. A memory address identifies a location in an address space; modern processes usually see virtual addresses that the operating system and hardware map to physical memory.

## HOW?
When a process needs memory, its runtime and operating system arrange addressable regions for code and data. The processor loads and stores values through addresses. Python layers objects, references, and namespaces over this, so ordinary Python code does not need to manipulate addresses directly.

## WHERE?
Python objects and interpreter state are held in a process's memory while it runs. The operating system gives each process a virtual address space, which helps isolate it from other processes. The exact object layout depends on the Python implementation and build.

## WHEN?
RAM holds active state; files and databases are used when data must persist or be shared beyond one process. Programs may also use caches and memory-mapped files for particular performance or access patterns.

## WHO?
The CPU reads and writes memory, the operating system manages process address spaces, and the language runtime requests and organizes allocations. The programmer influences usage by choosing data structures and how long objects remain reachable.

## WHAT IF?
If memory pressure becomes high, the operating system may reclaim caches, slow down, refuse allocations, or terminate a process. A process can also fail with an allocation error. RAM is not an infinite extension of disk storage, and swapping to disk is much slower.