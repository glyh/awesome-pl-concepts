[Rationale](https://github.com/glyh/nontrivial-PL-features/blob/main/rationale.md) [Convention](https://github.com/glyh/nontrivial-PL-features/blob/main/convention.md)

## List of features

### Code generation

Code generation is a set of techniques that generating codes via codes.

1. [runtime](https://en.wikipedia.org/wiki/Runtime_(program_lifecycle_phase)) and [compile-time](https://en.wikipedia.org/wiki/Compile_time) [AST](https://en.wikipedia.org/wiki/Abstract_syntax_tree)-based code generation in a [homoiconic](https://en.wikipedia.org/wiki/Homoiconicity) and [dynamically-typed](https://en.wikipedia.org/wiki/Type_system#Dynamic_type_checking_and_runtime_type_information) language -- [Lisp](https://lisp-lang.org/) [macros](https://lispcookbook.github.io/cl-cookbook/macros.html)
  - Pros: DRY, Productibility
  - Cons: Debuggablility, Readablility, Performance Predictablity

2. [compile-time](https://en.wikipedia.org/wiki/Compile_time) lisp macros that follows [lexical scope](https://en.wikipedia.org/wiki/Scope_(computer_science)#Lexical_scope) -- [Scheme](https://www.scheme.com/) [Hygeneic macro](https://docs.scheme.org/guide/macros/)
  - Related: 1
  - Pros: Debuggablility 

