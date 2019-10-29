# ENCM 511
## Acronyms
* CPU - Central Processing Unit
* CCU - Computer Control Unit
* DMA - DIrect Memory Access
* CLLR - Compile, Link, Load and Run
* PSP - Personal Software Process
* PIP - Personal Improvement Plan
* LSD - Little Stupid Details
* WIDFI - When in doubt, fake it
* WAIL - Worry about it later
* WAIN - Worry about it now
* PEP - Personal Exam Process
* CC - Condition IF coe
* PF - Programm Flag (on BF533)
* PF - Port F (on the 609)
* GPIO - General Purpose Input Output
* JSR - Jump to subroutine
* RTS - Return to subroutine
* REB - Remote Extender Board
* PSPP -Practice Safe Programming Process
* JEADI - Just enough additional development interfaces
* MVP - Minimal viable product
* ICE - In circuit emulator
* IRQ - Interrupt Request Line - Hardware line that devices can send interrupts
* MOSI - Master Out, Slave In
* KIS - Keep it simple
* TTCOS - TIme triggered cooperative operating system
* TDD - Test Driven Development
* GQM - Goal Question Metric
* SWI - Software Interrupt

### Differences between Harvard and von Neumann architecture

* Von Neumann architecture has only ONE address bus, ONE control bus, and ONE data bus. The address bus sends commands to memory and gets acknowledgements back.
* Harvard architecture has TWO address, control and data bus. There is separate memory for instructions and registers (ROM and RAM).

### Steps involved in a "Standard" instruction cycle of a microprocessor

1. Reset the processor, which causes the reset interrupt
2. Fetches an instruction from the program memory
3. Decodes the instruction and fetches any needed values from memory
4. Executes instruction
5. Write back the result
6. Go back to step 2

##### Von Neumann Operation
* The control bus sends timing commands to to memory and peripherals and gets acknowledgement signals back
* Von Neumann architecture has one address bus, one data and one control bus
* It goes through FETCH, DECODE, EXECUTE and WRITEBACK

In fetch, the program counter (PC) placed on Address BUS. It reads the control signal sent by the control bus. The program RAM places instruction on the instruction register. The data address generator (DAG) performs PC + 2 to point to next instruction.

In decode, the values needed to perform operation are fetched. The CCU (Computer control unit) looks at the OPCODE and recognizes the operation at needs to be done. It reads the source registers needed.

In the execute, the CCU looks at the Opcode and recognizes the operation that needs to be done. It performs the operation and stores the value in the output in the ALU.

In the writeback stage, the CCU looks at the destination register part of the IR, stores the ALU in R1. Moves back to the Fetch stage.

Basically, in a 16 bit number, Bits 15-11 is the OPCODE, bits 10-8 is the destination register, bits 7-4 is the source register 1 and bits 3-0 is source register 2. 

In a pipeline, the Von Neumann will often Stall as it cannot fetch data and instructions at the same time since there is only one data and address bus.

The harvard processor doesn't stall as it can fetch data and instructions at the same time with two data busses and two address buses.

## Interrupts

In digital computers, an interrupt is an input signal to the processor indicating an event needs immediate attention. An interrupt signal alerts the processor and serves as a request for the processor to interrupt the currently executing code so that the event can be processed in a timely manner. If the request is accepted, the processor responds by suspending its current activities, saving its state, and executing a function called an interrupt handler to deal with the event. This interruption is temporary, and unless the interrupt a fatal error, the processor resumes normal activities after the interrupt handler finishes.

Interrupts introduce a extra "phase" in the instruction cycle. Basically, after the writeback stage, the program will check if a interrupt request has occurred. If so, it will deal with the interrupt before returning to the fetch stage.

A hardware interrupt can happen any time it wants.
1. It is not under your control - therefore a ASYNCHRONOUS event
2. How does your interrupt know what to do?
3. How do you get back to your instruction that got interrupted?
4. How does the processor recover after an interrupt.
5. Inside a C++ or ASM ISR, how can you use registers when all registers are used by the code?
6. How can you test a ISR?

ISR - Interrupt Service Routine
IRQ - INterrupt ReQuest signal
NMI - Non-maskable Interrupt
Ready signal or Done signal - an IRQ signal that has not been programmed
#pragma interrupt - a command that adds features to a subroutine that turn sit into a ISR. 
VBT - vector branch table - special hardware array that lists the start of every ISR programmed.