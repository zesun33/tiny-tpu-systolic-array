# tiny-tpu-systolic-array: Architectural Specification

## 1. Systolic Dataflow
- Data inputs ($A_{i,k}$) flow horizontally from West to East across rows.
- Data weights ($B_{k,j}$) are either weight-stationary inside PEs or stream vertically from North to South.
- Partial sums accumulate either locally (output-stationary) or stream South.
- Input deskew buffers stagger input timing: Row $i$ is delayed by $i$ clock cycles.

## 2. Pinout & Interface
| Signal | Direction | Width | Description |
| :--- | :---: | :---: | :--- |
| `clk` | In | 1 | Clock |
| `rst_n` | In | 1 | Active-low reset |
| `start` | In | 1 | Start matrix multiplication execution |
| `matrix_a_vec` | In | ROWS*8 | Packed input vector (e.g. 4x INT8 for 4x4) |
| `matrix_b_vec` | In | COLS*8 | Packed weight vector (e.g. 4x INT8 for 4x4) |
| `matrix_c_out` | Out | ROWS*COLS*24 | Complete resulting output matrix |
| `done` | Out | 1 | Computation complete strobe |
