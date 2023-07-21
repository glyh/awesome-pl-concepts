## Rationale
Features get reinvented over and over again. As a non-academic compiler writer I feel exhausted trying to catch up with all features possible in all languages.

However, they are of great importance in that it may inspire other people to design a better language. Hence I decide to start this project to keep track of all exisiting/imagined features that I can gather on the world, you can sort of think of this as a cheatsheet/treasure map for features of languages. 

## Convention
Languages looks different from one to another. While there're some academically approved ways to represent some concepts, some of them are not formalized. Here we decide to write some convention on the description of the feature so they are easier to read and reason about.

#### Format
The title of a feature should be within 30 words. If it's too long or your description doesn't precisely match what you mean, (e.g. "A 'SynthiGen' feature that will generate synthetic data for realistic simulations and testing." -- ChatGPT), then probably that feature is too complicated to use. 

At the end of the title, you should list 1 to 3 langauges with that feature in mind so people may look up more information on the internet.

When using non-trivial terms, please attach some links that may explain it. Wikipedia is good enough. Some well-known terms can be leave as is. For example AST, dynamically-typed, etc.

#### Language
Use algol-like(C, Rust, Java, JavaScript) syntax when describing a feature, unless you have a better reason for using another syntax.

## List of features

- AST-based [macro](https://en.wikipedia.org/wiki/Macro_(computer_science)) in a [homoiconic](https://en.wikipedia.org/wiki/Homoiconicity) and dynamically-typed language -- LISP
