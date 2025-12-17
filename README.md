
Canonical Measurement Block Diagram (QMCTB)

┌──────────────────────────┐
│  Field Excitation        │
│                          │
│  • Laser / coherent      │
│    optical source        │
│                          │
│  (No measurement)        │
└─────────────┬────────────┘
              │
              ▼
┌──────────────────────────┐
│  Double-Slit Aperture    │
│                          │
│  • Boundary conditions   │
│  • Path superposition    │
│  • Imprint formation    │
│                          │
│  (No measurement)        │
└─────────────┬────────────┘
              │
              ▼
┌────────────────────────────────────────────────────┐
│  MEASUREMENT LAYER (Detector Plane Imaging)         │
│                                                    │
│  Physical:                                         │
│  • Detector material (CMOS / EMCCD / ICCD / etc.)  │
│  • Screen / phosphor / intensifier (if any)        │
│                                                    │
│  Electronic + Software:                            │
│  • Integration / thresholding                      │
│  • Timing resolution / binning                     │
│  • Firmware & digitization                         │
│  • Image / data formation                          │
│                                                    │
│  → Irreversible information loss occurs here       │
└─────────────┬──────────────────────────────────────┘
              │
              ▼
┌──────────────────────────┐
│  Recorded Output         │                       │
│ • Image / dataset       │
  • Saved frame / file    │                       │
└─────────────┬────────────┘
              │
              ▼
┌──────────────────────────┐
│  Operator / Observer     │
  • Views / analyzes      │
│ • Interprets results    │
│ (No causal influence)   │
└──────────────────────────┘

---

> ⚠️ **Measurement Definition (Non-Negotiable)**
>  
> In this project, “the detector” means the *entire measurement pipeline*:
> detector material, screen or conversion stage, electronics, firmware,
> digitization, software processing, and output display.  
>  
> The observer/operator is *not* part of the measurement layer and has no causal
> influence on the physical outcome.
>  
> This definition is fixed and applies to all benchmarks in this repository.
> See **DEFINITION.md** for the authoritative statement.


# Quantum Measurement Stack

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.17966568.svg)](https://doi.org/10.5281/zenodo.17966568)

The Quantum Measurement Stack is a causally ordered measurement and control
pipeline.


## The Quantum Measurement Stack

The Quantum Measurement Stack is a causally ordered measurement and control
pipeline. Quantum information flows strictly downward through irreversible
layers. Each layer determines what survives to the next.

The stack is defined box-by-box below.


### 1. Imprint Field Dynamics

**Role**  
Physical propagation, interactions, and boundary conditions generate structured
phase, timing, and spatial correlations in fields.

**Key properties**
- Entirely pre-measurement and observer-independent
- Governed by standard physical dynamics
- Defines what correlations physically exist

**Output**  
Coherent imprint field


### 2. Detector Plane Imaging

**Role**  
Detector architecture couples to the imprint field and determines whether
correlations are preserved or destroyed during measurement.

**Key properties**
- Measurement causality is localized here
- Detector architecture is not neutral
- Correlation loss here is irreversible

**Output**  
Analog detector signals


### 3. DAQ Integrity

**Role**  
Digitization, sampling, timing, thresholding, and binning determine which
accessible correlations survive into permanent digital records.

**Key properties**
- Data acquisition is an active causal layer
- Undersampling and over-binning destroy information
- No post-processing can recover lost correlations

**Output**  
Discrete digital datasets


### 4. Quantum Diagnostics

**Role**  
Statistical analysis and validation quantify what survived the measurement
pipeline and with what confidence.

**Key properties**
- Computes visibility, fidelity, correlations, and error rates
- Decoherence can be injected deliberately for stress testing
- Inference only — no control actions

**Output**  
Validated diagnostic metrics


### 5. QCS — Quantum Control System

**Role**  
System-level control layer that uses validated diagnostics to manage quantum
resources and orchestrate future experimental cycles.

**Key properties**
- Manages coherence budgets and entanglement lifecycles
- Enforces measurement policy and scheduling
- Handles retry, reset, and recovery from entanglement failure
- Acts only forward in time

**Output**  
Control actions for next experimental run


### Core Rules of the Stack

- Causality flows strictly downward.
- Each layer introduces irreversible information loss.
- Higher layers cannot repair or reinterpret lower-layer loss.
- Control exists only at the top and only forward in time.


## Formal Definition

The formal definition, governing rules, and causal constraints of the Quantum
Measurement Stack are specified in **DEFINITION.md**.

That document is authoritative with respect to stack ordering,
irreversibility, and the separation of inference and control.

