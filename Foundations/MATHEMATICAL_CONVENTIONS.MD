# Mathematical Conventions for Math-Atlas

This document is the single reference for conventions used across the Foundations chapters. Individual chapters may introduce additional local notation, but they should not contradict these rules.

## Number systems

- $\mathbb{N}=\{0,1,2,\ldots\}$ throughout Math-Atlas.
- $\mathbb{N}_{>0}=\{1,2,3,\ldots\}$ denotes the positive integers.
- $\mathbb{Z}$, $\mathbb{Q}$, $\mathbb{R}$, and $\mathbb{C}$ denote the integers, rationals, reals, and complex numbers.

## Logic

- Unless stated otherwise, use classical two-valued logic.
- $P\Rightarrow Q$ is implication; $P\Leftrightarrow Q$ is biconditional.
- Quantifier domains must be stated or made unambiguous.
- Quantifier order is significant and must not be rearranged without justification.

## Sets and functions

- $A\subseteq B$ allows equality; $A\subsetneq B$ means proper subset. Avoid the potentially ambiguous $A\subset B$.
- Functions should state domain and codomain whenever injectivity, surjectivity, or inverse functions are discussed.
- The range/image of a function is a subset of its codomain and need not equal it.
- $f^{-1}(T)$ may denote the preimage of a set even when no inverse function exists; explain the context.

## Algebraic structures

- A ring in Math-Atlas has a multiplicative identity (unital ring) unless explicitly labelled non-unital.
- Ring multiplication is not assumed commutative unless stated.
- A field is a nontrivial commutative ring with identity in which each nonzero element has a multiplicative inverse.
- Ordered fields use a total order compatible with addition and multiplication.

## Equality, approximation, and operators

- Use $=$ for exact equality and $\approx$ for numerical approximation.
- Use $\equiv$ only with context: logical equivalence or congruence modulo a stated integer.
- Use $:=$ or words such as “define” for definitions.
- In displayed formulas intended for GitHub rendering, use constructions such as `\mathop{\text{Dom}}(R)` for named operators rather than `\operatorname{...}` when the latter causes renderer incompatibility.

## Computation

- Every Python example should state input assumptions and should be executable in its documented context.
- A finite computational check is not a proof of a statement over an infinite domain.
- Distinguish exact arithmetic from floating-point approximation.
- Do not rely on Python set iteration order for a reproducible displayed sequence.
