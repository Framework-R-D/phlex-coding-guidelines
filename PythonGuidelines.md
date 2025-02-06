# Python Guidelines

Basis: [PEP-8](https://peps.python.org/pep-0008/)

### Python interpreters

We will support only the official Python implementation, often called CPython.
Other choices (PyPy, Jython, IronPython, ...) do not have wide support and do not have good support for extension modules written for CPython, which are widespread.

Because `numpy` is a critical component of much of the scientific Python ecosystem, we will follow [NEP-29](https://numpy.org/neps/nep-0029-deprecation_policy.html) in deprecating old versions of Python and of `numpy`.
This is because we do not have more resources than do the `numpy` developers to support `numpy` on older versions of Python.

### Unit test library

[pytest](https://docs.pytest.org/en/stable/)

### Other utilities

As Python is a dynamically typed language, it does not support static checks that would normally be performed by a compiler.  We will instead use the following tools:

- code coverage tools such as [Codecov](https://github.com/marketplace/codecov)
- type annotations conforming to [PEP 484](https://peps.python.org/pep-0484/) and checked by [mypy](https://www.mypy-lang.org)
