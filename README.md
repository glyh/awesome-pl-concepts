[Rationale](https://github.com/glyh/nontrivial-PL-features/blob/main/rationale.md) [Convention](https://github.com/glyh/nontrivial-PL-features/blob/main/convention.md) [Contributing](https://github.com/glyh/nontrivial-PL-features/blob/main/contributing.md)

## List of features

#### 1. [Compile-time](https://en.wikipedia.org/wiki/Compile_time) [AST](https://en.wikipedia.org/wiki/Abstract_syntax_tree)-based code generation in a [homoiconic](https://en.wikipedia.org/wiki/Homoiconicity) and [dynamically-typed](https://en.wikipedia.org/wiki/Type_system#Dynamic_type_checking_and_runtime_type_information) language -- [Lisp](https://lisp-lang.org/) [macros](https://lispcookbook.github.io/cl-cookbook/macros.html)
  - Pros: DRY, Productibility
  - Cons: Debuggablility, Readablility, Performance Predictablity

#### 2. lisp macros that follows [lexical scope](https://en.wikipedia.org/wiki/Scope_(computer_science)#Lexical_scope) -- [Scheme](https://www.scheme.com/) [Hygienic macro](https://docs.scheme.org/guide/macros/)
  - Related: [1](https://github.com/glyh/nontrivial-PL-features#1-compile-time-ast-based-code-generation-in-a-homoiconic-and-dynamically-typed-language----lisp-macros)
  - Pros: Debuggablility 

#### 3. Evaluation of code at [compile time](https://en.wikipedia.org/wiki/Compile_time) and compile-time [duck-typing](https://en.wikipedia.org/wiki/Duck_typing) -- [Zig](https://ziglang.org/) [comptime](https://ziglang.org/documentation/master/#comptime)
  - Pros: 
    - Eliminate the need of generics: generics are just compile time evaluated function from types to types
  - Cons: Compilation speed

#### 4. A structural way for obtain data from complicated [data structures](https://en.wikipedia.org/wiki/Data_structure) -- [Haskell](https://www.haskell.org/) [pattern matching](https://www.haskell.org/tutorial/patterns.html)
  - Pros: Readablility, Optimizabililty

#### 5. A syntax sugar for writing [preemptive](https://en.wikipedia.org/wiki/Preemption_(computing)) [concurrent](https://en.wikipedia.org/wiki/Concurrency_(computer_science)) code that looks serial -- [Javascript](https://www.javascript.com/) [async-await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
  - Pros: Readability
  - Cons: Uncontrolable
