# REST API

## WHY?
REST is a set of architectural constraints for networked systems. Its conventions make HTTP APIs easier to understand and allow generic clients, caches, and infrastructure to work predictably.

## WHAT?
REST organizes a service around resources identified by URLs and uses a uniform interface, commonly HTTP. A RESTful design aims for stateless requests, cache-aware responses, and a layered architecture. Many services called “REST APIs” follow only some of these constraints.

## HOW?
Clients use HTTP methods such as GET, POST, PUT, PATCH, and DELETE on resource URLs. GET retrieves a representation; POST commonly submits data or creates a resource; PUT replaces a resource representation; PATCH applies a partial change; DELETE requests removal. Status codes communicate outcomes. The API contract determines precise behavior, and safe or idempotent semantics matter for retries.

## WHERE?
REST APIs are usually exposed over HTTP between browsers, mobile apps, other services, and backend systems. They may sit behind gateways, authentication services, and load balancers.

## WHEN?
REST conventions suit many resource-oriented services and public web APIs. Other styles, such as GraphQL, RPC, or event messaging, may better suit different query, interaction, or throughput needs.

## WHO?
API designers define resources and method semantics; server developers implement them; client developers consume them. HTTP specifications define general method behavior, while each API documents its own resource contract.

## WHAT IF?
If an endpoint is slow or unavailable, clients should handle timeouts and error statuses. A request can be modified by a client or attacker, so servers must validate inputs and enforce authentication and authorization on every protected operation; CORS is not access control for the API itself.