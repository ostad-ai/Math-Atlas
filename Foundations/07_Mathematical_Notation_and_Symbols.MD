# Foundations 07 — Mathematical Notation, Symbols, and Language

## 1. Introduction

Mathematics uses a precise symbolic language to describe quantities, relationships, structures, operations, and logical arguments.

Mathematical notation (نمادگذاری ریاضی) allows complex ideas to be expressed concisely and consistently.

A mathematical expression is not merely a collection of symbols. Its meaning depends on:

- The symbols being used.
- Their definitions.
- The mathematical domain in which they are interpreted.
- The rules governing their combination.

This chapter introduces the basic conventions that will be used throughout Math-Atlas.

---

## 2. Variables, Constants, and Parameters

### 2.1 Variables

A variable (متغیر) is a symbol representing an element of a specified domain.

Examples:

\[
x\in\mathbb{R}
\]

means that \(x\) is a real number.

\[
n\in\mathbb{N}
\]

means that \(n\) is a natural number.

Common conventions include:

| Symbols | Typical use |
|---|---|
| \(x,y,z\) | Real-valued variables |
| \(a,b,c\) | Constants or coefficients |
| \(i,j,k\) | Integer indices |
| \(m,n\) | Natural-number indices |
| \(u,v,w\) | Vectors or other mathematical objects |
| \(A,B,C\) | Sets, matrices, or structures |
| \(f,g,h\) | Functions |
| \(P,Q,R\) | Propositions or predicates |

These are conventions, not universal restrictions. A symbol can represent different objects in different contexts, provided its meaning is clearly defined.

### 2.2 Constants

A constant (ثابت) represents a fixed value within a particular context.

Examples include:

\[
\pi,\quad e,\quad \sqrt{2}.
\]

A parameter (پارامتر) is a quantity that remains fixed within a particular analysis but may vary between different models or problems.

For example:

\[
f(x)=ax^2+bx+c
\]

uses \(a,b,c\) as parameters and \(x\) as the variable.

---

## 3. Number Sets and Their Symbols

The following symbols describe common number systems.

| Symbol | Meaning |
|---|---|
| \(\mathbb{N}\) | Natural numbers |
| \(\mathbb{Z}\) | Integers |
| \(\mathbb{Q}\) | Rational numbers |
| \(\mathbb{R}\) | Real numbers |
| \(\mathbb{C}\) | Complex numbers |

A common convention is

\[
\mathbb{N}=\{0,1,2,3,\ldots\}.
\]

Some textbooks instead define natural numbers starting from 1. Math-Atlas uses the convention that includes zero unless a topic explicitly states otherwise.

The number systems are related by

\[
\mathbb{N}\subseteq\mathbb{Z}
\subseteq\mathbb{Q}
\subseteq\mathbb{R}
\subseteq\mathbb{C}.
\]

Examples:

\[
-3\in\mathbb{Z}
\]

\[
\frac{2}{5}\in\mathbb{Q}
\]

\[
\sqrt{2}\in\mathbb{R}\setminus\mathbb{Q}
\]

\[
3+2i\in\mathbb{C}.
\]

---

## 4. Basic Mathematical Relations

### 4.1 Equality and Inequality

| Symbol | Meaning |
|---|---|
| \(=\) | Equal to |
| \(\neq\) | Not equal to |
| \(<\) | Less than |
| \(>\) | Greater than |
| \(\leq\) | Less than or equal to |
| \(\geq\) | Greater than or equal to |
| \(\approx\) | Approximately equal to |
| \(\equiv\) | Context-dependent: identical, equivalent, or congruent |

The meaning of \(\equiv\) must be established by context.

For example, modular congruence is written as

\[
17\equiv 2\pmod 5.
\]

This means that 17 and 2 have the same remainder when divided by 5.

### 4.2 Membership and Set Relations

| Symbol | Meaning |
|---|---|
| \(\in\) | Is an element of |
| \(\notin\) | Is not an element of |
| \(\subseteq\) | Is a subset of |
| \(\subsetneq\) | Is a proper subset of |
| \(\supseteq\) | Contains as a subset |
| \(\varnothing\) | Empty set |
| \(\cup\) | Union |
| \(\cap\) | Intersection |
| \(\setminus\) | Set difference |
| \(\mathcal{P}(A)\) | Power set of \(A\) |

For example,

\[
2\in\{1,2,3\}
\]

and

\[
\{1,2\}\subseteq\{1,2,3\}.
\]

The distinction between an element and a subset is important:

\[
2\in\{1,2,3\}
\]

but

\[
\{2\}\subseteq\{1,2,3\}.
\]

---

## 5. Logical Symbols

Mathematical statements use logical symbols to express relationships between propositions.

