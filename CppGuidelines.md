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

### Build system

[CMake](https://cmake.org/cmake/help/git-master/)

### Unit test library

[Catch2](https://github.com/catchorg/Catch2)
