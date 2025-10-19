# CAP Theorem



Consistency, Availability and Partition Tolerance. You can at best have two of those.

1. **CA** **-** Data can be trusted and is highly available ( single reader, one writer )
2. **CP** **-** Data can be trusted always ( multi reader, one writer )
3. **AP -** Data is highly available but isn't really consistent. ( multi reader, multi writer )

Its not possible to have CA both. You can either do CP or AP.

Partitioning can not be avoided, its just going to happen.

Availability is relative.

Consistency cant really be instant.
