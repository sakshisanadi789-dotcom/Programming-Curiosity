# HTTP

## WHY?
Web clients and servers need a shared protocol for requesting resources and returning results. HTTP defines this exchange independently of the page's visual appearance.

## WHAT?
HTTP is an application-layer request/response protocol. A request includes a method, target, headers, and sometimes a body; a response includes a status code, headers, and sometimes a body. HTTP is stateless by design, while cookies or other application mechanisms can associate requests with a session.

## HOW?
When a user clicks a website button, browser code may create an HTTP request. It is sent over a transport connection, commonly TCP with TLS for HTTPS or QUIC for HTTP/3. The server routes it to application logic, which may consult other services, and returns a response. The browser then interprets the status, headers, and body.

## WHERE?
The request passes from the browser through network interfaces, routers, providers, and server infrastructure. The server may be a reverse proxy or load balancer in front of application processes rather than one physical machine.

## WHEN?
HTTP is used for web pages, APIs, and many other network services. Methods express intended operations: GET retrieves, POST submits or creates, PUT replaces, PATCH partially modifies, and DELETE requests removal; exact application behavior is defined by the service.

## WHO?
The client constructs requests; DNS and network systems help reach the host; proxies may forward traffic; server software and application code produce responses. The browser associates a response with its outstanding connection or request context.

## WHAT IF?
Slow or failed requests can time out, return an error status, or be retried. A retry is not always harmless, especially for operations that change data. Clients should handle status codes, timeouts, and connection failures rather than assume every response succeeds.