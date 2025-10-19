# Read Types & Transaction Isolation Levels

#### Read Types

**Dirty Read**

Reading values of another uncommitted transaction

**Non Repeatable Read ( dirty UPDATE )**

Upon re-reading the data it has already read it finds that it has changed ( same row )

**Phantom Read ( dirty INSERT / DELETE )**

Upon re-executing the query it gets more or less records ( different number of rows )

#### Transaction Isolation Levels

**Read Uncommitted**

All three possible

**Read Committed**

Phantom & Non Repeatable reads possible

**Repeatable Read**

Only Phantom reads possible

**Serializable**

All three impossible
