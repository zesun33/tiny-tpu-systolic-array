# tiny-tpu-systolic-array

<!-- BEGIN GENERATED PROJECT GUIDE -->

## Purpose and first steps

Specify a proposed INT8 systolic-array dataflow and interface.

**Who it is for:** Hardware learners studying matrix-multiplication dataflow and PE timing.

**First task:** Trace one small matrix product through the proposed skewed input schedule.

**What to expect:** A systolic-array dataflow and interface proposal to implement and compare with a software GEMM reference.

**Current scope:** Architecture draft only: no synthesizable array, executable regression, or measured implementation is present.

**Start here:** [Systolic dataflow proposal](ARCHITECTURE.md).

**Related projects:** [cim-bit-serial-pe](https://github.com/zesun33/cim-bit-serial-pe), [cuda-gemm-optimization](https://github.com/zesun33/cuda-gemm-optimization).

[Choose another project](https://github.com/zesun33/personal-projects/blob/main/GETTING_STARTED.md).
<!-- END GENERATED PROJECT GUIDE -->

Architecture proposal for a small INT8 matrix-multiplication engine built from a systolic processing-element array.

## Current implementation

This repository currently contains this README and [ARCHITECTURE.md](ARCHITECTURE.md). No RTL array, runnable GEMM regression, or implementation measurements are present yet.

## Why study this design?

A systolic array reuses operands as they move between neighboring processing elements. The key design question is how the input schedule, weight placement, and accumulation timing produce the correct matrix result.

## Proposed features

- A small parameterized array, starting with a manageable size such as 4 × 4.
- Skewed input arrival times for a diagonal wavefront.
- Signed INT8 operands and a proposed 24-bit accumulation result.
- A dataflow choice and buffering scheme to finalize before implementation.

## Next concrete milestone

Choose one stationary dataflow, write its cycle schedule, implement the first array, and compare complete results with a software GEMM reference. Quantify throughput and area only after the implementation and checks exist.
