## Convention
Languages looks different from one to another. While there're some academically approved ways to represent some concepts, some of them are not formalized. Here we decide to write some convention on the description of the feature so they are easier to read and reason about.

#### How trivial is trivial? 

We only accept features that is not wildly accepted by languages existing on the market up till 2022. It's true that langauges are evolving all the time, and some features may become trivial in the future. To keep everything simple, we decide to leave things as is.  

#### Format
The title of a feature should be within 30 words. If it's too long or your description doesn't precisely match what you mean, (e.g. "A 'SynthiGen' feature that will generate synthetic data for realistic simulations and testing." -- ChatGPT), then probably that feature is too complicated to use. 

At the end of the title, you should list 1 to 3 langauges with that feature in mind so people may look up more information on the internet. For each language listed, attach the name of that feature in that langauge. That language is not necessarily the earliest one, but it's recommended to choose a widely adaptted one or the one that have this feature as a primary tool to solve problems.

When using non-trivial terms, please attach some links that may explain it. Wikipedia is good enough. Some well-known terms can be leave as is. For example AST, dynamically-typed, etc.

Each feature is assigned a unique number, for the ease of indexing.

For each feature, write some keywords on how does it benefit the programmer who is using this feature. Also, write some keywords on how it will become a draw back.

Each feature may list a number of related feature id.

Use algol-like(C, Rust, Java, JavaScript) syntax when describing a feature, unless you have a better reason for using another syntax.
