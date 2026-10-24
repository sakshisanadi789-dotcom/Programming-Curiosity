# JavaScript

## WHY?
JavaScript became the standard programming language built into web browsers, enabling interactive behavior alongside HTML and CSS. Node.js later made the same language available for server-side programs.

## WHAT?
JavaScript is a dynamic language standardized as ECMAScript. Browser engines implement it, and Node.js embeds the V8 engine with server-oriented APIs; other runtimes and engines also exist.

## HOW?
An engine parses and executes JavaScript, often using just-in-time compilation. In a browser, JavaScript can interact with the document and browser APIs. In Node.js, it uses APIs for files, networking, and processes. Asynchronous event loops help handle many I/O operations without blocking on each one.

## WHERE?
JavaScript runs in browsers, servers, desktop applications, and other embedded runtimes. A browser application and Node server can communicate through HTTP APIs, even though they run in separate processes and may use different machines.

## WHEN?
Use JavaScript when building browser interfaces or when its ecosystem and runtime suit a backend or tool. Choose architectures and libraries according to the application's needs; sharing a language across client and server does not make them one security boundary.

## WHO?
ECMAScript is standardized through a standards process; browser vendors and runtime projects implement it. Web developers use JavaScript to build client behavior and server applications.

## WHAT IF?
If browser JavaScript makes a request to a server, the server must still validate and authorize it; client code is visible and modifiable by users. Slow CPU-bound JavaScript can block an event loop, so such work may need workers, separate processes, or another service.