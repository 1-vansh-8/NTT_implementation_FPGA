# NTT-Based Polynomial Multiplication Architectures

This repository contains multiple hardware implementations of polynomial multiplication using the Number Theoretic Transform (NTT). The designs explore different architectural tradeoffs including combinational, pipelined, and time-multiplexed implementations for varying polynomial sizes (`N`) and integer widths.

The project is motivated by applications in:
- Post-Quantum Cryptography (PQC)
- Lattice-based cryptography
- Hardware accelerators for polynomial arithmetic
- ASIC/FPGA implementation of efficient modular multiplication systems

---

# Repository Contents

## 1. `NTT_combinational.v`

A fully combinational implementation of NTT-based polynomial multiplication.

### Features
- Single-cycle computation structure
- High throughput
- Minimal control overhead
- Suitable for smaller values of `N`

### Tradeoffs
- Large combinational delay
- High area utilization
- Reduced scalability for large polynomial sizes

### Best Use Cases
- Small-size NTTs
- Low-latency experimental designs
- Functional verification/reference architecture

---

## 2. `NTT_SDF_pipelined.txt`

Documentation and architectural notes for a pipelined Single-path Delay Feedback (SDF) NTT architecture.

### Features
- Deep pipelining
- Streaming-compatible architecture
- Improved clock frequency
- Better scalability for larger transforms

### Concepts Used
- Butterfly computation stages
- Delay feedback paths
- Modular arithmetic pipelines
- Twiddle factor scheduling

### Advantages
- High throughput
- Better timing closure
- Efficient hardware reuse

### Applications
- FPGA acceleration
- ASIC-oriented NTT engines
- PQC hardware accelerators

---

## 3. `ntt_time_multiplexed_3_cycle.v`

Time-multiplexed NTT implementation using multi-cycle computation.

### Features
- Hardware resource sharing
- Reduced area
- Multi-cycle execution model
- Optimized for constrained hardware environments

### Tradeoffs
- Lower throughput
- Increased latency
- Additional control complexity

### Best Use Cases
- IoT devices
- Edge accelerators
- Energy-efficient cryptographic hardware

---

## 4. `NTT_explanation.pdf`

Supporting explanation document containing:
- NTT fundamentals
- Polynomial multiplication workflow
- Modular arithmetic concepts
- Hardware design intuition
- Architectural comparisons

---

# Core Concept

Polynomial multiplication is accelerated using the Number Theoretic Transform:

\[
C(x) = A(x) . B(x)
\]

Using NTT:
1. Forward NTT on input polynomials
2. Point-wise multiplication
3. Inverse NTT

This reduces complexity from:

\[
O(N^2) -> O(N log N)
\]

making it highly suitable for cryptographic systems.

---

# Architectural Comparison

| Architecture | Throughput | Area | Latency | Scalability |
|---|---|---|---|---|
| Combinational | High | High | Low | Limited |
| Pipelined SDF | Very High | Medium-High | Medium | Excellent |
| Time-Multiplexed | Medium-Low | Low | High | Good |

---

# Applications

These architectures are relevant for:
- Kyber-like PQC accelerators
- Ring-LWE cryptography
- Secure IoT devices
- FPGA/ASIC cryptographic engines
- High-performance modular arithmetic systems

---

# Future Work

Potential extensions include:
- ASIC synthesis and PPA analysis
- Parameterizable NTT generators
- Support for larger polynomial degrees
- Integration with PQC schemes
- Energy-aware accelerator design
- CUDA/GPU-assisted hybrid implementations

---

# Author

Vansh Goel  
Department of Electrical Engineering  
IIT Gandhinagar

---

# Notes

This repository is intended for educational, research, and hardware accelerator exploration purposes.
