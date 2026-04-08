---
title: Installation
layout: default
parent: Documentation
nav_order: 0
---

# Installation

---

_dynamarq_ is available as a PyPI package, and can be installed using

```bash
$ pip install dynamarq
```

It is highly recommended to install _dynamarq_ using a python virtual environment manager like
[venv](https://docs.python.org/3/library/venv.html){:target="\_blank"} or
[conda](https://docs.conda.io/projects/conda/en/stable/user-guide/getting-started.html){:target="\_blank"}.

_dynamarq_ requires `qiskit` and `guppylang` for circuit generation, `qiskit-aer` and `qiskit-ibm-runtime` for IBM/Qiskit simulation and testing, and `selene-sim` for Quantinuum/Guppy simulation and testing.
