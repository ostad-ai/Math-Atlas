# Algebra Conventions for Math-Atlas

This document supplements the repository-wide rules in `../Foundations/MATHEMATICAL_CONVENTIONS.MD`. It does not replace them. If a later chapter needs a special convention, it must state the convention locally and explain why it is needed.

## Domains and variables

- Unless stated otherwise, lowercase Latin letters such as $x$, $y$, and $t$ denote real variables in elementary algebra.
- A variable's domain must be stated whenever it affects admissible values, equivalence, or the solution set.
- Parameters are fixed quantities within a stated problem, even if their values are not specified. Distinguish parameters from variables when discussing a family of equations.
- Use $\mathbb{R}$ for the real numbers, $\mathbb{Z}$ for the integers, $\mathbb{Q}$ for the rationals, and $\mathbb{C}$ for the complex numbers, consistent with Foundations.

## Expressions, equations, and identities

- An **expression** denotes a value once its variables are assigned admissible values; it does not assert equality to another expression.
- An **equation** asserts that two expressions are equal and is solved for values satisfying the stated domain restrictions.
- An **identity** is an equality that holds for every admissible value of its variables.
- An **inequality** compares two quantities using an order relation.
- Use $\equiv$ only when its meaning is explicitly stated. Prefer “is an identity” in prose when there is risk of confusing identity with congruence.

## Equality-preserving transformations

- Adding the same quantity to both sides of an equation preserves its solution set.
- Multiplying both sides by a nonzero quantity preserves its solution set. If the multiplier may be zero, split cases or justify the operation.
- Dividing by an expression requires proving that the expression is nonzero on the solutions under consideration.
- Squaring both sides, taking even powers, or applying a non-injective function can introduce extraneous candidates. Check candidates in the original equation.
- Clearing denominators requires retaining all restrictions that made the original denominators nonzero.

## Fractions, powers, and radicals

- Write a fraction with explicit grouping when numerator or denominator contains more than one term: `\frac{a+b}{c+d}`.
- Use parentheses for negative bases when exponentiation is intended: $(-a)^2$ differs from $-a^2$.
- For real-valued even roots, the radicand must be nonnegative. For real-valued odd roots, negative radicands are allowed.
- For real $a>0$ and real $r$, define $a^r$ through the exponential/logarithmic definition in the chapter where real exponents are introduced. Do not silently extend integer-exponent rules beyond their domains.
- The principal square root $\sqrt{x}$ is nonnegative for $x\geq0$; it is not a two-valued symbol.

## Functions and graphs

- The general language of domain, codomain, image, composition, and inverse functions is established in Foundations, Chapter 03.
- Algebra chapters focus on specific function families and their formulas, graphs, restrictions, and models.
- Do not assume a graph is a function unless it passes the vertical-line test or its defining relation establishes uniqueness of output for each input.

## Notation and rendering

- Use `$...$` for inline mathematics and `$$...$$` on separate lines for display mathematics.
- Avoid `\operatorname` in GitHub-facing Markdown where the renderer may fail; prefer constructions such as `\mathop{\text{...}}` when a named operator is required.
- In Markdown table cells, avoid a raw `|` as mathematical content. Use `\lvert x\rvert` for absolute value or move the formula outside the table.
- Escape literal dollar signs that are not math delimiters, or write currency in prose to avoid ambiguity.

## Computation

- State whether a result is exact or approximate.
- Use integer or rational arithmetic when exactness matters; use floating-point arithmetic only with a stated tolerance or approximation context.
- A computer algebra system can verify or explore an identity, but a general proof still requires mathematical reasoning.
