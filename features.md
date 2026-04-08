---
title: Circuit features
layout: default
parent: Documentation
nav_order: 3
---

# Circuit features

---

_dynamarq_ provides an API to efficiently compute a set of circuit features tailored to dynamic circuits.
These features are detailed in our [arxiv paper](https://arxiv.org/pdf/2604.03360){:target="\_blank"}.

Note that the values of the features may depend on the gate error rates which must be retrieved from hardware provider.
Here is an example calculating circuit feature values from IBM Quantum platform.

```python
>>> import dynamarq
>>> print(dynamarq.QiskitMetrics.get_metric_names(None))
    ...
>>> from qiskit_ibm_runtime import QiskitRuntimeService
>>> service = QiskitRuntimeService() # Make sure you have your IBM Quantum token
>>> backend = service.backend('ibm_pittsburgh')
>>> testbench = dynamarq.get_testbench()
>>> for benchmark in testbench :
        qiskit_metrics = dynamarq.QiskitMetrics(benchmark, backend, stretch_dd=False)
        metric_values = qiskit_metrics.get_metrics()
        print(benchmark.name(), metric_values)
```

We can compute features for Quantinuum's Helios hardware/emulator using `dynamarq.QuantinuumMetrics(benchmark)` method.

The set of circuit features and hardware fidelity scores can be used for fitting a statistical model on a collection of benchmarks
to evaluate the features that have the greatest impact on the fidelity, and also for predicting the fidelity of new circuits
without running them on hardware.
