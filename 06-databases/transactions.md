# Transactions

## WHY?
Related data changes often need to succeed or fail together. Transactions protect invariants when operations fail midway or when multiple users update data concurrently.

## WHAT?
A transaction is a unit of database work with defined commit or rollback behavior. ACID describes common goals: atomicity, consistency, isolation, and durability. The exact guarantees depend on the database and its configuration.

## HOW?
An application begins a transaction, performs reads and writes, then commits; on failure it can roll back. Databases use mechanisms such as locks, logs, and multi-version concurrency control. Isolation levels determine which concurrent changes a transaction can observe.

## WHERE?
Transaction logic runs in the database engine, even when the application coordinates the sequence over a network. A transaction usually protects records within one database; coordinating across multiple services requires additional patterns.

## WHEN?
Use a transaction when several changes must preserve one invariant, such as deducting funds from one account while crediting another. Keep transactions short to reduce contention and avoid holding database locks while waiting on unrelated network calls.

## WHO?
Application code defines the intended unit of work; the database enforces its transactional guarantees. Concurrent users can submit updates at nearly the same time, and the database's isolation and conflict rules determine the outcome.

## WHAT IF?
If two users modify the same record, one may wait, fail with a conflict, or work from a version that is later rejected, depending on the database and isolation level. Use transactions, constraints, optimistic version checks, or retry logic to prevent silent lost updates. A client that loses its connection during commit may not know whether the commit succeeded, so operations may need idempotency or reconciliation.