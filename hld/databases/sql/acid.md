# ACID

**Atomicity**

A transaction is all or nothing

**Consistency**

Force constraints ( eg. foreign key, primary key, triggers etc. )

**Isolation**

Transactions should look like if its the only transaction happening ( Ideally Serializable, practically Repeatable Read, Performant Read Commit, Consistency Violating but very performant Read uncommitted )

**Durability**

A transaction should persist despite outages ( done through WAL )
