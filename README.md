[Rationale](https://github.com/glyh/nontrivial-PL-features/blob/main/rationale.md) [Convention](https://github.com/glyh/nontrivial-PL-features/blob/main/convention.md)

## List of features

### Code generation

Code generation is the techniques for generating codes via codes.

1. AST-based code generation in a [homoiconic](https://en.wikipedia.org/wiki/Homoiconicity) and dynamically-typed language -- [Lisp](https://lisp-lang.org/) [macros](https://lispcookbook.github.io/cl-cookbook/macros.html)
  - Pros: DRY, Productibility
  - Cons: Debuggablility, Readablility

2. macros that follows lexical scope -- [Scheme](https://www.scheme.com/) [Hygeneic macro](https://docs.scheme.org/guide/macros/)
  - Related: 1
  - Pros: Debuggablility 

