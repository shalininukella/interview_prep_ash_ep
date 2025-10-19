# GIL, Async and Concurrency

#### IO and CPU Bound

If CPU is idle mostly and some read/write is happening the code is IO bound.\
If CPU is executing some instructions mostly then code is CPU bound.

#### OS Signals

SIGINT ( ctrl + C ) - Meant to be handled by the program\
SIGTSTP ( ctrl + Z ) - Stop a program - meant to handled by the program\
SIGKILL ( kill -9 ) - Kill a program forcefully

#### GIL

A lock in CPython that prevents simultaneous bytecode execution in a multithreaded execution environment.\
Its released every 100 bytecode instructions by threads to make sure other threads dont starve in an IO bound case.\
Python C extensions in numpy, numba etc. do manually release GIL.

#### Multi Threading

Multiple threads executing a IO bound job.

Threads share parent process's memory segment but have a separate stack so communication is easier.

**Daemon Threads**

Background threads that die as soon as the main thread dies, they dont hold the main process from exiting.\
**SIGINT** will kill this thread.\
**SIGTSTPT** will put it in background ( we can use fg to bring it back to life if the shell is still active )

**Non Daemon Theads**

**SIGINT** will not kill this thread.\
**SIGTSTPT** will put it in background ( we can use fg to bring it back to life if the shell is still active )

**Create a thread in python**

```python
from threading import Thread

class MyThread(Thread):
    def __init__(self, arg1, arg2, *args, **kwargs):
        super().__init__(*args, **kwargs)
    
    def run(self):
        ...

mt = MyThread(arg1=1, arg2=2)
mt.start()
mt.join()
```

**Synchronization primitives**

1. Mutex - `threading.Lock`
2. Semaphore
3. RLock
4. Conditions
5. Barriers

#### Multi Processing

Multiple processes to do a job.

Processes dont share same memory so we need some way to communicate which is called Inter Process Communication ( IPC )

**Create a Process in Python**

```python
from multiprocessing import Process

class MyProcess(Process):
    def run(self):
        ...
```

**Inter Process Communication**

1. **Managers -** A server process that handles communication between different processes. It creates proxy objects that can be shared over a network as well.
2. **SharedMemory -** A memory map shared across processes where they can read and write binary buffers
3. **Pipes -** Connection between two objects, returns two Connection objects that can be called recv and send upon.
4. **Queues -** pub sub implemented using pipes with semaphores.

**Fork, ForkServer and Spawn**

1. **Fork -** Copies entire memory to child except threads and their locks. ( fast, bloated )
2. **Spawn -** Entirely new python process no carry overs. ( slow, compact )
3. **ForkServer** **-** Forks parent process and trims down memory, then each time new process needs to be created its created by forking this new `forkserver` process by passing it the child callable\
   ( fast, compact )

#### Asynchronous

User defined cooperative multitasking primitive

1. **Event Loop** - A single threaded program that executes all callbacks and tasks in this thread in a loop.
2. **Task -** `asyncio.create_task` is a wrapper of future used to schedule a coroutine in a running event loop.
3. **Future -** Special low level awaitable object that represents result of async op.
