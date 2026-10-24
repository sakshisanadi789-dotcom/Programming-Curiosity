# DNS

## WHY?
People remember names more easily than numeric network addresses. DNS provides a distributed way to look up the records services publish for those names.

## WHAT?
The Domain Name System is a hierarchical system of records and servers. A DNS lookup for `google.com` can return one or more IP addresses, though the exact answer may vary by location, time, and service configuration.

## HOW?
A browser or operating system first checks caches. If it needs an answer, a DNS resolver asks other DNS servers as necessary, following the hierarchy from root and top-level-domain servers to authoritative servers. The resolver returns the record and caches it according to its time-to-live.

## WHERE?
DNS resolvers may run on a device, router, ISP network, company network, or public DNS service. Authoritative DNS servers publish records from distributed infrastructure around the world.

## WHEN?
DNS is typically consulted when an application needs to connect to a hostname and has no usable cached answer. Records can change, but caches may continue using an older answer until its TTL expires.

## WHO?
Domain owners configure records through registrars or DNS hosting providers. Recursive resolvers perform lookups for clients; authoritative servers provide the published answers.

## WHAT IF?
If DNS is unavailable or records are incorrect, a client may fail to find the service even when its server is healthy. Cached records can temporarily mask an outage or delay a change from taking effect.