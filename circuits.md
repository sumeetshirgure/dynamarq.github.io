---
title: Circuit generators
layout: default
parent: Documentation
nav_order: 1
---

# Circuit generators

---

_dynamarq_ can be used to generate benchmark dynamic circuits.
All benchmarks are encapsulated in a `benchmark` class, available after importing _dynamarq_.

```python
>>> import dynamarq
>>> ghz_benchmark = dynamarq.GHZ.GHZ(3) # Create a 3 qubit GHZ benchmark
```

Each benchmark object implements a `qiskit_circuits()` and a `guppy_circuits()` function
that can be used to get a list of circuits.
We run multiple circuits to evaluate the machine/simulator on the given benchmark.
Each benchmark object is parameterized by a number `n` that is related to the number of qubits,
and other parameters relevant to the circuit like the number of Trotter steps.
These functions are scalable in the parameters provided.

Qiskit circuits can be constructed with or without insertion of
[dynamical decoupling](https://en.wikipedia.org/wiki/Dynamical_decoupling){:target="\_blank"}
sequences using IBM's new
[stretch](https://quantum.cloud.ibm.com/docs/en/guides/stretch){:target="\_blank"}
operations. This can be enabled using the `stretch_dd=True` flag.

By default IBM's new [MidCircuitMeasure](https://www.ibm.com/quantum/blog/utility-scale-dynamic-circuits){:target="\_blank"}
instruction is used for mid-circuit measurements. This can be disabled using the `mcm=False` flag.

```python
>>> qiskit_circuits = ghz_benchmark.qiskit_circuits(stretch_dd=True)
>>> print(qiskit_circuits[0])
    ...
```

You can read more about individual benchmarks using `help(dynamarq.<benchmark>.<benchmark>)` doc.

_dynamarq_ also provides a `get_testbench()` function to create a list of benchmarks in our suite.

```python
>>> testbench = dynamarq.get_testbench()
>>> print(list(benchmark.name() for benchmark in testbench))
    ...
```
