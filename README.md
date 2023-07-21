## Rationale
Features get reinvented over and over again. As a non-academic compiler writer I feel exhausted trying to catch up with all features possible in all languages.

However, they are of great importance in that it may inspire other people to design a better language. Hence I decide to start this project to keep track of all exisiting/imagined features that I can gather on the world, you can sort of think of this as a cheatsheet/treasure map for features of languages. 

The reason I can't just look for papers are:
1. Papers are too long, it's a waste of time to read for engineers that just want to get thing done.
2. Some languages are designed by non-academic people, they don't have the motivation to document it.

For submission convention, see [here](https://github.com/glyh/nontrivial-PL-features/blob/main/convention.md).

## List of features

1. AST-based code generation in a [homoiconic](https://en.wikipedia.org/wiki/Homoiconicity) and dynamically-typed language -- [Lisp](https://lisp-lang.org/) [macros](https://lispcookbook.github.io/cl-cookbook/macros.html)
  - Pros: DRY, Productibility
  - Cons: Debuggablility, Readablility