| Symbol | Meaning |
|---|---|
| \(\neg P\) | Negation |
| \(P\land Q\) | Conjunction |
| \(P\lor Q\) | Disjunction |
| \(P\Rightarrow Q\) | Implication |
| \(P\Leftrightarrow Q\) | Logical equivalence |
| \(\forall\) | For all |
| \(\exists\) | There exists |
| \(\exists!\) | There exists exactly one |
| \(\therefore\) | Therefore |
| \(\because\) | Because |

### 5.1 Universal Quantification

The statement

\[
\forall x\in\mathbb{R},\quad x^2\geq0
\]

means that every real number has a nonnegative square.

### 5.2 Existential Quantification

The statement

\[
\exists x\in\mathbb{Z},\quad x^2=9
\]

means that there exists an integer whose square is 9.

### 5.3 Unique Existence

The statement

\[
\exists!x\in\mathbb{R},\quad x+2=5
\]

means that exactly one real number satisfies the equation.

That number is \(x=3\).

### 5.4 Implication and Equivalence

An implication

\[
P\Rightarrow Q
\]

states that if \(P\) is true, then \(Q\) is true.

A biconditional

\[
P\Leftrightarrow Q
\]

states that both implications hold:

\[
(P\Rightarrow Q)\land(Q\Rightarrow P).
\]

---

## 6. Arithmetic and Algebraic Symbols

| Symbol | Meaning |
|---|---|
| \(+\) | Addition |
| \(-\) | Subtraction |
| \(\times\), \(\cdot\) | Multiplication |
| \(/\), \(\div\) | Division |
| \(a^n\) | Exponentiation |
| \(\sqrt{x}\) | Square root |
| \(\sqrt[n]{x}\) | \(n\)-th root |
| \(|x|\) | Absolute value |
| \(a\bmod b\) | Remainder modulo \(b\) |
| \(\sum\) | Summation |
| \(\prod\) | Product |

### 6.1 Summation Notation

The expression

\[
\sum_{k=1}^{n}k
\]

means

\[
1+2+\cdots+n.
\]

More generally,

\[
\sum_{k=m}^{n}a_k
=
a_m+a_{m+1}+\cdots+a_n.
\]

### 6.2 Product Notation

The expression

\[
\prod_{k=1}^{n}k
\]

means

\[
1\cdot2\cdot\ldots\cdot n=n!.
\]

### 6.3 Absolute Value

For a real number \(x\),

\[
|x|=
\begin{cases}
x & x\geq0,\\
-x & x<0.
\end{cases}
\]

Absolute value represents distance from zero on the real number line.

For example,

\[
|-7|=7.
\]

---

## 7. Functions and Mappings

A function (تابع) maps every element of a specified domain to exactly one element of a codomain.

The notation

\[
f:A\to B
\]

indicates a function from set \(A\) to set \(B\).

For an element \(x\in A\), its image is written as

\[
f(x).
\]

Example:

\[
f:\mathbb{R}\to\mathbb{R}
\]

\[
f(x)=x^2.
\]

Then

\[
f(3)=9.
\]

Important function-related notation includes:

| Symbol | Meaning |
|---|---|
| \(f(x)\) | Function value at \(x\) |
| \(f^{-1}\) | Inverse function, when it exists |
| \(f\circ g\) | Function composition |
| \(\operatorname{dom}(f)\) | Domain |
| \(\operatorname{range}(f)\) | Range |
| \(\operatorname{Im}(f)\) | Image of a function |
| \(f:A\to B\) | Mapping from \(A\) to \(B\) |

The notation \(f^{-1}(x)\) refers to the inverse function when one exists. It does not generally mean \(1/f(x)\).

---

## 8. Calculus Notation

Calculus uses specialized notation for limits, derivatives, and integrals.

### 8.1 Limits

\[
\lim_{x\to a}f(x)=L
\]

means that \(f(x)\) approaches \(L\) as \(x\) approaches \(a\).

### 8.2 Derivatives

The derivative of \(f\) can be written as

\[
f'(x),\qquad
\frac{df}{dx},\qquad
\frac{d}{dx}f(x).
\]

For example, if

\[
f(x)=x^2,
\]

then

\[
f'(x)=2x.
\]

### 8.3 Integrals

The indefinite integral is written as

\[
\int f(x)\,dx.
\]

The definite integral is written as

\[
\int_a^b f(x)\,dx.
\]

For example,

\[
\int_0^1 x^2\,dx=\frac13.
\]

### 8.4 Partial Derivatives

For a function of several variables,

\[
f(x,y)=x^2+3xy+y^2,
\]

the partial derivatives are written as

\[
\frac{\partial f}{\partial x},
\qquad
\frac{\partial f}{\partial y}.
\]

They describe differentiation with respect to one variable while holding the other variables constant.

---

## 9. Linear Algebra Notation

