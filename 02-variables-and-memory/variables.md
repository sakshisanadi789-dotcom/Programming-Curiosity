# Variables

## WHY?
Names make data easier to reuse and reason about than raw memory locations. They let code express intent, such as `total = price * count`, instead of manually tracking where each value is stored.

## WHAT?
A variable is a name associated with a value according to a language's rules. In Python, a name is best understood as a binding to an object, not as a box that permanently contains the value.

## HOW?
For `x = 10`, Python evaluates `10` as an integer object and binds the name `x` to it. For `x = 20`, it binds `x` to the object for `20`; the old object can be reclaimed only when nothing still refers to it. In `a = b = c = 100`, the right-hand expression is evaluated once and all three names are bound to that result. This does not mean three independent copies; integers are immutable, and code should not rely on object identity for equal values.

## WHERE?
Names live in namespaces, such as a function's local namespace or a module's global namespace. Objects occupy memory managed by the Python implementation. Python normally exposes names and values, not raw physical addresses.

## WHEN?
Use a name when a value needs to be described, reused, or updated. Rebinding a name changes what it refers to; mutating a mutable object changes that object and can be visible through every name that refers to it.

## WHO?
The language defines assignment and scope rules. The Python implementation creates and manages objects, while the programmer chooses names and decides when to rebind or mutate them.

## WHAT IF?
If another variable still refers to the old object, rebinding `x` does not remove that object. If an object is mutable and several names refer to it, changing it through one name can affect observations through the others.