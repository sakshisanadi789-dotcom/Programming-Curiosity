# NoSQL

## WHY?
Some workloads need data models, distribution patterns, or scaling approaches that do not fit a traditional relational design well. NoSQL systems provide alternative models, often with tradeoffs in query flexibility or consistency behavior.

## WHAT?
“NoSQL” covers several database families, including document, key-value, wide-column, and graph databases. It does not mean “no structure” or “no SQL-like queries”; each system has its own schema and query model.

## HOW?
A document database may store JSON-like records; a key-value store retrieves values by key; a graph database represents nodes and relationships. Many NoSQL systems distribute data across machines using partitioning and replication, with consistency guarantees that vary by product and configuration.

## WHERE?
NoSQL databases are used in cloud services, caches, content systems, event data pipelines, and applications with large or flexible datasets. The right placement depends on whether the system is the source of truth, a cache, or an index.

## WHEN?
Choose a specific NoSQL system when its data model and operational characteristics suit measured requirements. Relational databases may be simpler when strong relational constraints, joins, and multi-record transactions are central.

## WHO?
Application developers choose access patterns and model data; database operators configure availability, replication, and backups. Product teams should define consistency requirements rather than treating “NoSQL” as one uniform capability.

## WHAT IF?
If a replica is delayed or a partition is unavailable, a read may be stale or a write may be rejected, depending on the system's guarantees. Understand the chosen database's failure and consistency behavior before relying on it for critical data.