# VHDL Process without Wait Statement

This repository demonstrates a common error in VHDL: a process without a wait statement.  This can lead to unintended infinite loops and simulation issues.

## The Bug

The `bad_process.vhdl` file contains a process that responds to a rising clock edge.  However, it lacks a `wait` statement.  This means that the process will execute continuously, consuming significant simulation resources and potentially causing unexpected behavior in hardware.

## The Solution

The `good_process.vhdl` file provides a corrected version.  The addition of a `wait until` statement ensures that the process suspends execution until the next rising edge of the clock, resolving the infinite loop problem.

## How to Reproduce

1.  Compile `bad_process.vhdl` using your VHDL simulator (e.g., ModelSim, GHDL).
2.  Simulate the design. Observe the extremely high CPU usage and potentially a simulation crash.
3.  Compile and simulate `good_process.vhdl`. Observe the corrected behavior with normal resource consumption.
