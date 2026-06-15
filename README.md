# Transistor-Level RTL Half Adder: From Schematic to Dual-Layer PCB Layout

A comprehensive, production-ready discrete hardware implementation of a 2-bit binary Half Adder cell designed from scratch using Resistor-Transistor Logic (RTL) topology. This project covers the complete silicon-to-board workflow, including SPICE netlist simulation validation (LTspice) and industrial physical layout design (KiCAD 9) with 100% DRC clearance.

## 🚀 Technical Features & Specifications
* **Logic Family:** Discrete Resistor-Transistor Logic (RTL)
* **Active Components:** 6x BC547 NPN Bipolar Junction Transistors (BJTs), 2x 1N4148 Fast-Switching Diodes
* **Architecture Blocks:** * **CARRY (AND Gate):** Series-stacked NPN transistor cascade with 330Ω pull-down loading.
* **SUM (XOR Gate):** Cross-coupled parallel NPN branch network paired with a Wired-OR diode mixing node to eliminate signal feedback degradation.
* **PCB Architecture:** Dual-Layer High-Density Placement Routing (`F.Cu` and `B.Cu` layers)
* **Form Factor & Design Parameters:** Optimized single-board design with strict orthogonal routing to prevent capacitive cross-talk.

## 📊 Verification & Simulation Analysis
The circuit logic was extensively stress-tested in LTspice using sharp transient pulse streams ($10\text{ns}$ rise/fall transitions) to replicate true high-frequency binary operations:
* **Inputs Pattern:** Dynamic binary cycles ($00 \rightarrow 01 \rightarrow 10 \rightarrow 11$).
* **Voltage Levels:** Controlled forward voltage drop mitigation ($\approx 3.6\text{V}$ on SUM due to diode barrier attenuation, and $\approx 4.4\text{V}$ on CARRY).
* **DRC Report:** 0 Errors, 0 Warnings.

## 📸 Project Gallery

### 1. Schematic Design
<img width="1092" height="755" alt="Schematic" src="https://github.com/user-attachments/assets/0d83bebb-ba59-4811-8f49-b25a02f4b488" />

### 2. PCB 3D Hardware Render
<img width="1918" height="1018" alt="3D view back side" src="https://github.com/user-attachments/assets/c6a0ceb0-993f-47dc-b26b-d5122dd2c04e" />
<img width="1092" height="755" alt="Schematic" src="https://github.com/user-attachments/assets/8be41ac7-da4e-486e-89c3-da6ca9fef03c" />
<img width="1916" height="1017" alt="3D view front side" src="https://github.com/user-attachments/assets/973423d6-5866-47f9-ba8d-be920cb79d5d" />

### 3. PCB Routing
<img width="805" height="787" alt="PCB Editor 2" src="https://github.com/user-attachments/assets/3e335f79-3e9b-44b8-bac1-7855b0133653" />

### 3. LTspice Transient Waveform Graph
<img width="1916" height="1022" alt="Waveforms" src="https://github.com/user-attachments/assets/9b9d18bf-987b-4ba7-ae23-ed2d2911d27a" />

## 📁 Repository Structure
* `/Schematic/` : KiCAD 9 `.kicad_sch` source files
* `/Layout/` : Dual-layer routed `.kicad_pcb` layout files
* `/Simulation/` : LTspice `.cir` netlist and testbench simulation files
* `/Outputs/` : High-resolution 3D renders and layout plots
