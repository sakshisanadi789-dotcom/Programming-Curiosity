# IP

## WHY?
Connected devices need a common way to identify network destinations and move data between networks. IP provides addressing and routing at the Internet layer.

## WHAT?
An IP address identifies a network interface or endpoint in a particular network context. IPv4 uses 32-bit addresses; IPv6 uses 128-bit addresses. An address is not necessarily a permanent identity for a person or device.

## HOW?
DNS can provide an address for a hostname. The client sends IP packets through local routers and its internet provider; routers forward packets toward the destination based on routing information. A port in the transport layer, such as TCP or UDP, helps deliver data to the right application endpoint on a host. IP itself does not guarantee delivery or order.

## WHERE?
Packets cross local networks, routers, provider networks, and possibly content-delivery networks before reaching a service. The route can change, and requests and responses need not follow identical paths.

## WHEN?
IP is used whenever networked systems communicate across IP-based networks. Ports matter when multiple services or connections share the same host address; familiar examples include TCP port 443 for HTTPS and 53 for DNS, though protocols can use other configurations.

## WHO?
Network operators allocate and route address ranges; routers forward packets; transport protocols and operating systems deliver data to sockets. Applications choose the destination host and service they need.

## WHAT IF?
If routing fails, packets can be delayed or lost. Firewalls, address translation, and network policy can block or rewrite traffic. A successful DNS lookup alone does not prove that a server is reachable or accepting connections.