# VHDL Counter Overflow Bug

This repository demonstrates a common error in VHDL code: an integer counter that can overflow. The `counter_bug.vhdl` file contains the buggy code, which lacks a check to prevent the counter from exceeding its maximum value. The `counter_solution.vhdl` file provides a corrected version.

## Bug Description

The original counter implementation doesn't handle the case where `internal_count` reaches its maximum value (15). When the counter increments beyond 15, it wraps around to 0 due to the modulo arithmetic implied by the `INTEGER range 0 to 15` declaration. This behavior may be unintended, and could lead to logic errors in larger designs that depend on the counter's output.

## Solution

The corrected version in `counter_solution.vhdl` includes an `if` statement to check if `internal_count` is at its maximum value. If it is, the counter is held at 15 instead of incrementing.