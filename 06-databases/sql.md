# SQL

## WHY?
Programs need durable, shared data that survives process exits and can be queried or updated by multiple users. A database provides storage and rules beyond the lifetime of in-memory variables.

## WHAT?
SQL is a language used with relational databases. A table organizes records into rows and named columns; a primary key identifies a row uniquely. Different database products implement SQL with their own features and variations.

## HOW?
An application sends a SQL statement through a database driver. The database parses and plans the statement, reads or changes records, and returns results. For example, `INSERT` adds data, `SELECT` reads it, `UPDATE` changes it, and `DELETE` removes it. Constraints can enforce rules such as uniqueness and required values.

## WHERE?
Data is stored by the database process in files or managed storage, often on persistent disks. A database may run on the same machine as an application or on a separate server; the application normally accesses it through a driver and network protocol.

## WHEN?
Relational databases are a strong fit when structured relationships, constraints, joins, and transactions are useful. Keep application state in variables for temporary computation; use a database when data must persist, be shared, or be queried reliably.

## WHO?
Application code issues queries; the database engine manages storage, concurrency, and access rules. Database administrators and developers design schemas, permissions, backups, and operational monitoring.

## WHAT IF?
If a process crashes before a transaction commits, the database uses its recovery mechanisms to preserve consistency according to its guarantees. If a database is unavailable, writes may fail; applications need clear error handling and should not claim data was saved until they receive confirmation.