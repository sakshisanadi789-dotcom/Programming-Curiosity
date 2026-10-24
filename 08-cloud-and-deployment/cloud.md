# Cloud

## WHY?
Cloud services let teams obtain computing resources without purchasing and operating every physical machine themselves. They can provision capacity on demand and use managed services for common infrastructure needs.

## WHAT?
Cloud computing is on-demand access to shared computing resources over a network. Providers such as AWS and Azure offer virtual machines, storage, databases, networking, identity tools, monitoring, and higher-level managed services; they are not one giant computer.

## HOW?
Providers operate data centers and expose control planes and APIs for allocating resources. A deployed application runs on provider-managed physical hardware, often behind virtualization or container layers. Customers configure their application and data, while the provider manages parts of the underlying infrastructure according to the service model.

## WHERE?
Applications run in selected cloud regions and availability zones, on physical servers in provider data centers. Data location, network path, and replication choices affect latency, resilience, cost, and compliance.

## WHEN?
Cloud services suit workloads that benefit from managed operations, flexible capacity, or globally distributed infrastructure. On-premises hosting may be preferable for specific control, cost, regulatory, or latency requirements; cloud is not automatically cheaper or safer.

## WHO?
The provider secures and operates its infrastructure; customers remain responsible for their applications, identities, data, and service configuration. The exact division depends on whether a service is infrastructure, platform, or software as a service.

## WHAT IF?
If a region or service fails, applications designed for redundancy may fail over; otherwise they may become unavailable. Cloud services do not remove the need for backups, least-privilege access, cost controls, incident response, and tested recovery procedures. If the Internet vanished, remote cloud services would generally be unreachable, though local offline features and cached data could still work.