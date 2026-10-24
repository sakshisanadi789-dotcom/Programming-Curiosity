# Indexes

## WHY?
Without an index, a database may need to scan many or all rows to find matching records. Indexes speed up selected reads by keeping an additional searchable structure.

## WHAT?
An index is auxiliary data maintained by a database, often a tree or hash-based structure, that maps indexed values to rows. A primary key is commonly backed by a unique index, but indexes can also cover other columns or expressions.

## HOW?
When data changes, the database updates relevant indexes. A query planner decides whether an index is useful based on the query and available statistics. An index can help filters, joins, and ordering, but the database still has to fetch row data when it is not covered by the index.

## WHERE?
Indexes are stored and maintained alongside database data, consuming memory and persistent storage. They may be local to a table or distributed according to the database's architecture.

## WHEN?
Add indexes for frequent, selective query patterns and verify their value with query plans and measurements. Indexes are not free: they add storage and can slow inserts, updates, and deletes.

## WHO?
Database designers and developers choose indexes based on actual access patterns; the query optimizer chooses whether to use them for each query. Operators monitor index size and performance.

## WHAT IF?
Too few indexes can make reads slow; too many can waste storage and make writes expensive. A poorly chosen index may not be used, so inspect execution plans instead of assuming every index improves every query.