# Write Ahead Log

#### Write Ahead Log

Provides integrity while speeding up writes because only WAL needs to be flushed to disk to acknowledge a commit.

Even if something goes wrong WAL assures that we can recover with the log.

#### Replication Slot

A way to make sure that master has history of WAL even when replicas are disconnected.
