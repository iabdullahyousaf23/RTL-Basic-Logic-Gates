# RTL-Basic-Logic-Gates

# Basic Logic Gates RTL Implementation & FPGA Synthesis

## 📌 Project Overview
This repository contains the Register-Transfer Level (RTL) design, behavioral simulation, and FPGA logic synthesis for fundamental combinational logic gates: **NOT, NAND, and NOR**. 

This project bridges theoretical digital IC design with practical hardware implementation, demonstrating a complete hardware compiler workflow using **Xilinx Vivado**. It serves as a foundational step toward more complex physical designs and custom architectures.

## Theoretical Background
Combinational logic circuits are the building blocks of all digital systems, where the output is a pure function of the present inputs. 

* **NOT Gate (Inverter):** Outputs the opposite logic level of the input. 
    * Boolean Expression: $Y = \overline{A}$
* **NAND Gate:** A universal gate that produces a `0` output only if all inputs are `1`. 
    * Boolean Expression: $Y = \overline{A \cdot B}$
* **NOR Gate:** A universal gate that produces a `1` output only if all inputs are `0`. 
    * Boolean Expression: $Y = \overline{A + B}$

*Note: NAND and NOR are "universal gates," meaning any complex boolean function can be implemented using only these gates, making them critical for transistor-level IC design.*

## Tools & Technologies
* **Hardware Description Language:** Verilog / SystemVerilog
* **EDA Tool:** Xilinx Vivado
* **Target Hardware:** 7-Series FPGA architecture (e.g., Kintex-7)

## Implementation & Synthesis Details

### 1. RTL Schematic & Elaboration
The high-level HDL was elaborated into discrete hardware primitives. The technology schematic demonstrates the mapping of the physical inputs (`a`, `b`) through Input Buffers (**IBUF**), computation via 6-input Look-Up Tables (**LUT1**, **LUT2**), and routing to Output Buffers (**OBUF**).
*(Note: Upload your Schematic Image here)*

### 2. Behavioral Simulation
Before synthesis, the design was validated using a testbench. The simulated waveform confirms deterministic timing and strictly accurate logic transitions across all possible input states (00, 01, 10, 11).
*(Note: Upload your Waveform Image here)*

### 3. FPGA Logic Synthesis & Resource Utilization
The RTL was successfully synthesized into a physical netlist mapped to the FPGA fabric. The logic optimization was highly efficient, with the following utilization metrics on a 41,000-LUT device:
* **Slice LUTs:** 2 / 41,000 (< 1%)
* **Bonded IOBs (Input/Output Blocks):** 5 / 300 (1.67%)
*(Note: Upload your Utilization Report Image here)*

### 4. Device Floorplanning
Physical placement constraints and routing were explored via Vivado's Device view, highlighting how standard combinational gates map physically into the logic slices on the silicon die.
*(Note: Upload your Device Layout Image here)*

## Future Scope
* Implement parameterized N-bit variations of these gates.
* Design custom Arithmetic Logic Units (ALUs) utilizing these base modules.
* Integrate synthesized modules into a larger open-source CPU architecture path, such as a basic RISC-V core.
