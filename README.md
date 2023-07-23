| [Rationale](rationale.md) | [Convention](convention.md) | [Contributing](contributing.md) | [TODO](TODO.md) |

## By topic

- Caching: [Caching with Reactive Invalidation](#caching-with-reactive-invalidation) 

- Calculus: [Dot Calculus](#dot-calculus), [Lambda Calculus](#lambda-calculus), [Symmetric Interaction Calculus](#symmetric-interaction-calculus), [Term Rewriting](#term-rewriting), [Turing Machine](#turing-machine)

- Code Generation: [Hygienic Macro](#hygienic-macro), [Lisp Macro](#lisp-macro), [Reader Macro](#reader-macro)

- Dependency: [Fragment Based Code Distribution](#fragment-based-code-distribution)

- Design Pattern: [Async/await](#asyncawait), [Continuation Passing](#continuation-passing), [Message Passing](#message-passing), [Type Constraints](#type-constraints)

- Pattern Matching: [Active Pattern](#active-pattern), [Pattern matching](#pattern-matching), [View Pattern](#view-pattern)

- Evaluation: [Compile-time Code Evaluation](#compile-time-code-evaluation), [Lazy Evaluation](#lazy-evaluation)

- First Class: [First Class Date](#first-class-date), [First Class Module](#first-class-module), [First Class Regex](#first-class-regex), [First Class Type](#first-class-type)

- Memory Management: [Garbage Collection](#garbage-collection), [Ownership](#ownership), [Reference Counting](#reference-counting)

- Mutitasking: [Async/await](#asyncawait), [Coroutine](#coroutine), [Green Thread](#green-thread), [Symmetric Interaction Calculus](#symmetric-interaction-calculus) 

- Paradigm: [Functional Programming](#functional-programming), [Logic Programming](#logic-programming)

- Polymorphism: [Row Polymorphism](#row-polymorphism)

- Property: [Referential Transparency](#referential-transparency)

- Subsystem: [Datalog](#datalog), [Module](#module)

- Syntax Sugar: [Automatic Broadcast Implementation](#automatic-broadcast-implementation), [Chained Try](#chained-try), [For Comprehension](#for-comphrehension), [Generalized Update Syntax](#generalized-update-syntax), [Universal Function Call Syntax](#universal-function-call-syntax)

- Type: [Algebraic Data Type](#algebraic-data-type), [Capability Safety](#capability-safety), [Dependent Type](#dependent-type), [Effect System](#dependent-type), [Generalized Algebraic Data Type](#generalized-algebraic-data-type), [Gradual Typing](#gradual-typing), [Linear Type](#linear-type), [Nil Fallthrough](#nil-fallthrough), [Reference Capabilities](#reference-capabilities)

## List of features

### Actor Model

### Active Pattern

### Algebraic Data Type

### [Async/await](https://en.wikipedia.org/wiki/Async/await)
  - Description: A syntax sugar for writing [asynchronous](https://en.wikipedia.org/wiki/Async/await) [concurrent](https://en.wikipedia.org/wiki/Concurrency_(computer_science)) code that looks serial. 
  - Implementation: [JavaScript](https://www.javascript.com/) [async-await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
  - Videos: [Fireship: The Async Await Episode I Promised](https://www.youtube.com/watch?v=vn3tm0quoqE&t=344s)

### Automatic Broadcast Implementation
  - Description: Given a definition `f: a -> b` and a functor `M`, `f: M a -> M b` is implemented automatically.
  - Implementation: [Chapel](https://chapel-lang.org/), [Matlab](https://www.mathworks.com/products/matlab.html) [array and matrix semantic](https://www.mathworks.com/help/matlab/learn_matlab/matrices-and-arrays.html) (partial)
  - Articles: [Hillel Wayne - Microfeatures I'd like to see in more languages](https://buttondown.email/hillelwayne/archive/microfeatures-id-like-to-see-in-more-languages/)

### Caching with Reactive Invalidation
  - Description: Caching the result of function, invalidating the data reactively when the cache are potentially outdated.
  - Implementation: [Skip](http://skiplang.com/docs/tutorial.html) [Caching with reactive invalidation](http://skiplang.com/)

### Capability Safety
  - Description: Functions cannot access data besides that reachable via their closure, their inputs, and global constants. Generally implied by [referential transparency](#referential-transparency), and incompatible with mutable global variables.
  - Implementations: [Pony](https://www.ponylang.io/), [Monte](http://www.monte-language.org/), [Wyvern](https://wyvernlang.github.io/)

### Chained Try
  - Description: A generalization of [optional chaining](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Optional_chaining) in [JavaScript](https://www.javascript.com/). A language construct that accepts a series of blocks where each block will be executed only if the previous blocks yield an error. 
  - Example Usage:
  ```js
  try {
      assert user_exists(name)
      current_user = get_user(name)
      assert user_not_banned(current_user)
      do_lots_of_stuff_with(current_user)
  } {
      deny_login_of_user(name)
  }

  // Replacing if-and-bind, like Python's walrus operator:
  try {
      match = regex.search("\d+(\d)", text)
      assert match
      process_numbers(match[0])
  } {
      match = regex.search("\w+(\d)", text)
      assert match
      process_letters(match[0])
  } {
      print("No match.")
  }

  // Replacing complicated conditions that would otherwise be in a single line.
  try {
      assert user.age > 18 and user.has_feature_enabled
      assert user.has_billing_account and user.get_credits() > 0
      assert user.get_last_payment().age_in_days < 90
      process_as_premium_user()
  } {
      process_as_normal_user()
  }

  // Replacing nested catch blocks:
  try {
      response = fetch_from_network(resource_id)
      assert response.network_success
      value = response.value
  } {
      assert resource_id in offline_cache
      value = offline_cache[resource_id]
  } {
      print("Failed to get resource. Use manual value?")
      response = user_input("Resource override: ")
      assert not response.cancelled
      value = response.value
  } {
      raise Error('Network not available and ID {resource_id} not in offline cache.')
  }
  print(value)


  ```
  - Articles: [BoppreH - a Reply in If-fail-else Construct](https://www.reddit.com/r/ProgrammingLanguages/comments/110bx5e/comment/j88xu52)

### Compile-time Code Evaluation
  - Description: Evaluation of code at [compile time](https://en.wikipedia.org/wiki/Compile_time).
  - Implementation: [Zig](https://ziglang.org/) [comptime](https://ziglang.org/documentation/master/#comptime), [Konna](https://github.com/eashanhatti/konna) [2LTT](https://www.reddit.com/r/ProgrammingLanguages/comments/rpe65y/konna_my_programming_language/)

### [Continuation Passing](https://en.wikipedia.org/wiki/Continuation-passing_style)
  - Description: a pattern in which the state of an executing program may be captured and passing around, resume on demand.
  - Implementation: [Scheme](https://www.scheme.com/) [continuation](https://cs.brown.edu/courses/cs173/2008/Manual/guide/Continuations.html)

### [Coroutine](https://en.wikipedia.org/wiki/Coroutine)
  - Description: A syntax sugar for structuring [cooperative](https://en.wikipedia.org/wiki/Cooperative_multitasking) [concurrent](https://en.wikipedia.org/wiki/Concurrency_(computer_science)) code modularly.
  - Implementation: [Lua](https://www.lua.org/) [coroutine](https://www.lua.org/pil/9.1.html)

### [Datalog](https://en.wikipedia.org/wiki/Datalog)

### Dependent Type
  - Articles: 
    - [Hacker News - serokell.io - Dependent Haskell Is the Future (2018)](https://news.ycombinator.com/item?id=20712646)
    - [pressron - Why Writing Correct Software Is Hard](https://pron.github.io/posts/correctness-and-complexity) 

### Dot Calculus
  - Articles: [Essense of Scala](https://www.scala-lang.org/blog/2016/02/03/essence-of-scala.html)

### Effect System
  - Description: A system similar to type system, but tracks [side effects](https://en.wikipedia.org/wiki/Side_effect_(computer_science)) instead of type of the value.
  - Implementation: [Koka](https://koka-lang.github.io/koka/doc/index.html) [effect system](https://en.wikipedia.org/wiki/Effect_system)
  - Articles: [Stephen Diehl - Exotic Programming Ideas: Part 3 (Effect Systems)](https://www.stephendiehl.com/posts/exotic03.html)

### First Class Date

### First Class Module
  - Description: Modules are treated as structs
  - Implementation: [1ML](https://github.com/rossberg/1ml), [Zig](https://ziglang.org), [Ocaml](https://v2.ocaml.org/) [First class module](https://v2.ocaml.org/manual/firstclassmodules.html)
  - Articles: [Stackoverflow - What (exactly) are "First Class" modules?](https://stackoverflow.com/questions/56575195/what-exactly-are-first-class-modules)

### First Class Regex

### First Class Type

### Fragment-based Code Distribution
  - Description: A compiler infrastructure that identify codes fragment by its hash.
  - Implementaion: [Haskell](https://www.haskell.org/) [fragnix](https://github.com/fragnix/fragnix), [Unison](https://www.unison-lang.org/) [hash identified AST](https://www.unison-lang.org/learn/tour/_big-technical-idea/)
  - Articles: [Big Technical Idea on Unison](https://www.unison-lang.org/learn/tour/_big-technical-idea/)

### For Comprehension

### Formal Methods
  - Description: A series of techiques that helps proving the behavior of the program
  - Implementation: [Coq](https://coq.inria.fr/) [proof assitant](https://en.wikipedia.org/wiki/Proof_assistant)

### Functional Programming

### [Garbage Collection](https://en.wikipedia.org/wiki/Garbage_collection_(computer_science))
  - Description: A system that free unused [heap-allocated](https://en.wikipedia.org/wiki/C_dynamic_memory_allocation) memory in [runtime](https://en.wikipedia.org/wiki/Runtime_system)
  - Implementation: [Common Lisp](https://lisp-lang.org/)

### Generalized Algebraic Data Type

### Generalized Update Syntax
  - Description: for any binary operator function `f : a -> a -> a`, we can rewrite `a = f a b` as `a f= b`
  - Implementation: [Noulith](https://github.com/betaveros/noulith/) [generalized update syntax](https://github.com/betaveros/noulith/)
  - Articles: 
    - [Hillel Wayne - Microfeatures I'd like to see in more languages](https://buttondown.email/hillelwayne/archive/microfeatures-id-like-to-see-in-more-languages/)

### [Gradual Typing](https://en.wikipedia.org/wiki/Gradual_typing)
  - Description: A type system that checks some expresions/variables at compile time while leaving others to the runtime type checker.
  - Implementation: [Typescript](https://www.typescriptlang.org/)
  - Articles:
    - [Vlad Balin - TypeScript: Static or Dynamic? The war is over.](https://itnext.io/typescript-static-or-dynamic-64bceb50b93e)

### [Green Thread](https://en.wikipedia.org/wiki/Green_thread)
  - Description: An abstraction that allow easily writing [preemptive](https://en.wikipedia.org/wiki/Preemption_(computing)) [concurrent](https://en.wikipedia.org/wiki/Concurrency_(computer_science)) code, without actually using OS thread
  - Implementation: [Java](https://www.java.com/) green thread

### Hygienic Macro
  - Description: [Lisp macros](#lisp-macros) that follows [lexical scope](https://en.wikipedia.org/wiki/Scope_(computer_science)#Lexical_scope).
  - Implementation: [Scheme](https://www.scheme.com/) [Hygienic macro](https://docs.scheme.org/guide/macros/)

### Lambda Calculus
  - Implementation: [pLam](https://github.com/slovnicki/pLam)

### Lazy Evaluation
  - Description: Any portion of the code is evaluated only when needed.
  - Implementation: [Haskell](https://www.haskell.org/) [lazy evaluation](https://wiki.haskell.org/Lazy_evaluation)

### Linear Type

### Lisp Macro
  - Description: [Compile-time](https://en.wikipedia.org/wiki/Compile_time) [AST](https://en.wikipedia.org/wiki/Abstract_syntax_tree)-based code generation in a [homoiconic](https://en.wikipedia.org/wiki/Homoiconicity) and [dynamically-typed](https://en.wikipedia.org/wiki/Type_system#Dynamic_type_checking_and_runtime_type_information) language.
  - Implementation: [Common Lisp](https://lisp-lang.org/) [macros](https://lispcookbook.github.io/cl-cookbook/macros.html)

### Logic Programming
  - Implementation: [Prolog](https://en.wikipedia.org/wiki/Prolog)

### Module 

### [Message Passing](https://en.wikipedia.org/wiki/Message_passing)
  - Implementation: [Erlang](https://www.erlang.org/) [concurrent programming](https://www.erlang.org/doc/getting_started/conc_prog.html), [Smalltalk](https://en.wikipedia.org/wiki/Smalltalk)

### Nil Fallthrough
  - Description: A generalization of [optional chaining](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Optional_chaining) in [JavaScript](https://www.javascript.com/), where any operation on nil will always yield nil.
  - Articles: 
    - [sporeboyofbigness - Call for action: let's build a list of features for non-trivial PL features](https://www.reddit.com/r/ProgrammingLanguages/comments/156bfwc/comment/jt047a5/?utm_source=share&utm_medium=web2x&context=3)

### Object Capabilities
  - Description: See [Capability safety](#capability-safety)

### Ownership
  - Description: A system that helps compiler decide when to free [heap-allocated memory](https://en.wikipedia.org/wiki/C_dynamic_memory_allocation) statically by annotating the ownership of heap allocated variables to entities in the program.
  - Implementation: [Rust](https://www.rust-lang.org/) [ownership](https://doc.rust-lang.org/book/ch04-00-understanding-ownership.html)

### Pattern matching 
  - Description: A structural way for obtain data from complicated [data structures](https://en.wikipedia.org/wiki/Data_structure).
  - Implementation: [Haskell](https://www.haskell.org/) [pattern matching](https://www.haskell.org/tutorial/patterns.html)

### Reader Macro
  - Description: Macro system that gets called by the reader, before AST is formed.
  - Implementation: [Common Lisp](https://lisp-lang.org/), [Elixir](https://elixir-lang.org/) [Sigils](https://elixir-lang.org/getting-started/sigils.html) (this is a weaker alternative to reader macro)
)

### Reference Capabilities
  - Description: A type system feature in which each reference carries a modifier to the capabilites, which can describe whether reading or writing is allowed, and whether these features are isolated to this reference.
  - Impelementation: [Pony](https://www.ponylang.io/)

### Reference Counting

### [Referential Transparency](https://en.wikipedia.org/wiki/Referential_transparency)
  - Description: A property for a function where: 1. returns the same for identical arguments; 2. has no other side effects.

### [Row Polymorphism](https://en.wikipedia.org/wiki/Row_polymorphism)
  - Description: A polymorphism that dispatch on concerned record fields and their type.
  - Implementation: [OCaml](https://ocaml.org/) [row polymorphism](https://www.cl.cam.ac.uk/teaching/1415/L28/rows.pdf)
  - Articles: 
    - [Jadon Fowler - Row Polymorphism without the Jargon](https://jadon.io/blog/row-polymorphism/)
    - [Stackoverflow - What are row types? Are they algebraic data types?](https://stackoverflow.com/questions/48092739/what-are-row-types-are-they-algebraic-data-types)
  - Paper: [Objective ML: An effective object-oriented extension to ML](https://caml.inria.fr/pub/papers/remy_vouillon-objective_ml-tapos98.pdf)

### Symmetric Interaction Calculus
  - Description: A calculus similar to [Lambda Calculus](https://en.wikipedia.org/wiki/Lambda_calculus), that can be implement concurrently due to its support for projection and duplication.
  - Implementation: [HVM](https://github.com/HigherOrderCO/HVM)
  - Articles: 
    - [Victor Maia - The Symmetric Interaction Calculus](https://medium.com/@maiavictor/the-abstract-calculus-fe8c46bcf39c)
    - [XXIIVV - interaction nets](https://wiki.xxiivv.com/site/interaction_nets.html)
    - [Zicklag - Interaction Nets, Combinators, and Calculus](https://zicklag.github.io/blog/interaction-nets-combinators-calculus/)
  - Papers:
    - [Interaction nets](https://dl.acm.org/doi/10.1145/96709.96718)

### Term Rewriting

### Type Constraints
  - Implementation: [Haskell](https://www.haskell.org/) [typeclass](https://www.haskell.org/tutorial/classes.html), [Rust](https://www.rust-lang.org/) [trait](https://doc.rust-lang.org/book/ch10-02-traits.html)

### Turing Machine

### [Universal Function Call Syntax](https://en.wikipedia.org/wiki/Uniform_Function_Call_Syntax)
  - Description: A syntax sugar for function call that makes chaining function calls easy.
  - Implementation: [Nim](https://nim-lang.org/) [UFCS](https://narimiran.github.io/nim-basics/#_calling_the_procedures), [Elixir](https://elixir-lang.org/) [pipe operator](https://elixir-lang.org/getting-started/enumerables-and-streams.html#the-pipe-operator), [Clojure](https://clojure.org/) [threading macro](https://clojure.org/guides/threading_macros)

### View Pattern
