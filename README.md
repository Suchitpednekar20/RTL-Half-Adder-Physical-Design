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

## 📁 Repository Structure
* `/Schematic/` : KiCAD 9 `.kicad_sch` source files
* `/Layout/` : Dual-layer routed `.kicad_pcb` layout files
* `/Simulation/` : LTspice `.cir` netlist and testbench simulation files
* `/Outputs/` : High-resolution 3D renders and layout plots
