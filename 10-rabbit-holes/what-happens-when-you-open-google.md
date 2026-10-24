# What Happens When You Open Google?

## WHY?
A browser needs to turn a human-readable site name into a network connection, request content, and render the result. Each step uses protocols so independently operated systems can cooperate.

## WHAT?
Opening `google.com` may involve DNS lookup, IP routing, a secure transport connection, an HTTP request, server-side processing, and a response containing page resources. The exact infrastructure and sequence vary by browser, network, region, and current service configuration.

## HOW?
1. The browser checks relevant caches and asks a DNS resolver for an address if needed.
2. It connects to an address, commonly using TCP plus TLS or QUIC, and validates the site's certificate for HTTPS.
3. It sends an HTTP request containing the hostname and requested path, along with headers and possibly cookies.
4. Routers forward packets across networks. A content-delivery edge, proxy, or load balancer may receive the request before application services.
5. The service processes the request and may consult caches, databases, or other services. It returns an HTTP response; the browser downloads additional resources and renders the page.

## WHERE?
The browser runs on your device; DNS resolvers, routers, data centers, and edge servers may be in different organizations and locations. Packets can take different routes in each direction, and a service may answer from a nearby edge rather than one central machine.

## WHEN?
DNS answers, TLS sessions, connections, and web resources may be cached or reused. If a valid cache entry exists, some steps can be skipped; otherwise the browser performs the lookups and handshakes needed for a new request.

## WHO?
The browser and operating system initiate the request; DNS operators resolve names; network providers forward traffic; certificate authorities help establish domain identity; and the website's infrastructure processes the request.

## WHAT IF?
If DNS, routing, TLS validation, or the service fails, the browser shows an error rather than a page. If the Internet connection disappears, remote Google services are unreachable; local browser files or cached content may remain available, but they cannot provide fresh remote results.