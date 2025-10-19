# RabbitMQ

Smart Broker - Dumb Consumer

Push Model

Multiprotocol service queue ( AMQP, STOMP, MQTT )

Publisher -> Exchange -> (through bindings) -> Queues -> Consumer

**Exchange**

Exchange is the router which routes messages to various queues based on strategy used.

1. **Direct** - Send to a specific queue
2. **Fanout** - Send to all queues
3. **Topics** - Shared pattern

**Connection**

An authenticated actual TCP connection

**Channel**

Virtual connection on top of a connection

**Dead Letter Exchange**

Gets undelivered messages from queue.

Any exchange can become a dead letter exchange if we specify header `x-dead-letter-exchange` on a queue with an exchange name.

**Alternate Exchange**

Gets unroutable messages from exchange.

If a message is unroutable then the exchange will route the message to this exchange ( used for logging with a fanout )
