

## Cycle type signals

There are four types of cycles, N, S, I, and C. The CPU specifies what the next cycle type is on the bus (i.e. it is piplined one cycle ahead) using two bits. They are as follows:

Cycle Type | nMREQ | SEQ | 
-----------|-------|-----|-----
N          |   0   |  0  | Nonsequential
S          |   0   |  1  | Sequential 
I          |   1   |  0  | Internal
C          |   1   |  1  | Coprocessor register transfer

* nMREQ = Not memory request
	* When low it indicates a memory access will happen the next cycle
* SEQ = Sequential

Both the above signals become valid during phase 1 and remain valid in phase 2 of the cycle prior to which the cycle it refers to.

## Address bus

A 32 bit bus. The address bus becomes valid during phase 2 of the cycle preceeding the memory access, and remains valid through phase 1 of the actual memory cycle.

## MAS bus

A two bit bus that encodes the size of the memory transfer. It becomes valid during phase 2 of the cycle preceeding the memory access, and remains valid through phase 1 of the actual memory cycle.

## Read/Write signal

One bit signal which indicates whether this is a read or write. It becomes valid during phase 2 of the cycle preceeding the memory access, and remains valid through phase 1 of the actual memory cycle.

## Data bus

A 32 bit bus.

During read: Is an input to the CPU. Data must be valid at the end of phase 2.

During write: Is an output from the CPU. Valid data appears during phase 2 of the cycle preceeding the access and remains valid through phase 1 of the actual memory cycle.

## Lock signal

Indicates that a swap instruction is in progress and the two memory cycles should be regarded as atomic. Becomes valid during phase 2 of the cycle before the first access and remains valid through phase 1 of the second memory access.

## Opcode signal

This signal indicates this is an instruction prefetch. It becomes valid during phase 2 of the cycle preceeding the memory access, and remains valid through phase 1 of the memory cycle.

This signal is utilised by the GBA BIOS ROM for execute permission.

## Translate signal

Signalled during memory accesses in user mode. It becomes valid during phase 2 of the cycle preceeding the memory access, and remains valid through phase 1 of the memory cycle.

## Thumb signal

Indicates if the processor is executing in thumb mode. It becomes valid during phase 2 of the cycle preceeding the memory access, and remains valid through phase 1 of the memory cycle.