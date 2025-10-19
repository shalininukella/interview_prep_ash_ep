# Kafka

Dumb broker - Smart Consumer

Pull Model

Durable topic based message exchange

Durable - because it persists messages in partitions

**Consumer Groups**

Set of consumers to consume from same topic to provide parallelization

**Topic**

A collection of partitions based on which messages are pub subbed

**Partition**

A division of topic.\
1\. Ordered\
2\. Every message has a different offset in a parittion with a unique sequence id\
3\. Append only\
4\. Different consumers and producers can write / read from different paritions to boost scalability and parallelism.

**Log Compaction**

Process that ensures only latest version of a record in a partition
