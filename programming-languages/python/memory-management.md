# Memory Management

**Object Heap**

All python objects reside here, its managed by **Python Memory Manager**

**Allocators**

Which perform the allocation

1. malloc
2. pymalloc ( optimized for small objects - uses a fixed size 512KB / 1024KB blocks allocation for objects called in a memory area called **arena** )

**Allocation Domains**

Different memory allocation strategies for different purposes.

1. Raw - Buffer Memory for GIL free operation
2. Mem - Buffer Memory for Op with GIL
3. Object - For Python Objects
