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

## Lecture 3

The first assignment will be released this week.

### Memoization

Memoization is similar to caching. This is a optimization technique used to speed up programs by remembering results of expensive computations.

### Controller

A device controller is a chip or set of chips that physically control the device. Controlling the device is complicated, and the CPU can do other things, so the controller abstracts the device.

### Device

The device connects to the computer via the controller. It follows a standard when communicating with the computer.

### Device Driver

The device driver is a software which the OS needs to install to talk to the hardware. It's typically written by the controller manufacturer, following some abstraction defined by the OS. Drivers are often implemented as kernel modules, loaded on demand, running in kernel mode.

### Booting

1. When the computer is booted, the BIOS is started (Basic Input Ourpur Program) is a program on the motherboard
2. It checks the RAM, keyboard, and other devices (checks basically vitality of computer)
3. Record interrupt levels and I/O addresses of devices
4. Determine the boot device
5. Read/run primary boot loader program from first sector of boot device
6. Read/run secondary boot loader from potentially another device
7. Read the OS kernel from the active partition and start it
8. OS queries the BIOS to get the configuration information and initialize all device drivers in the kernel
9. OS creates a device table, and necessary background processes, and waits for I/O events

### Kernel

The central part or the "heart" of the OS.

- Located and started by the bootstrap program (boot loader)
- The only software that can talk to hardware
- Provides services to applications to system calls
- Much of the kernel is a set of rules

### Kernel Modes

- The modern CPUs support at least two privilege levels: kernel mode and user mode
- The mode can be switched by special instruictions
- When the CPU is in kernel mode
  - All instructions are allowed, all I/O allowed
- When CPU is in user mode
  - Only some operations are allowed, the rest are disallowed
  - Switching to kernel mode is disallowed
  - Illegal instructions returns traps (exceptions)
  - All applications run in user mode (including ones a part of OS)

### User Mode

Applications talk to the kernel to perform I/O via system calls

- system call = mechanism to call a kernel routine
- System call needs to include transition from user mode to kernel mode
- System calls are usually implemented using a special instruction
  - The instruction allows the switch from user to kernel mode to be safe
  - Common mechanism is invoking a trap (software interrupt)
  - When the kernel routine is done, application resumes in user mode

### I/O

Most system calls are blocking system calls. If you invoke the system call, the operating system will perform that operation and your application will only continue to run once the system call completes. Non-blocking system is a system call that doesn't block program continuation.

I/O can use busy waiting/spinning/busy looping for I/O. The CPU repeatedly checks to see if the device is ready. The issue with busy waiting is that the CPU is tied up while the slow I/O completes the operation, and you're wasting power/generating heat.

Busy waiting can be improved by taking a short sleep whenever we wait. Sleep could be detected by the OS, and the CPU could be then given to another program.

Some issue:

- Hard to estimate the right amount of sleep
- Program might end up running longer than necessary

### Interrupts

Interrupts are the best way of handling the I/O issue.

We basically ask the system/OS to send interrupt when the program is done. This approach assumes the I/O device supports interrupt. Most devices support interrupts, and if they don't, they can be connected through controllers that do.

Your application first runs. The interrupt happens, and the CPU switches to kernel code. The interrupt handler saves the CPU states, handles the interrupr, and restores the CPU state and switches back to user mode. The CPU the continues executing the original program in user mode.

Software interrupts are similar to hardware interrupts, but the source of the interrupt is the CPU itself. Some unintentional software interrupts include exceptions. Intentional software interrupts are traps. The trap occurs as a result of executing a special instruction. The purpose is to execute a predefined routine in kernel mode.

## Lecture 4

### Monolithic Kernels

Absolutely everything in the kernel runs in kernel mode. So running as fast as possible.

### Microkernels

Parts of kernels run in user mode. This increases communication/mode shifting, so slows things down.

### Dynamically loaded modules

- Modules are loaded on demand, when needed or requested
- Goal here is to really speed up the kernel bootup and easier to reconfigure on the fly

### Layered Approach to the kernel

- Kernel components organized into a hierarchy of layers
- Layers above constructed upon the ones below it
- Problems
  - Hard to define players, needs careful planning
  - Communication overhead
  - Not all problems can be easily adapted to layers

### Virtual Machines

A virtual machine is not a real machine. It is a emulated machine.

Emulation usually happens in software, but new computers usually have some hardware that helps with the emulation process.

- Bare-metal are virtual machines installed directly on a newly built computer
- Hosted is virtual machines that runs on top of another OS
- Hybrid is when a Linux kernel can function as a hypervisor through a KVM module
  - If you want to run Windows + Linux

