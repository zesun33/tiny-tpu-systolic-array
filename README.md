# tiny-tpu-systolic-array

> Parametric 2D Systolic Tensor Array Core for Dense Matrix Multiplication (INT8 GEMM).

[![License: Apache-2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](./LICENSE)
[![Architecture: Systolic](https://img.shields.io/badge/architecture-Google%20TPU%20%7C%20Tensor%20Core-blue)](#)
[![Precision: INT8 x INT8 -> INT24](https://img.shields.io/badge/precision-INT8%20%E2%86%92%20INT24-green)](#)

## Overview
`tiny-tpu-systolic-array` is a synthesizable 2D grid processing engine implementing diagonal wavefront systolic dataflows for high-throughput GEMM execution in Transformer and CNN inference.

## Key Features
- **Parametric Array**: Configurable $4 \times 4$ or $8 \times 8$ PE mesh.
- **Wavefront Delay Registers**: Hardware skewing buffers aligning row and column arrival times.
- **Precision**: 8-bit signed inputs $\times$ 8-bit signed weights $\to$ 24-bit accumulation buffers.
- **Double-Buffered Weights**: Seamless weight swapping for continuous compute streaming.
