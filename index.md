---
title: Home
layout: home
nav_order: 1
---

# Welcome to the dynamarq docs!

---

_dynamarq_ is a scalable benchmarking framework specially designed for dynamic quantum circuits.

Dynamic quantum circuits consist of mid-circuit measurements (MCMs) and feed-forward operations
that depend on the outcome of those measurements.
They are an important component of many useful quantum primitives 
like [error correction](https://en.wikipedia.org/wiki/Quantum_error_correction){:target="\_blank"}
and [teleportation](https://en.wikipedia.org/wiki/Quantum_gate_teleportation){:target="\_blank"}.
They have also been useful in bringing down the depth of quantum state preparation circuits and quantum algorithms.

_dynamarq_ collects a suite of application level dynamic circuits to act as benchmarks and provides circuit generators
in [Qiskit](https://www.ibm.com/quantum/qiskit){:target="\_blank"} and [Guppy](https://docs.quantinuum.com/guppy/){:target="\_blank"}.
Every benchmark has an associated fidelity score that can be computed efficiently from the simulation or hardware execution results.

_dynamarq_ also provides a broad set of circuit features tailored to dynamic circuits.
These features are inspired by [SupermarQ](https://superstaq.readthedocs.io/en/latest/apps/supermarq/supermarq.html){:target="\_blank"}
and are detailed in our [arxiv paper](https://arxiv.org/pdf/2604.03360){:target="\_blank"}.

The set of circuit features and hardware fidelity scores can be used for fitting a statistical model on a collection of benchmarks
to evaluate the features that have the greatest impact on the fidelity, and also for predicting the fidelity of new circuits
without running them on hardware.
