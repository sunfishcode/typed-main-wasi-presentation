# Is WebAssembly Assembly?

Wasm is like an ISA, but different.

General-purpose CPUs have converged in many areas:
 - 8-bit bytes
 - Two's complement
 - IEEE 754 floating-point

But also:
 - Memory is a big virtual address space of bytes
 - Calls are just jumps (-and-link) with register and memory conventions
 - Syscalls are mode switches and jumps

In WebAssembly, the address space isn't everything.

Calls arguments are part of the call instruction.
