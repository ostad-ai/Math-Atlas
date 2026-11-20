# Algebra

**Math-Atlas — Algebra (working release v0.1)**

Algebra studies how quantities and relationships can be represented, transformed, and solved symbolically. This volume develops elementary and intermediate algebra from expressions and equations to polynomial, rational, exponential, and logarithmic models.

This is the first working release of the Algebra volume. It contains the complete curriculum map, the volume-specific conventions, and a fully drafted Chapter 01. The remaining chapters are planned, not presented as completed content.

## Scope and relationship to Foundations

Algebra builds on the language and reasoning established in **Foundations**. It does not repeat the general introductions to sets, relations, functions, number systems, proof techniques, or mathematical notation. Instead, it applies those ideas to algebraic expressions, equations, inequalities, and models.

Recommended Foundations references:

- `../Foundations/01_Propositional_Logic.MD` — logical statements and quantifiers used in definitions and proofs.
- `../Foundations/03_Relations_and_Functions.MD` — domain, codomain, image, composition, and inverse-function language.
- `../Foundations/04_Number_Systems_and_Mathematical_Structures.MD` — number systems and algebraic structures.
- `../Foundations/05_Mathematical_Proof_Techniques.MD` — proof methods used for algebraic identities and theorems.
- `../Foundations/07_Mathematical_Notation_and_Symbols.MD` — shared notation.
- `../Foundations/MATHEMATICAL_CONVENTIONS.MD` — repository-wide mathematical conventions.

A reader who has completed equivalent elementary arithmetic may begin Chapter 01 while consulting Foundations as needed. Formal proof language is introduced only when required and is not assumed to be mastered at the start.

## Learning objectives

By the end of the full Algebra volume, a learner should be able to:

- Translate verbal and contextual statements into algebraic expressions, equations, and inequalities.
- Simplify expressions while preserving equivalence and respecting domain restrictions.
- Solve linear, polynomial, rational, radical, exponential, and logarithmic equations within stated domains.
- Represent algebraic relationships with tables, graphs, formulas, and functions.
- Analyze systems of equations and inequalities.
- Select and justify appropriate algebraic methods rather than applying procedures mechanically.
- Build and interpret mathematical models, including checking assumptions and the reasonableness of results.
- Use Python and, where appropriate, symbolic-computation tools to explore algebra while distinguishing computation from proof.

## Curriculum map

### Part I — Elementary Algebra

| No. | Chapter | Main scope | Status |
|---:|---|---|---|
| 01 | Algebraic Language and Expressions | Variables, constants, terms, coefficients, evaluation, translating phrases, equivalent expressions, and the distributive property. | Drafted in v0.1 |
| 02 | Real-Number Properties and Algebraic Simplification | Real-number operations, order of operations, additive and multiplicative properties, signs, fractions, and simplification. | Planned |
| 03 | Linear Equations and Literal Equations | One-variable linear equations, formulas, rearrangement, identities, contradictions, and solution checking. | Planned |
| 04 | Linear Inequalities and Absolute Value | Inequality transformations, interval notation, compound inequalities, and absolute-value equations/inequalities. | Planned |
| 05 | Coordinate Graphs and Linear Models | Slope, intercepts, equations of lines, rate of change, and interpreting linear models. | Planned |
| 06 | Systems of Linear Equations | Substitution, elimination, graphical interpretation, consistency, and applications. | Planned |
| 07 | Exponents and Scientific Notation | Integer exponents, exponent laws, scientific notation, and growth/scaling contexts. | Planned |
| 08 | Polynomials and Polynomial Operations | Polynomial vocabulary, degree, addition, subtraction, multiplication, and special products. | Planned |
| 09 | Factoring and Polynomial Equations | Greatest common factors, grouping, standard identities, zero-product property, and polynomial equations. | Planned |
| 10 | Rational Expressions and Equations | Restrictions, simplifying rational expressions, operations, rational equations, and extraneous solutions. | Planned |
| 11 | Radicals and Rational Exponents | Roots, radical operations, rational exponents, equations involving radicals, and domain checks. | Planned |
| 12 | Quadratic Equations and Quadratic Models | Factoring, completing the square, quadratic formula, graphs, discriminant, and applications. | Planned |

### Part II — Intermediate Algebra

| No. | Chapter | Main scope | Status |
|---:|---|---|---|
| 13 | Complex Numbers | Imaginary unit, arithmetic, conjugates, modulus, and complex solutions. | Planned |
| 14 | Polynomial Functions and Equations | Zeros, multiplicity, end behavior, factor/remainder theorems, and polynomial models. | Planned |
| 15 | Rational Functions and Equations | Domains, asymptotes, discontinuities, transformations, and rational models. | Planned |
| 16 | Exponential Functions and Models | Exponential growth/decay, compound growth, transformations, and equations. | Planned |
| 17 | Logarithmic Functions and Equations | Logarithm definition, laws, change of base, inverse relationships, and equations. | Planned |
| 18 | Sequences, Series, and Binomial Expansion | Arithmetic/geometric sequences, finite series, recursive descriptions, and binomial expansion. | Planned |
| 19 | Nonlinear Systems and Inequalities | Intersections, substitution/elimination in nonlinear systems, and regions defined by inequalities. | Planned |
| 20 | Algebraic Modeling and Optimization | Model construction, parameter interpretation, constraints, sensitivity, and elementary optimization. | Planned |

## Pedagogical structure

Chapters will use the following structure where appropriate:

1. Motivation and learning objectives
2. Definitions and notation
3. Core properties and formulas
4. Explanations and derivations
5. Theorems and proofs when they add genuine value
6. Worked examples with explicit reasoning
7. Common errors and domain restrictions
8. Python implementations or computational experiments where useful
9. Exercises organized by difficulty and skill
10. Selected answers or solution outlines
11. References

Procedures must be accompanied by explanations of why they preserve equality or solution sets. A transformation that can introduce or remove candidate solutions must state the relevant conditions and require checking.

## Quality principles

- State the domain of every variable when it affects the result.
- Distinguish an expression, an equation, an identity, and an inequality.
- Distinguish equivalent expressions from equations with the same solutions only under stated restrictions.
- Never divide by an expression without considering whether it can be zero.
- Check solutions in the original equation after operations such as squaring, clearing denominators, or applying non-injective functions.
- Distinguish exact values from decimal approximations.
- Do not present numerical tests as proofs of general identities.
- Keep examples executable and describe their input assumptions.
- Keep GitHub Markdown tables free of unescaped pipe characters inside cells; use `\lvert` and `\rvert` for absolute-value delimiters inside table math.

## Python policy

Python examples should prioritize clarity and correctness over cleverness. Standard-library code is preferred for basic arithmetic. SymPy, NumPy, or plotting libraries may be introduced only when they materially improve the lesson. Never use Python's `eval` to evaluate learner-provided algebraic input.

## Current release contents

- `readme.MD` — scope, learning objectives, curriculum map, and quality principles.
- `ALGEBRA_CONVENTIONS.MD` — notation and algebra-specific conventions.
- `01_Algebraic_Language_and_Expressions.MD` — first complete chapter draft.
- `QA_VALIDATE.py` — structural checks for this working release.
- `QA_RESULTS_v0_1.txt` — latest local validation summary.

**Release status:** v0.1 is a curriculum and first-chapter draft, not a completed Algebra textbook.
