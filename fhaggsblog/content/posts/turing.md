+++
title = 'Turing machines and great powers'
date = 2025-08-19T12:12:22-03:00
draft = false
+++
Why do we have bugs?

<!--more-->
---
### The Pursuit of Mathematical Certainty

In the early 20th century, the mathematician David Hilbert posed a challenge. He envisioned a universal method, an effective procedure or "truth machine," that could take any mathematical statement and decide, once and for all, whether it was true or false. This was a central component of his program to formalize all of mathematics and resolve the foundational crisis that had emerged from paradoxes in logic and set theory, such as Russell’s paradox. Hilbert believed that by mechanizing mathematical reasoning, certainty could be restored.

In response to this challenge, Alan Turing described a theoretical "automatic machine" (or *a-machine*), the model we now call the **Turing machine**. The purpose was not to construct a physical device but to create a formal model that could capture the essence of any conceivable computation.

However, Hilbert's dream was ultimately proven to be unattainable. In 1931, Kurt Gödel published his incompleteness theorems. He demonstrated that any consistent formal system powerful enough to describe arithmetic will inevitably contain true statements that cannot be proven within the system itself. This implied that no single, complete set of rules could ever capture the entirety of mathematical truth. A system could be designed to produce only truths (making it sound), but it would necessarily be incomplete. Hilbert's vision of a complete and mechanically decidable mathematics was therefore impossible.

---

### The Halting Problem and Static Analysis

Turing extended this concept from mathematical proof to computation itself. He showed that fundamental limits exist on what can be computed in principle. His most famous illustration of this is the **Halting Problem**, which asks if an algorithm can exist that, given an arbitrary program and its input, can determine whether that program will eventually halt or run forever.

The answer is no. No such universal algorithm can exist. This was a direct blow to Hilbert’s vision; if one cannot even determine whether a simple program will halt, one certainly cannot build a machine to decide the truth of all mathematical statements.

This theoretical limit has a direct practical consequence in a field we now call **static analysis**. The Halting Problem is the canonical example of an undecidable property. If a perfect static analyzer existed, it could inspect any program's source code and determine with certainty whether it would halt, contain bugs, or perform its intended function correctly. Such a tool would eliminate the need for most forms of testing, as the compiler could simply verify the program's correctness. Because of the Halting Problem, we know this is impossible in the general case. Static analysis can be a powerful tool, but it can never be perfect.

---

### The Trade-off in Language Design

This fundamental limit forces a trade-off in the design of programming languages: the more powerful and expressive a language is (i.e., Turing-complete), the less can be proven about its behavior statically. Conversely, the simpler the language, the more guarantees a compiler or interpreter can provide before the program is executed.

This is why simple, non-Turing-complete data formats like YAML or JSON are used for configuration. Their lack of arbitrary loops or conditionals makes them easy to parse, validate, and verify for correctness.

The Rust programming language offers a compelling modern example of this principle. Its design deliberately restricts the set of valid programs to prioritize safety that can be proven statically. The compiler's **borrow checker** enforces a strict set of rules regarding data ownership, lifetimes, and mutability. As a result, entire classes of common bugs, such as use-after-free errors and data races, are eliminated at compile time.

This safety comes at a cost. Not all objectively correct programs are accepted by the compiler; it only permits a subset of safe programs, namely, those whose safety it can prove through its analysis. This echoes Turing's insight: one cannot have everything. A language can either allow maximum expressiveness at the risk of undetectable errors or restrict expressiveness to gain stronger guarantees.

For situations requiring low-level control, Rust provides the `unsafe` keyword. This keyword signals that the programmer is manually taking responsibility for upholding the language's safety invariants, allowing an escape from the compiler's restrictions when absolutely necessary.

### Funny personal note  

When I just started programming, way before college, I was using Python. I didn’t know anything about computability theory or Turing machines. But one thing I noticed, even as a total noob, was how much nicer it felt when my editor caught mistakes early.  

If I forgot a colon or messed up indentation, the editor would add a little red line under my code. I preferred that a lot compared to running the program and getting a runtime error. Even back then, I realized errors caught before execution are way easier to deal with. I didn’t know the word “static analysis” yet, but I already liked the idea of having my mistakes flagged as soon as possible, even if no one taught me that. I also wondered why my editor did not tell me about this runtime error before. That is why I wanted to write this blog post, If you've taken a CS class, you may already know this, but this post is a gift to the me from the past.