Linear algebra uses conventions that distinguish scalars, vectors, and matrices.

| Notation | Meaning |
|---|---|
| \(a\) | Scalar |
| \(\mathbf{v}\) | Vector |
| \(A\) | Matrix |
| \(A^T\) | Transpose |
| \(A^{-1}\) | Matrix inverse, when it exists |
| \(I\) | Identity matrix |
| \(\det(A)\) | Determinant |
| \(\operatorname{rank}(A)\) | Matrix rank |
| \(\mathbf{0}\) | Zero vector |
| \(\langle u,v\rangle\) | Inner product |

For example,

\[
A=
\begin{bmatrix}
1&2\\
3&4
\end{bmatrix}
\]

and

\[
\mathbf{x}=
\begin{bmatrix}
5\\
6
\end{bmatrix}.
\]

Their matrix product is

\[
A\mathbf{x}
=
\begin{bmatrix}
17\\
39
\end{bmatrix}.
\]

---

## 10. Probability and Statistics Notation

Probability and statistics use symbols to describe random variables, distributions, and numerical summaries.

| Symbol | Meaning |
|---|---|
| \(P(A)\) | Probability of event \(A\) |
| \(P(A\mid B)\) | Conditional probability |
| \(X\) | Random variable |
| \(E[X]\) | Expected value |
| \(\operatorname{Var}(X)\) | Variance |
| \(\sigma\) | Population standard deviation |
| \(\mu\) | Population mean |
| \(\bar{x}\) | Sample mean |
| \(s\) | Sample standard deviation |
| \(n\) | Sample size |
| \(\sim\) | Follows a specified distribution |

For example,

\[
X\sim\mathcal{N}(\mu,\sigma^2)
\]

means that random variable \(X\) follows a normal distribution with mean \(\mu\) and variance \(\sigma^2\).

---

## 11. Common Greek Letters

Greek letters are widely used in mathematics, statistics, and scientific computing.

| Symbol | Name | Common uses |
|---|---|---|
| \(\alpha\) | Alpha | Angles, significance levels |
| \(\beta\) | Beta | Coefficients, parameters |
| \(\gamma\) | Gamma | Constants, functions |
| \(\delta\) | Delta | Small changes, tolerances |
| \(\Delta\) | Capital Delta | Differences, discriminants |
| \(\epsilon\) | Epsilon | Small positive quantities |
| \(\theta\) | Theta | Angles, model parameters |
| \(\lambda\) | Lambda | Eigenvalues, parameters |
| \(\mu\) | Mu | Population mean |
| \(\sigma\) | Sigma | Standard deviation |
| \(\Sigma\) | Capital Sigma | Summation |
| \(\pi\) | Pi | Circle constant |
| \(\rho\) | Rho | Correlation, density |
| \(\phi\) | Phi | Angles, functions |
| \(\omega\) | Omega | Angular frequency, sample spaces |

These uses are common conventions rather than strict rules.

---

## 12. Mathematical Notation in Python

Python does not use mathematical notation exactly as written in textbooks. Mathematical symbols must be translated into programming-language expressions.

| Mathematics | Python |
|---|---|
| \(a+b\) | `a + b` |
| \(a-b\) | `a - b` |
| \(a\times b\) | `a * b` |
| \(a/b\) | `a / b` |
| \(a^b\) | `a ** b` |
| \(\sqrt{x}\) | `math.sqrt(x)` |
| \(|x|\) | `abs(x)` |
| \(a\bmod b\) | `a % b` |
| \(a=b\) | `a == b` |
| \(a\neq b\) | `a != b` |
| \(a\leq b\) | `a <= b` |
| \(a\geq b\) | `a >= b` |

**Important distinction:** In Python, `^` is the bitwise XOR operator, not exponentiation. Use `**` for powers.

### 12.1 Summation

Mathematical expression:

\[
S=\sum_{k=1}^{n}k^2.
\]

Python implementation:

```python
def sum_of_squares(n):
    return sum(k**2 for k in range(1, n + 1))


print(sum_of_squares(5))  # 55
```

### 12.2 Mathematical Sets

```python
A = {1, 2, 3}
B = {3, 4, 5}

print(A | B)  # Union
print(A & B)  # Intersection
print(A - B)  # Difference
```

### 12.3 Functions

Mathematical definition:

\[
f(x)=x^2+2x+1.
\]

Python implementation:

```python
def f(x):
    return x**2 + 2*x + 1


print(f(3))  # 16
```

### 12.4 Numerical Approximation

Some mathematical operations cannot be represented exactly using ordinary floating-point numbers.

For example:

```python
import math

x = math.sqrt(2)

print(x)
print(x * x)
print(math.isclose(x * x, 2.0))
```

The final result is a numerical approximation, not an exact symbolic proof.