A hypervisor is a software or hardware that manages VMs.

Benefits:

- Working on CPSC 457 assignments under Windows
- The host system is protected from the VMs
- VMs are isolated and safe from each other
- Multiple different OSes or versions can be running on the same computer concurrently
- Perfect vehicle for OS research and development
- System consolidation where you buy one server instead of many smaller ones

### System Calls

- OS provides services to applications, and we can access it through system calls.

Inside a kernel routine:

- OS saves application state
- OS performs requested operation
- OS switches back to user mode and restores application state
- After this the application resumes

The System Call is basically calling a API.

Wrappers are used to invoke system calls from higher level functions.

For example in C, to access system call, you can use the following code block:

```C
write(fd, buff, len)
```

The wrappers hide the implementation details.

Common wrappers include:

- POSIX APIs for Unix, Linux, and Mac OS X
- Win32 APIs for Windows
- Java APIs for Java Virtual Machine

`write()` is a wrapper for the `sys_write` system call signature.

The standard C library also provides many useful higher-level convenience functions, like `printf()`.

Examples of system calls:

```C
fd = open()
s = close(fd)
n = read()
n = write()
s = stat()
newpos = lseek()
```

The reason why need to open() a file before reading it is for performance reasons. If we open() first, we can store it in the cache, so the open will be faster.

### Tracing SYstem Calls

Running an application and logging all system calls.

- On Linux: `strace`

## Lecture 5

Not taking notes today, trying to finish assignment.

## Lecture 6

In the beginning, we were just going through some fork examples.

When forking, the variables will have their own deep copies regardless of the parent-child relationship. When forking, the child process gets its own copy of its memory.

Even when we use pointers pointing to a location address, it would be different between fork processes. It's pointing to the same virtual memory, but not necessarily the same hardware memory location.

A process in memory:

- Each process gets its own address space
  - Part(s) of memory available to a proces, decided by OS
  - On modern OSes it is a virtual address space isolated from other processes

How do we start an external program in Unix?

- We use `fork()` to create a clone
- We use the `exec()` command to replace the current process image with a new process image

With the `exec()`, we will pass the executable, argv, and environmental variables.

Example

```C
int main() {
  pid_t pid = fork();
  if (pid < 0) {
    fprintf(stderr, "Fork failed);
    exit(-1);
  }
  else if (pid == 0) {
    execlp("/bin/ls", "ls", "-l", NULL);
    // The piece of code under this should never run in the else if
  }
  else {
    printf("Waiting for child process")
    while (wait(NULL) > 0);
    printf("Child finished");
  }
}
```

C++ has provided us a more friendly wrapper function to create a new process.

```C
int main() {
  printf("Before ls.\n);
  system("/bin/ls -l");
  printf("After ls.\n");
}
```

If you run `pstree`, you can se all processes organized in a tree structure.

Init Process

- `init` is the first process started after booting
  - Maybe new systems used `systemd` instead of `init`
- `init` is the ancestor of all user processes
- Always has a pid = 1

Process Creation:

- There are many reasons for a process to create new processes
- During system initialization (boot)
  - Spawning background processes - daemon's, services, database server
- Application decides to spawn additional processes
- A user requests to create a new process
- Starting batch jobs

Address Space

- Each process has its own address space
- `fork()` duplicates address space, creating nearly identical identical copy of itself
- Next instruction is the same, usually "if/else"

Common Use Cases:

- Parent waits until child is finished (created via `fork()`), often used when child executes another program
- Parent continues to execute concurrently and independently on the child
- Parent continues to execute concurrently with child, but synchronizes with child sequentially. We will cover different synchronization mechanisms when we talk about threads.

Process Termination:

- Typical reasons for terminating a process
- Voluntary
  - Normal exit: Application decides to terminate, or user instructs an app to close (`exit()`)
  - Error exit - Application detects an error
- Involuntary
  - Fatal error - aka bugs in software
  - External - killed by another process (hitting control c)

If the parent processes dies before the child processes, the children needs to be terminated or re-parented. They are usually parented to the `init` processes. The behaviour can be changed.

Creating and deleting processes are expensive. If we can minimize the frequency of this, then that is better.

Process Scheduling:

- Process scheduling is a part of multitasking deciding which process gets the CPU next
- Typical objective is to maximize CPU utilization
- OS maintains scheduling queues:
  - Job queue, like priority queue
  - Ready queue, all processes that are ready to execute their next instruction
  - Device queue - Processes waiting for a particular device
