# Garbage Collection

## WHY?
Managed runtimes need a way to reclaim objects that a program can no longer use. Otherwise, short-lived allocations could accumulate until the process runs out of memory.

## WHAT?
Garbage collection is automatic memory management that identifies objects no longer reachable by a program and makes their storage reusable. It is not the same as deleting files or guaranteeing that memory is immediately returned to the operating system.

## HOW?
CPython primarily uses reference counting and supplements it with a cyclic garbage collector for unreachable reference cycles. Other Python implementations may use different strategies. Once an object is reclaimable, its memory can be reused by the runtime; the allocator may keep that memory for future allocations rather than return it to the OS immediately.

## WHERE?
Collection operates on objects in the running process. It does not clean persistent files, database records, or resources held by another process.

## WHEN?
Cleanup happens according to the implementation's memory-management rules, not necessarily at the exact moment a variable leaves scope. Programs should close external resources such as files and network connections explicitly, usually with context managers, rather than relying on garbage collection timing.

## WHO?
The runtime performs collection. Programmers help by avoiding unintended long-lived references, releasing external resources deterministically, and measuring memory use when it grows unexpectedly.

## WHAT IF?
If live objects consume more memory than the process can obtain, allocations can fail or the operating system can terminate the process. Garbage collection cannot reclaim objects that remain reachable, even if the program no longer finds them useful.