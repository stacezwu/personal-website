+++
title = "Design a custom FPGA Circuit"
date = "2021-04-15"

[extra]
subtitle = "I designed a logical circuit to perform a given computation using Verilog"
date = "April 2021"
abstract = "The goal of the project was to compute a given expression as efficiently as possible. Starting with a CORDIC algorithm implemented in C and building up to a pipe-lined custom circuit."
+++

# The Project

The goal of the project was to compute the expression:

<center>
0.5x + x^2 * cos((x - 128) / 128)
</center>

The initial task was to implement this function in C and use it to compute this formula over a large range of inputs `x`, and then compute the sum of all the intermediate results.

For the second task, I designed a custom instruction for `0.5 * a + b`, with floating point inputs
`a` and `b`, which can be used for part of the above formula.

The key step to computing the above formula efficiently is to compute the cosine of some value. To do so efficiently, I implemented the [CORDIC](https://en.wikipedia.org/wiki/CORDIC) algorithm as a custom instruction, operating on fixed point binary inputs.

CORDIC will compute the sin and cosine simultaneously, but for the above formula only the cosine was required and used.

In the final part of the project, these parts where combined into a single instruction. Once this was accomplished, I further improved upon the resource and memory utilization by implementing unrolled and partially-unrolled pipe-lined designs.

All these circuits where designed using the Verilog HDL, and tested using simulations, as well as by running on actual FPGA hardware.
