# Processes and Memory
In a O/S:
* A OS starts a process
* A process starts as one thread
* One thread can spawn other threads
* OS schedules threads

Each Process:
* Has one copy of the code
* Each process has one copy of static, global, and literal data
* Each process has one shared block of memory for the heap
* Each thread has separate memory for its stack

CPU Scheduling:
* CPUs run threads
* Common CPUs 2-4 cores
* A CPU runs threads from one or more processes
* Scheduling is done by OS; process is mostly unaware

## Shared Memory
A shared memory sofware architecture is one in which memory is accessed simultaneously by multiple threads of execution, with the intent of enabling communication while keeping a single copy.

Badly parallelized code, results are:
* Random order of values in output vector
* Occasional crash
* Undefined behaviour leaving data structures in unknown states

This leads to non-determinism.

Thread-safe is code that can be run concurrently in more than one thread while producing the correct results. There are a couple strategies we can use to achieve this:
* Mutex
* Preallocate memory
* Better code design

```c
std::mutex my_lock;
for (size_t ii = 0; ii < values.size(); ++ii) {
    int v = values.at(ii);
    threads.emplace_back([v, &my_lock, &squares]) {
        my_lock.lock();
        squares.push_back(v * v);
        my_lock.unlock();
    }
}
```

Preallocating memory:
```c
squares.resize(values.size());
for (size_t ii = 0; ii < values.size(); ++ii) {
    threads.emplace_back([ii, &values, &squares]) {
        squares[ii] = values.at(ii) * values.at(ii);
    }
}
```

An idempotent operation is one that can be repeated without changing the result. In other words, the effect of repeating the operation any number of times is the same as having done it once.

For general better code design:
* Write idempotent functions
    * All inputs are immutable
    * The return value holds all results
* Follow this pattern throughout your code
* Except in the one function that coordinates the concurrency
* Clearly document the concurrency
* Write code that is easy to understand and read

Sometimes non-determinism is okay, but document it and choose an appropriate data structure like a set.

## Message Passing
Message passing is a software architecture for concurrency where the communication is done by sending messages to other threads over a unidirectional channel. The function can be anything from a function to a signal to data (like a struct).

Generally, it is recommended to use a library to perform message passing.

Message passing uses shared memory for the channel. The core concept in message passing is that threads only operate on their local data, not data that has shared ownership across multiple threads. The advantage with shared memory is that there is low overhead, keeps a single copy of the data, and synchronization of memory access. On the contrary, message passing establishes clear boundaries, easier to reason about and debug, and generally requires making a copy of data.