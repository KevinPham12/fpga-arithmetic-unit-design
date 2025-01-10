# FPGA Fixed-Point vs Floating-Point Arithmetic Comparison

This project compares fixed-point and floating-point arithmetic implementations on an FPGA, specifically using the Artix-7 Xilinx FPGA. The project focuses on the design and performance of addition and multiplication units for both fixed-point and floating-point arithmetic. The goal is to evaluate the efficiency, resource usage, and accuracy of these two formats in the context of FPGA-based designs.

## Project Overview

Reconfigurable Computing Systems (RCS), such as FPGAs, provide high flexibility and performance for custom arithmetic units. Fixed-point and floating-point arithmetic have different strengths and trade-offs in terms of resource usage and computational complexity. This project aims to compare these two formats by implementing basic arithmetic units (addition and multiplication) in VHDL and C++ using Vivado HLS, and then validating their performance and resource usage on the Artix-7 FPGA.

## Key Features

- **VHDL Design**: Implemented 8-bit, 16-bit, and 32-bit fixed-point and floating-point addition and multiplication units.
- **C++ Design**: Implemented the same arithmetic units using Vivado HLS to compare performance and resource usage in a high-level synthesis environment.
- **FPGA Validation**: Tested both designs on the Artix-7 Xilinx FPGA.
- **Performance Metrics**: Analyzed execution time, resource utilization, and power consumption.
- **Scalability**: Assessed the scalability of both designs with different bit widths (8-bit, 16-bit, and 32-bit).

## Background

- **Fixed-Point Arithmetic**: Simple and resource-efficient, typically used in embedded systems and digital signal processing (DSP). Ideal for real-time applications requiring fast, predictable calculations.
- **Floating-Point Arithmetic**: Offers higher precision and a larger dynamic range, suitable for tasks like scientific computing and machine learning. However, floating-point units require more resources and computational complexity.

## Methodology

1. **VHDL Design Process**: Developed fixed-point and floating-point units for 8-bit, 16-bit, and 32-bit inputs, ensuring scalability without sacrificing accuracy. Functionality was verified using custom testbenches in Vivado.
2. **C++ Design Process**: Implemented fixed-point and floating-point units in C++ and used Vivado HLS for synthesis and simulation to evaluate performance and resource utilization.
3. **Simulation and Validation**: Performed simulations using Vivado and Vivado HLS to evaluate timing, resource usage, and power consumption.

## Results

### Fixed-Point Results

- **Efficiency**: Fixed-point units demonstrated lower resource usage and faster computation times compared to floating-point units, making them suitable for real-time applications.
- **Scalability**: The designs scaled well from 8-bit to 32-bit, with a linear increase in resource usage and timing.

### Floating-Point Results

- **Accuracy Issues**: Floating-point units experienced some accuracy inconsistencies due to normalization issues during simulation.
- **Resource and Timing Trade-Offs**: Floating-point units consumed more resources and had higher timing delays compared to fixed-point units due to the complexity of handling normalization, exponent, and mantissa calculations.

### Vivado and Vivado HLS Simulations

- **Vivado Simulations**: Provided reliable timing and resource usage data, confirming the efficiency of fixed-point implementations and the inconsistencies in floating-point results.
- **Vivado HLS Simulations**: Validated the functionality of both designs and quantified resource utilization.

## Results Summary

### Timing Results (Vivado)
| Adder & Multiplier Type | WNS (ns) | TNS (ns) |
| ----------------------- | -------- | -------- |
| 8-bit Fixed             | 6.783    | 0        |
| 16-bit Fixed            | 7.092    | 0        |
| 32-bit Fixed            | 7.508    | 0        |
| 8-bit Floating          | 9.124    | 0        |
| 16-bit Floating         | 13.472   | 0        |
| 32-bit Floating         | 15.643   | 0        |

### Timing Results (Vivado HLS)
| Adder & Multiplier Type | Estimated Clock Period (ns) | Worst Case Latency (clock cycles) |
| ----------------------- | --------------------------- | --------------------------------- |
| 8-bit Fixed             | 8.85                        | 0                                 |
| 16-bit Fixed            | 9.09                        | 0                                 |
| 32-bit Fixed            | 9.07                        | 0                                 |
| 8-bit Floating          | 11.89                       | 0                                 |
| 16-bit Floating         | 16.48                       | 2                                 |
| 32-bit Floating         | 16.14                       | 5                                 |

## Conclusion

- **Fixed-Point Strengths**: Fixed-point arithmetic units performed better in terms of efficiency and simplicity. These designs are well-suited for applications requiring high-speed, resource-efficient processing.
- **Floating-Point Challenges**: Floating-point units faced accuracy issues and higher resource usage. Their implementation requires refinement to address normalization issues, but they offer higher precision when correctly implemented.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
