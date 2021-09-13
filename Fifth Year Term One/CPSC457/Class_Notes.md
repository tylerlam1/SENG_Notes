# CPSC 457

## Lecture One

Main Goals of this course:

- Understand fundamental operating system concepts like processes/threads/scheduling/memory/IO/file systems
- Learn interesting data structures and algorithms
- Make you a better programmer :)

An operating system is a piece of a software. It manages the hardware and software on a computer, and it makes the user's life easier through the following ways:

- Installing/running applications
- Running multiple applications concurrently
- Protecting from badly behaved applications
- Installing drivers for new hardware
- Managing files in directory structure
- Providing nice user features
- Provides services for controlling and allocating resources for application programs
- Provides controlled allocation for efficient and fair resource use

Tutorials in CPSC 457 are not optional.

## Lecture 2

An operating system from a developer perspective:

- It is the layer of software that provides apps a better, simpler, cleaner, model of the computer.
- Abstraction/generalization is key to managing complexity
- The OS understands the idea of files when writing to a disk. The underlying hardware only knows the space, no files.
- Then we use these abstractions to write applications and solve problems (like file editor, image viewer)
- Many OS concepts have abstractions, similar to OO programming

### Resource Manager

- OS can act as a resource manager
  - Two programs trying to run the same printer
  - Two programs running at the same time (scheduling)
  - Two programs each allocating memory
  - Managing conflicts among multiple programs or users
- OS can act as a control program
  - Controls execution of programs
  - Prevents errors and improper use

### History of operating system

- 1st generation of computers has no OS
  - A special person will build and design the OS for a company specific application
- 2nd generation of computers has transistors and batch systems
  - Building libraries and eventually used libraries to build operating systems
  - The idea behind batch system, whenever you have a bunch of operations you want to run on hardware, you batch them up. Like baking cookies in a stove.
    - In the beginning of computers, batch systems were implemented using punch cards. Multiple batch cards would be used to create a long line of tape (of code) will run a bunch of programs at once.
- 3rd generator of computers was where thing were minaturized. This is when integrated circuits became a thing
  - Computers had a lot more memory so you could do a whole bunch of cool things like below
  - Concepts
    - multiprogramming - A different job in each memory partition, CPU executes other jobs while waiting for the I/O of some jobs
    - Spooling - read jobs from cards to disk, load jobs from disk automatically, no more tapes. Multiple people can request services together
    - Time sharing - Multiple users using one computer simultaneously and interactively (programs running simultaneously)
- 4th generation of computer - Personal computers
  - Cheap mass produced computers
  - Nice GUI shells on top of the operation systems
  - Windows, Max OS, Linux + GNOME/KDE
- 5th generator of computers (current generation)
  - Packed mobile computers

### How do we run programs at the same time

- If we run things one at a time, we run program 1 on the CPU until its completely done. Then we run program 2, wait for it to finish. Then we run program 3. In this case, the CPU can be idle a lot waiting for I/O to complete.
- With multiprogramming, multiple programs are in memory. When lets say program 1 is waiting for I/O to be done, the CPU is given to program 2 to run.

### Spooling

Spooling is used when a quick device is trying to access a slow device. A computer (faster) will not talk to the printer (slow device). The computers will talk to spooler (intermediate) which is fast (like a print server).

Spooling can also be used to deal with deadlocks in concurrent programming.

### Hardware, booting, cache, kernel

Almost every computer will have a CPU, memory, video controller, USB controller, HD controller. All these components are connected using a bus.

A USB controller is a abstraction for all USB devices (keyboard, mouse).

### CPU

- The brain of the computer
- On board registers for faster computation
  - Instead of accessing memory for every instructions
  - Accessing information in registers is much faster than memory
  - There are general purpose registers (data and addresses) and special purpose registers.

### Instruction Cycle of CPU

A simple CPU cycle when stages operates sequentially.

1. Fetch an instruction from memory
2. Decode it from its type and operands
3. Execute it
4. Repeat

Fetch is usually the longest operation.

When fetching instructions sequentially, we complete all steps for instruction N, then does it for instruction N+1, and then instruction N+2.

Its assuming all stages takes the same amount of time, and notice that in this case that all units are often idle. We can improve the performance eby letting the units operate in parallel.

We can move things to work in parallel. While executing instruction N, the CPU could be decoding N+1, fetching instruction N+2, etc.

In the graph he shows, he assumes all stages take the same amount of time. But that is often not the case. When running in parallel, but a certain stage takes a longer period of time, there will be some idle time in the other stages.

Benefits of instruction pipeline:

- The CPU can work on more than one instruction at a time
- This allows the CPU to mask some of the memory access time

Cons:

- More complexity
- Have to deal with invalidated stages

### Multicore CPUs

- Each core can execute code in parallel with other cores
- Cores can share some hardware like cache, like same transistors (cache)
- Nearly all modern CPUs contain multiple cores

### Memory in computer

From fastest to slowest:

1. CPU registers
2. CPU cache
3. RAM
4. Disks
5. Tape backups

With memory, we can only store things and retrieve things. Memory is really slow in respect to the CPU.

Caching is a option to speed things up.

- Most heavily used data from memory is kept in a high speed cache located inside the CPU
- Cache hit: the data needed in the CPU is in cache
- Cache miss: The CPU needs to fetch the data from main memory

In the cache hierarchy, we got different levels:

- L1 is fastest - Feeds decoded instruction into CPU execution engine
- L2 is very fast - Stores LRU memory
- L3 is fast

Some CPUs have L4 cache.

Some multicore CPUs share the cache. In most cases, L2 is shared by cores, but L1 has individual cores.

Caching in general is to increase performance of slower memory/storage by adding small amount of fast memory.
To increase read performance:

- Keep copy of information from slow storage in cache
- Next time we need the info, check the cache first

To increase write performance:

- Write info to fast storage, and eventually write to slow storage
- Replaces multiple small writes with fewer big writes

Caching is fast but expensive, so its usually pretty small in general.
