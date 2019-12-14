# ENCM 511

## Abbreviations

* CPU = Central Processing Unit
* CCU = Computer Control Unit
* DMA = Direct Memory Access
* CLLR = Compile, Link, Load, and Run
* PSP = Personal Software Plan
* PIP = Personal Improvement Plan
* LSD = Little Stupid Details
* WIDFI = When in doubt, fake it
* WAIL = Worry about it later
* WAIN = Worry about it now
* PEP = Personal Exam Process
* CC = Condition Code
* PF = Programmable Flag
* PF = Port F
* GPIO = General purpose Input/Output
* JSR = Jump to Subroutine
* RTS = Return to Subroutine
* REB = Logic Lab Remote Extender Board
* PSPP = Practice Safe Programming Practices
* JEADI = Just Enough Additional Development Interfaces
* MVP = Minimum Viable Product
* ICE = In Circuit Emulator
* IRQ = Interrupt Request Line 
* MOSI =  Master out, Slave In
* KIS = Keep it Simple
* COTAAT = Change only one thing at a time
* TTCOS = Time-Triggered Cooperative Operating System
* RETS = Return from subroutine
* TFD = Test First Development
* TLD = Test Last Development
* GQM = Goal, Question, Metric
* EVT = Event Vector Table
* FILO = First In Last Out
* ASTAT = Arithmetic Status
* SPI = Serial Peripheral Interface
* KFC = Keep Fingers Crossed
* PPP = Profound Procrastinated Programming

In order to set up the GP Timer, check out the reference sheet. 

```c
void initialize_And_Start_Libraries() {
    Init_GP_Timer(GPTIMER);
    Start_GP_Timer(GPTIMER);
}
```

Basically, you go ahead and initialize and start the GP Timer. The GP Timer was used in Lab 4 for the temperature sensor.

Here are the differences between the GP Timer, CoreTimer and the WatchDog Timer:
* The CoreTimer acts like an hourglass -- just counts down from a particular time and sends a done signal
* The GP Timer has a connection to the outer world (not sure what that means)
* Watchdog Timer is basically like a CoreTimer, but it can take control of the entire system if needed

Let's look a little bit at the differences between Harvard and Von-Neumann Architecture.

### Harvard Arhitecture and Von-Neumann

Harvard Architecture has TWO address busses,TWO data busses, and TWO Control Busses. It also has a ROM and a RAM unlike the von-neumann architecture.

The Von-Neumann Architecture has ONE address bus, ONE data bus, and ONE Control Bus. The Control Bus sends timing commands to the memory and peripherals and gets acknowledgement signals back.

When you're taking a look at the standard instruction cycle of a microprocessor, you know that these are typically the instructions taken:

Reset -> Fetch -> Decode -> Execute -> Writeback 

By uselining Pipelining, we can speed things up. basically, we can go ahead and fetch another instruction while decoding the first one, fetch another instruction while the first one is executing, and so on. The only caveat is to ensure there is enough memory.

It is important to keep in mind that each stage must be as long as the longest instruction stage. The solution is using RISC (Reduced Instruction Set Processors) which no complex instructions.

On the Von-Neumann processorm, you cannot fetch data and instructions at the same time because there is only one data bus and one address bus. However, the Harvard Processor can perform this process of fetching data and instruction at the same time as there are two data busses and two address buses.

SISD - Single Instruction Single Data
SIMD - Single Instruction, Multiple Data

Basically, one instruction in SIMD does things with R registers with memory location P in first hald cycle of processor clock, and does things will the S (shadow) registers in the second half of the processor clock

At the end, the programmer must combine R and S results. Automatically handled by the optimizing compiler.

MIMD - Multiple Instruction Multiple Data

VILW - Variable Length Instruction Word - To save program memory space, some processors have 16-bit and 32-bit versions of the same COMMON instruction.

### Files Generates

The CrossCore Compiler uses .cpp and .asm files to create .doj files. The Linker uses the .doj and .dlb files to create the .dxe file. While the .dxe is an executable, the .dxe must become a .ldr file to go to the loader in the processor flash memory.

In general, here are the steps:
* The preprocessor takes the source files (.cpp) and converts them into expanded source files. The compiler takes the expanded source files and converts them into .asm.
* The assembler takes the .asm files and converts them into .doj files. The linker takes the .doj and .dlb files to create an .dxe executable to be loaded into flash memory by the loader.

Here are some of the basic differences between a Microprocessor and a Microcontroller.

### MicroProcessor

A Microprocessor itself is completely useless. It needs external peripherals to interact with the outside world. The issue with adding external devices is that there are:
* Many pins - this increase the time of design, and failure rates increase. The cost also increases with all these pins.
* Another issue is that you don't typically need all this flexibility with pins in real life.
* Probably need to redesign and reassemble the same thing over again

### MicroController

In a Microcontroller, you put a limited amount of most commonly used resources inside the chip. This is typically good enough for most applications.

The advantages of the Microcontroller:
* Pin Count down
* Reliability up
* Design time down
* Cost down
* Common software / hardware design environment available from manufacturer

Problems:
* There are two different types of memory (with different speeds when using) - ON CHIP and OFF CHIP.
* External components are still there - which need the DMA capability.
* It can't wait or poll.

## C++

.extern tells the compiler that the definition is an external file. Name mangling is when the compiler messes up a C++ function name when overloading (multiple overloads have the same name). 

Voltaile registers are registers that change in response to hardware, so the software need to take their erratic changing into account. ssync makes reads and writes happen now.