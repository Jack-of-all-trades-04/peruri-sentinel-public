# PERURI-SENTINEL

All-digital fault-attack sensor and key-protection IP for sovereign secure elements (e-Paspor). Design for the PERURI Chip Hackathon 2026, Topik 01 (Secure Identity & Security Element Chip).

The design combines a Tapped Delay Line glitch canary and a Ring Oscillator mesh with a multiplier-free LIF filter, an output release gate that holds ciphertext until the sensors report clean, graduated tamper response with asynchronous key zeroization, and always-on DPA hiding. Target platforms: Terasic DE10-Nano (Cyclone V SoC) and SkyWater sky130A via LibreLane.

## Contents

- `docs/peruri_sentinel_technical_specification.md`: technical specification (threat model, sensor fabric, FSM, resource estimates, test plan).
- `diagrams/`: architecture figures. Each figure has an editable source (`.drawio` or `.json5`) and PDF, PNG and SVG exports. See [diagrams/DIAGRAMS.md](diagrams/DIAGRAMS.md).

## Planned layout

- `rtl/`: Verilog sources (not yet added).
- `verify/`: testbenches for Icarus Verilog and cocotb (not yet added).
- `librelane/`: ASIC flow configuration for sky130A (not yet added).

Figures and the specification are reviewed as the RTL is implemented. Parameter values marked "(target)" or "(estimasi)" are not yet measured.
