---
title: Installation
layout: default
parent: Documentation
---

# Installation

dynamarq is available as a PyPI package, and can be installed using

```bash
$ pip install dynamarq
```

It is highly recommended to install dynamarq via a python virtual environment manager like venv or conda.

dynamarq requires `qiskit` and `guppylang` for circuit generation, `qiskit-aer` and `qiskit-ibm-runtime` for IBM/Qiskit simulation and testing, and `selene-sim` for Quantinuum/Guppy simulation and testing.
