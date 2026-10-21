# Chipguard-assignment
Verilog HDL assignment containing RTL designs, testbenches, and simulation results.
# ChipGuard: Instruction Encoding and Handshake FSM Design

Coursework for the ChipGuard assignment, covering two digital design problems:

1. **Problem 1: X-16 instruction set encoding.** Design a fixed-length binary instruction format for a simple 16-bit processor.
2. **Problem 2: Valid/ready handshake transmitter.** Design a finite state machine that sends three 8-bit readings (A, B, C) to a receiver that may be busy.



---

## Problem 1: X-16 Instruction Encoding

**Goal:** Choose an instruction length, split the bits into fields, and assign a unique binary code to each of the 16 operations (ADD, SUB, AND, OR, XOR, INC, DEC, MOV, LDI, LD, ST, BEQ, BNE, JMP, RET, NOP).

**Covered in this work:**
- Minimum field widths for registers, opcode, immediates, offsets, branch displacement and jump target
- Choice of instruction length, with justification
- Format diagrams showing the position and meaning of every field
- Encoding table for all 16 operations
- Verification: ranges fit, no duplicate codes, unambiguous decoding
- Worked binary examples (three-register, immediate, memory, branch/jump)
- Comparison with an alternative design

**Key design decisions:** We have used here the instruction length as 24bits because if we take 16 bits then we cannot encode conditional operations because it will require 17 bits for its representation therefore we will use 24 bit instruction length  

---

## Problem 2: Handshake FSM

**Goal:** Design a controller that sends A, B, C in order using a valid/ready handshake, never skipping, repeating or changing a reading before it has been accepted.

**Covered in this work:**
- State diagram and state-transition table
- Output definitions (VALID, DATA_OUT, DONE), including the idle state
- Behaviour while the receiver is busy (holding the current reading)
- Completion (DONE for one cycle) and synchronous reset
- Cycle-by-cycle timing exercise
- Analysis of the "VALID depends on READY" bug (deadlock and data loss)

**Design style:** It is a moore state machine design

---


## Tools Used

Quartus prime 
Qestasim

---
