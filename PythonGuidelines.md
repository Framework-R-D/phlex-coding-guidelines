# Python Guidelines

Basis: [PEP-8](https://peps.python.org/pep-0008/)

### Unit test library

[pytest](https://docs.pytest.org/en/stable/)

### Other utilities

As Python is a dynamically typed language, it does not support static checks that would normally be performed by a compiler.  We will instead use the following tools:

- code coverage tools such as [Codecov](https://github.com/marketplace/codecov)
- type annotations conforming to [PEP 484](https://peps.python.org/pep-0484/) and checked by [mypy](https://www.mypy-lang.org)
