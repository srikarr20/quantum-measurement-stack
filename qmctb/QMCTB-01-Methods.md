Methods: QMCTB-01 — Detector Plane Causality Benchmark


Overview and Scope

QMCTB-01 is a measurement benchmark, not a new physical experiment.
It uses a conventional double-slit optical geometry but applies a non-standard causal decomposition of the measurement process.

The goal of the benchmark is to isolate and test detector-plane causality:
whether interference visibility is determined upstream by field propagation, or locally by detector-plane coupling that preserves or destroys correlations.

No modifications are made to the underlying physical laws, source properties, or propagation dynamics. All deviations from textbook presentations arise solely from explicitly separating measurement into causally ordered layers.

Physical Geometry (Unmodified)

The physical layout corresponds to a standard double-slit experiment:

Coherent field excitation
A spatially coherent optical field is assumed (e.g., laser illumination).
In the simulation, this is modeled as a monochromatic scalar field.

Aperture plane (double slit)
Two narrow slits separated by a fixed distance define two spatially separated propagation paths.

Free-space propagation
The field propagates from the aperture plane to the detection plane over distance 
𝑧
z.
Paraxial Fresnel propagation is used, including quadratic phase factors.

Detection plane
A spatially resolved detection plane records the field-dependent response.

This geometry is intentionally conventional to avoid confounding apparatus novelty with measurement causality.

Causal Decomposition of the Measurement Process

The key methodological contribution of QMCTB-01 is the explicit separation of the experiment into five irreversible layers, each with a defined input and output.

Stage 1: Imprint Field Dynamics (Pre-measurement)

Input: Coherent excitation and aperture geometry

Process: Field propagation, interference, and phase accumulation

Model: Paraxial Fresnel propagation from each slit

Output: A coherent imprint field at the detector plane

At this stage, interference exists as a physical field structure, independent of detection or statistics.

No observers, detectors, or digitization are involved.

Stage 2: Detector Plane Imaging (Measurement Coupling)

This stage defines how the detector couples to the incoming field.

Two detector models are evaluated against the same imprint field:

Correlation-preserving detector (PRESERVE)

Detector response is proportional to

∣
𝜓
1
+
𝜓
2
∣
2
∣ψ
1
	​

+ψ
2
	​

∣
2

Phase correlations between paths are retained

Interference fringes are physically expressed in the detector signal

Correlation-destroying detector (DESTROY)

Detector response is proportional to

∣
𝜓
1
∣
2
+
∣
𝜓
2
∣
2
∣ψ
1
	​

∣
2
+∣ψ
2
	​

∣
2

Phase correlations are lost locally at detection

No interference structure is present in the signal

This distinction models real differences between detector architectures, not interpretive choices.

Once correlations are destroyed at this stage, they cannot be recovered downstream.

Stage 3: DAQ Integrity (Digitization and Noise)

Input: Analog detector signals

Process:

Poisson shot noise (photon counting statistics)

Frame-based accumulation

Output: Discrete digital datasets

Multiple frames are accumulated to simulate realistic data acquisition.

Importantly:

Increasing frame count averages noise

It does not create interference if it was destroyed earlier

Stage 4: Quantum Diagnostics (Inference Only)

Input: Digitized datasets

Metrics computed:

Visibility (contrast)

Statistical uncertainty

Output: Validated diagnostic metrics

No control actions occur here.
This stage performs inference only, making no assumptions about underlying ontology.

Stage 5: Quantum Control System (QCS)

Input: Diagnostic metrics and thresholds

Function:

Accept, reject, or continue benchmark runs

Adjust frame budget or detector mode for future runs

Constraint:

Acts only forward in time

Does not reinterpret prior data

In QMCTB-01 v1.0, parameters are locked and the benchmark is frozen after acceptance.

Benchmark Criterion

The benchmark is considered PASSED if:

Visibility in the PRESERVE path exceeds a predefined threshold

Visibility in the DESTROY path remains low after sufficient averaging

Results are stable across increasing frame counts

This demonstrates that detector-plane coupling alone determines interference visibility for a fixed upstream field.

What This Benchmark Does Not Claim

No new quantum mechanics

No modification of wave-particle duality

No claim about single-photon ontology

No reinterpretation of collapse

QMCTB-01 is strictly a causal, operational benchmark.

Summary Statement

QMCTB-01 shows that, within a conventional double-slit geometry, the presence or absence of interference fringes is fully accounted for by local detector-plane correlation handling, without invoking observer-dependent explanations or nonlocal mechanisms.

The benchmark formalizes this insight into a reproducible, diagnosable, and controllable test suitable for integration into a Quantum Measurement & Control Test Bench.
