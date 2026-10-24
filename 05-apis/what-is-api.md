# What Is an API?

## WHY?
An API lets one software component use another component's capabilities without reaching into its internal variables or implementation. This separation allows either side to change internally while keeping an agreed interface.

## WHAT?
An Application Programming Interface is a documented contract: available operations, accepted inputs, outputs, errors, and rules. An API can be a local library interface, an operating-system interface, or a network service; web APIs are only one kind.

## HOW?
A client sends a request through the API's defined interface. The provider validates it, performs work, and returns a result or an error. For a web API, the contract often specifies URLs, HTTP methods, headers, status codes, and data formats such as JSON.

## WHERE?
An API may be called inside one process, across processes on one machine, or over a network. A React application calling a Node.js or Python API usually sends an HTTP request; the server does not share the browser's JavaScript variables.

## WHEN?
Use an API when components need a stable boundary, independent deployment, access control, or reuse. A function call in one codebase may be simpler when no such boundary is needed.

## WHO?
API providers design and maintain the contract; client developers integrate with it; users depend on its behavior. API consumers should follow published limits, authentication rules, and versioning policies.

## WHAT IF?
If the provider changes the contract unexpectedly, clients can break. Versioning, backward-compatible changes, clear error behavior, and contract tests reduce that risk. An API boundary does not automatically make a system secure; each request still needs validation and authorization.