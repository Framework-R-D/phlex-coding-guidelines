# C++ guidelines

Basis: [C++ Core Guidelines](https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines)

Exceptions:
1. Use east-`const` notation (at variance with [NL. 26 Use conventional const notation](https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines#Rl-const))

### Clang format

We will use `clang-format` to adopt a unified style:
- [Clang-format style file](.clang-format)

### Naming conventions

The namespace for C++ Phlex code is simply `phlex`, where two leading colons (i.e. `::phlex`) may be used to disambiguate between the top-level namespace and any nested namespaces.

We adopt the underscore-style or [snake-case](https://en.wikipedia.org/wiki/Snake_case) naming convention, consistent with the following C++ core guidelines:
- [NL.8: Use a consistent naming style](https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines#nl8-use-a-consistent-naming-style)
- [NL.9: Use `ALL_CAPS` for macro names only](https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines#nl9-use-all_caps-for-macro-names-only)
- [NL.10: Prefer `underscore_style` names](https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines#nl10-prefer-underscore_style-names)

The snake case convention will apply to variables, functions (free and member), classes, namespaces, files, and any C++ modules.

Note that the `SCREAMING_SNAKE_CASE` (or `ALL_CAPS` style) will be reserved for only macro names, consistent with the [NL.9 C++ core guideline](https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines#nl9-use-all_caps-for-macro-names-only) referenced above.

Exceptions to the snake-case rule include the names of:
- *executables*, which should prefer hyphens instead of underscores (e.g. `phlex-program` is easier to type than `phlex_program`)
- *template parameters*, which should prefer Pascal case (see [here](https://en.wikipedia.org/wiki/Camel_case) for distinction between Camel and Pascal cases)

<!- inspired by Celeritas and ROOT conventions -->

#### Symbol names

Functions should be verbs; classes should be names. As in standard Python (PEP-8-compliant) code, classes should use CapWordsStyle and variables use snake_case_style. A symbol should have a trailing underscore always and only if it is private member data: neither public member data nor private member functions should have them (public data member are expected to only be access via their containing symbol name (`mystruct.myvalue` or `this->myvalue` in the rare case of member function of struct with public data member).

Functors (classes whose instances act like a function) should be an *agent
noun*: the noun form of an action verb. Instances of a functor should be a
verb. For example::
```
   ModelEvaluator evaluate_something(parameters...);
   auto result = evaluate_something(arguments...);
```

#### Variable names

Generally speaking, variables should have short lifetimes and should be self-documenting. Avoid shorthand and “transliterated” mathematical expressions: prefer `constants::na_avogadro` to `N_A` (or express the constant functionally with `atoms_per_mole`) and use `atomic_number` instead of `Z`. Physical constants should try to have the symbol concatenated to the context or meaning (e.g. `c_light` or `h_planck`).

Use scoped enumerations (`enum class`) where possible (named like classes) so their values can safely be named like member variables (lowercase with underscores). Prefer enumerations to boolean values in function interfaces (since `do_something(true)` requires looking up the function interface definition to understand).

### Build system

[CMake](https://cmake.org/cmake/help/git-master/)

### Unit test library

[Catch2](https://github.com/catchorg/Catch2)
