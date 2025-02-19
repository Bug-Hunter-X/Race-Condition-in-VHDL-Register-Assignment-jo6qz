# VHDL Race Condition Example

This repository demonstrates a potential race condition in a simple VHDL register assignment. The code implements a basic register that copies input data to an output port. However, the output might not be updated immediately due to timing issues, resulting in incorrect behavior.

## Bug Description

The primary issue lies in the `process` statement. While the `internal_reg` updates correctly on the rising edge of the clock, there's no guarantee of immediate propagation to `data_out`.  In high-frequency designs, this slight delay could lead to missed data or glitches.

## Solution

The solution involves using a separate process or ensuring the data path has proper timing constraints to eliminate the race condition. The updated code provides improved synchronization.