For exact symbolic mathematics, libraries such as SymPy can be used.

---

## 13. Notation Conventions for Math-Atlas

To maintain consistency across the repository, the following conventions will be adopted.

### 13.1 Variables and Objects

- Lowercase Latin letters represent scalar variables unless stated otherwise.
- Uppercase Latin letters represent sets, matrices, or named structures.
- Bold lowercase letters represent vectors.
- Greek letters commonly represent parameters, angles, or specialized quantities.
- Subscripts identify indexed quantities.

Examples:

\[
x,\quad A,\quad \mathbf{v},\quad
\theta,\quad a_n.
\]

### 13.2 Function Definitions

Functions should explicitly specify their domain and codomain whenever these are mathematically relevant.

Preferred:

\[
f:\mathbb{R}\to\mathbb{R},
\qquad f(x)=x^2.
\]

Avoid leaving the domain and codomain ambiguous when they affect the mathematical properties being discussed.

### 13.3 Sequences

Sequences will generally use indexed notation:

\[
(a_n)_{n=0}^{\infty}.
\]

When the starting index matters, it must be stated explicitly.

### 13.4 Sets

Set definitions will use braces:

\[
A=\{1,2,3,4\}.
\]

Set-builder notation will use:

\[
A=\{x\in\mathbb{Z}:x>0\}.
\]

### 13.5 Approximation and Equality

The symbol \(=\) should be reserved for exact equality.

Use \(\approx\) for numerical approximations.

For example,

\[
\sqrt{2}\approx1.4142.
\]

### 13.6 Definitions and Theorems

Every important mathematical object should be introduced with a clear definition.

Theorems should state their assumptions and conclusions explicitly.

Proofs should distinguish between:

- Assumptions.
- Intermediate deductions.
- Final conclusions.

### 13.7 Code and Mathematical Expressions

When mathematical notation is translated into Python:

- State any assumptions about input types and valid ranges.
- Distinguish exact arithmetic from floating-point approximation.
- Explain differences between mathematical operators and programming operators.
- Include examples that can be executed independently.

---

## 14. Exercises

### Exercise 1 — Symbol Interpretation

Explain the meaning of each expression:

1. \(x\in\mathbb{Q}\)
2. \(A\subseteq B\)
3. \(\forall x\in\mathbb{R}\)
4. \(\exists!x\in\mathbb{Z}\)
5. \(f:A\to B\)
6. \(P(A\mid B)\)
7. \(\sum_{k=1}^{n}k\)
8. \(\det(A)\)

### Exercise 2 — Translate into Mathematical Notation

Express each statement symbolically.

1. Every positive integer has a successor.
2. There exists a real number whose square is 2.
3. Every element of set \(A\) is also an element of set \(B\).
4. The function \(f\) maps real numbers to real numbers.
5. The sum of the first \(n\) positive integers.

### Exercise 3 — Translate into Python

Write Python expressions or functions for:

1. \(x^3+2x^2-5x+1\)
2. \(\sqrt{x^2+y^2}\)
3. \(\sum_{k=1}^{n}k^3\)
4. The absolute difference between two numbers.
5. The intersection of two finite sets.

### Exercise 4 — Identify Ambiguity

Explain why the following statements require additional information:

1. \(f(x)=x^2\)
2. \(A\subset B\)
3. \(n\in\mathbb{N}\)
4. \(a\equiv b\)
5. \(x^{-1}\)

### Exercise 5 — Mathematical and Computational Precision

Explain the difference between:

1. \(=\) and \(\approx\).
2. \(f^{-1}(x)\) and \(1/f(x)\).
3. \(a^b\) in mathematics and `a ^ b` in Python.
4. An exact symbolic result and a floating-point approximation.

---

## 15. References

1. Kenneth H. Rosen, *Discrete Mathematics and Its Applications*. McGraw-Hill.
2. Susanna S. Epp, *Discrete Mathematics with Applications*. Cengage Learning.
3. Richard Courant and Herbert Robbins, *What Is Mathematics?* Oxford University Press.
4. George B. Thomas, Maurice D. Weir, and Joel Hass, *Thomas' Calculus*. Pearson.
5. Gilbert Strang, *Introduction to Linear Algebra*. Wellesley-Cambridge Press.

---

## 16. Summary

Mathematical notation is the common language connecting definitions, theorems, proofs, algorithms, and computational implementations.

This chapter established conventions for:

- Variables, constants, and parameters.
- Number systems and set relations.
- Logical and algebraic symbols.
- Functions and mappings.
- Calculus and linear algebra.
- Probability and statistics.
- Greek letters.
- Translation between mathematical expressions and Python.
- Consistent notation throughout Math-Atlas.

A consistent notation system makes mathematical content easier to read, verify, extend, and implement.