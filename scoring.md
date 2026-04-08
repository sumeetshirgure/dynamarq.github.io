---
title: Fidelity scores
layout: default
parent: Documentation
nav_order: 2
---

# Fidelity scores

---

The generated circuits can be dispatched to a hardware/simulators.

```python
    ...
>>> from qiskit_aer import AerSimulator
>>> # Get circuits without MidCircuitMeasure for AerSimulator
>>> sim_circuits = benchmark.qiskit_circuits(mcm=False)
>>> jobs = [AerSimulator().run(circuit, shots=4096) for circuit in sim_circuits]
```

Each benchmark object implements a `qiskit_score()` and a `guppy_score()` function that calculates
the hardware fidelity score given a list of hardware/simulation results.
These functions are also scalable in the benchmark parameters.

```python
>>> counts = [job.result().get_counts() for job in jobs]
>>> print( benchmark.qiskit_score(counts) )
    ...
```
