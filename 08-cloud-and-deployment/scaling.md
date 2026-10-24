# Scaling

## WHY?
An application that works for one user may become slow or unavailable when demand grows. Scaling adds capacity or changes the design so the system can handle more users, data, or requests within acceptable limits.

## WHAT?
Vertical scaling gives one machine more resources; horizontal scaling adds machines or instances. Real systems often combine both with caching, queues, databases, and content-delivery networks. A million users do not necessarily mean a million simultaneous requests, so capacity planning uses measured traffic and workload patterns.

## HOW?
Measure bottlenecks first. A load balancer can spread stateless requests across instances; caches and CDNs reduce repeated work and serve media near users; queues absorb bursts; databases may use indexes, replicas, partitioning, or sharding. Scaling one component can move the bottleneck elsewhere, and distributed components introduce coordination and failure modes.

## WHERE?
Capacity may be added across application servers, databases, regions, and edge networks. An uploaded photo is typically sent to an application service, validated, stored as an object in durable storage, and served later through a CDN; metadata and access rules may be stored in a database. The exact design varies by product.

## WHEN?
Scale when measurements show resource saturation, unacceptable latency, or a need for higher availability. Begin with simpler optimizations and load testing; “buy one huge computer” can help temporarily but has cost, capacity, and failure limits.

## WHO?
Application developers design statelessness and data access; infrastructure teams operate capacity and networking; database and security specialists protect state and data. Services such as messaging apps also require identity, message routing, durable queues or logs, databases, media storage, push notifications, and abuse prevention.

## WHAT IF?
If an instance crashes, a load balancer can route new requests to healthy instances and an orchestrator can replace the failed instance; in-flight work may still be lost. If two users edit the same record, database transactions and conflict handling are needed. During a total Internet outage, only features whose code and data are available locally can continue; remote APIs and cloud-hosted data cannot be reached.