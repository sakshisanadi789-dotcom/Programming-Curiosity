# Request and Response

## WHY?
Distributed components need a defined way to ask for work and communicate its outcome. Requests and responses make that exchange explicit, including failures and metadata.

## WHAT?
A request is a message from a client asking a service to perform or report something. A response is the service's reply, usually carrying a status, headers, and optional data. JSON is common because it represents structured data in a text format supported by many languages, but it is not mandatory.

## HOW?
The client serializes its input, sends it over a connection, and waits for the service to respond. The server parses and validates the message, runs application logic, and serializes a result. A React client and a Python or Node server can interoperate because both follow the shared network and data-format contract, not because they share memory.

## WHERE?
Requests travel from the client through networks and may pass through proxies, gateways, or load balancers before reaching an application. The response follows a connection back to the client, which matches it to the request context.

## WHEN?
The client uses a request when it needs data or a remote action. It should set a timeout because networks and services can be slow or unreachable. Asynchronous requests let an interface remain responsive while waiting.

## WHO?
The client creates requests and handles responses; network infrastructure transports them; server components validate, process, and answer them. Operators monitor latency, errors, and service availability.

## WHAT IF?
If a response takes 10 seconds, the client may show a loading state or time out. If the server is down, the client gets a connection failure or gateway error rather than a normal response. Retries need limits and backoff, and should account for whether repeating the operation could duplicate its effects.