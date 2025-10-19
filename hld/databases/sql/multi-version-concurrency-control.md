# Multi Version Concurrency Control

A way to provide higher concurrency for read and write.

While reading give a snapshot of database to read.

Postgres uses it.

Benefit of this is that it allows writes without blocking reads and reads without blocking writes unlike traditional locking mechanisms.
