# Algebra 08 — Polynomials and Polynomial Operations

## 1. Introduction

A **polynomial** is an algebraic expression built from constants and nonnegative integer powers of one or more variables, combined using addition and multiplication. Polynomials are central to algebra because they can be added, subtracted, multiplied, evaluated, and later used to define important families of functions and equations.

This chapter studies polynomials in **one variable** with real coefficients. It develops their vocabulary, standard form, degree, addition, subtraction, multiplication, and several frequently used product identities. Factoring and solving polynomial equations are deliberately postponed to Chapter 09. Polynomial functions, their zeros, graphs, and end behavior receive a fuller treatment in Chapter 14.

The chapter uses the exponent laws from Chapter 07 and the distributive property from Chapter 01. It does not treat negative powers as polynomial terms: an expression such as $x^{-2}+1$ is not a polynomial in $x$.

### Learning objectives

By the end of this chapter, a learner should be able to:

- Decide whether an expression is a polynomial in the stated variable.
- Identify terms, coefficients, exponents, the constant term, degree, and leading coefficient.
- Rewrite a polynomial in standard form and combine like terms.
- Add and subtract polynomials while preserving signs.
- Multiply monomials and polynomials using the distributive property.
- Derive and use the square-of-a-sum, square-of-a-difference, difference-of-squares, and product-of-two-binomial identities.
- Explain why the degree of a product of two nonzero real polynomials is the sum of their degrees.
- Evaluate a polynomial exactly or approximately at a specified input.
- Represent and manipulate polynomials with exact rational coefficients in Python.

## 2. What is a polynomial?

A polynomial in the variable $x$ with real coefficients has the form

$$
P(x)=a_nx^n+a_{n-1}x^{n-1}+\cdots+a_2x^2+a_1x+a_0,
$$

where each coefficient $a_i$ is real and each exponent is a nonnegative integer. Some coefficients may be zero. The displayed exponent $n$ is the degree only when $a_n\ne0$; zero leading coefficients must be removed before the degree is identified.

For example,

$$
P(x)=4x^5-3x^2+\frac12x-7
$$

is a polynomial. The missing $x^4$ and $x^3$ terms have coefficient zero, so an equivalent full listing is

$$
P(x)=4x^5+0x^4+0x^3-3x^2+\frac12x-7.
$$

By contrast, the following are not polynomials in $x$:

- $x^{-1}+2$, because it contains a negative exponent;
- $\sqrt{x}+1$, because $x^{1/2}$ is not a nonnegative integer power;
- $\dfrac{1}{x+1}$, because the variable occurs in a denominator;
- $2^x+1$, because the variable is an exponent rather than a nonnegative integer power.

These expressions may be meaningful on suitable domains, but they belong to other topics in this volume. Chapter 10 develops rational expressions, Chapter 11 develops radicals and rational exponents, and Chapter 16 develops exponential functions.

### 2.1 Coefficients and exponents

In the term $-\frac{3}{5}x^4$, the coefficient is $-\frac35$ and the exponent of $x$ is $4$. The coefficient includes its sign. The exponent is not the coefficient.

A nonzero constant such as $8$ is a polynomial of degree $0$: it is its own constant term. In formal polynomial notation, the degree-zero monomial $x^0$ denotes the constant polynomial $1$, so the constant may also be represented as $8x^0$. This is a polynomial convention: evaluating the constant polynomial at $x=0$ gives $8$. It is not an instruction to evaluate the scalar expression $0^0$, which Chapter 07 leaves undefined. The zero expression is also a polynomial, called the **zero polynomial**.

### 2.2 Terms and like terms

A **term** is a constant or a coefficient multiplied by a power of the variable. In one variable, two nonzero terms are **like terms** exactly when they have the same exponent of that variable.

For example, $7x^3$ and $-2x^3$ are like terms, while $7x^3$ and $-2x^2$ are not. Like terms can be combined by adding their coefficients:

$$
7x^3-2x^3=(7-2)x^3=5x^3.
$$

The powers of $x$ are not added when like terms are combined. The exponent stays the same.

## 3. Degree, leading coefficient, and standard form

For a **nonzero** polynomial, its **degree** is the greatest exponent whose coefficient is nonzero. When a polynomial is written in descending powers of $x$, it is in **standard form**.

The coefficient of the highest-degree term is the **leading coefficient**. The term itself is the **leading term**. The coefficient of $x^0$ is the **constant term**.

Consider

$$
P(x)=-6x^4+3x^2-\frac12x+9.
$$

Its degree is $4$, its leading term is $-6x^4$, its leading coefficient is $-6$, and its constant term is $9$.

### 3.1 Common names by number of terms

| Name | Meaning | Example |
|---|---|---|
| Monomial | One nonzero term | $-4x^3$ |
| Binomial | Two unlike nonzero terms | $x^2-5$ |
| Trinomial | Three unlike nonzero terms | $2x^2+x-7$ |

These names count terms **after** like terms have been combined and zero terms removed. For example, $x^2+3x-x^2+4$ simplifies to $3x+4$, a binomial rather than a four-term polynomial.

### 3.2 Degree conventions and the zero polynomial

A nonzero constant polynomial has degree $0$. The zero polynomial has **no degree in the convention used in this volume**, because it has no nonzero term and therefore no greatest exponent with a nonzero coefficient. Some advanced texts assign it degree $-\infty$ for convenience; this volume does not use that convention.

This distinction matters in statements about degree. Whenever a degree is used below, the polynomial is assumed to be nonzero unless explicitly stated otherwise.

### 3.3 Rewriting in standard form

To put an expression in standard form:

1. Expand products only when expansion is requested or useful.
2. Identify all terms with the same exponent.
3. Add their coefficients, including signs.
4. Remove terms whose combined coefficient is zero.
5. Arrange the remaining terms from highest exponent to lowest.

Example:

$$
3x-2x^3+5-x+4x^3-5
=2x^3+2x.
$$

The degree is $3$, not the largest exponent that appeared before simplification if the corresponding terms cancel.

## 4. Polynomial equality and identities

Two polynomial expressions are **equal as polynomials** when the coefficient of every power of the variable is the same after both expressions are written in standard form. For example,

$$
2(x^2+3x)-4x=2x^2+2x
$$

is an identity because expansion and collection of like terms produce the same coefficients on both sides.

Comparing coefficients is a reliable way to verify an identity after both sides have been expanded. Checking a few numerical values can detect some errors, but it cannot prove that two expressions are identical for every real input. A proof must use algebraic reasoning, such as the distributive property and coefficient comparison.

This chapter uses polynomial identity in the algebraic sense. The more extensive study of polynomial functions and their zeros is reserved for Chapter 14.

## 5. Adding and subtracting polynomials

Polynomials are added by adding the coefficients of like powers. The operation is performed power by power, including zero coefficients for any missing powers.

Let

$$
P(x)=3x^3-2x+5,\qquad Q(x)=x^3+4x^2+2x-1.
$$

Then

$$
\begin{aligned}
P(x)+Q(x)
&=(3+1)x^3+(0+4)x^2+(-2+2)x+(5-1)\\
&=4x^3+4x^2+4.
\end{aligned}
$$

Subtraction means adding the additive inverse of the second polynomial. Therefore **every term in the polynomial being subtracted changes sign**:

$$
\begin{aligned}
P(x)-Q(x)
&=3x^3-2x+5-(x^3+4x^2+2x-1)\\
&=3x^3-2x+5-x^3-4x^2-2x+1\\
&=2x^3-4x^2-4x+6.
\end{aligned}
$$

### 5.1 Degree of a sum

If $P$ and $Q$ are nonzero polynomials, then

$$
\deg(P+Q)\leq\max(\deg P,\deg Q),
$$

provided $P+Q$ is nonzero. The degree can be smaller because leading terms may cancel. For example,

$$
(x^4+2x)- (x^4-3x^2)=3x^2+2x.
$$

The degree drops from $4$ in each input polynomial to $2$ in the sum. If the sum is the zero polynomial, its degree is undefined under this volume's convention.

## 6. Multiplying polynomials

Polynomial multiplication follows from the distributive property: **each term of one factor must multiply every term of the other factor**. Then like terms are collected.

### 6.1 Multiplying a monomial by a polynomial

For example,

$$
\begin{aligned}
-3x^2(2x^3-x+4)
&=(-3x^2)(2x^3)+(-3x^2)(-x)+(-3x^2)(4)\\
&=-6x^5+3x^3-12x^2.
\end{aligned}
$$

The coefficient is multiplied and the exponents of the same base are added, as established in Chapter 07.

### 6.2 Multiplying two general polynomials

Let

$$
P(x)=2x^2-3x+4,\qquad Q(x)=x^2+5x-2.
$$

Distribute every term:

$$
\begin{aligned}
P(x)Q(x)
={}&2x^2(x^2+5x-2)\\
&-3x(x^2+5x-2)\\
&+4(x^2+5x-2)\\
={}&2x^4+10x^3-4x^2\\
&-3x^3-15x^2+6x\\
&+4x^2+20x-8\\
={}&2x^4+7x^3-15x^2+26x-8.
\end{aligned}
$$

A common error is to multiply only the first terms or to omit one of the cross-products. A box or area model can help organize all pairwise products, but the algebraic justification remains the distributive property.

### 6.3 A coefficient formula for multiplication

Write

$$
P(x)=\sum_{i=0}^{m}a_ix^i,
\qquad
Q(x)=\sum_{j=0}^{n}b_jx^j.
$$

Their product is

$$
P(x)Q(x)=\sum_{k=0}^{m+n}c_kx^k,
\qquad
c_k=\sum_{i+j=k}a_ib_j.
$$

For each exponent $k$, the coefficient $c_k$ is the sum of all products whose exponents add to $k$. This is the coefficient-convolution rule. It is the algebraic basis of the dictionary implementation in the Python section.

### 6.4 Degree of a product

If $P$ and $Q$ are nonzero real polynomials, then

$$
\deg(PQ)=\deg P+\deg Q.
$$

**Reason.** Suppose the leading terms are $a_mx^m$ and $b_nx^n$, where $a_m\ne0$ and $b_n\ne0$. The product contains the term $a_mb_nx^{m+n}$. Every other product of terms has exponent smaller than $m+n$. Since the real numbers have no zero divisors, $a_mb_n\ne0$, so this highest-degree term cannot disappear. Thus the degree is $m+n$.

The statement requires both factors to be nonzero. If either factor is the zero polynomial, their product is the zero polynomial and its degree is undefined here.

## 7. Special products

Several products occur frequently enough to memorize, but each formula follows from distribution. The variables $a$ and $b$ below may be any real numbers.

### 7.1 Square of a sum

$$
\begin{aligned}
(a+b)^2&=(a+b)(a+b)\\
&=a^2+ab+ba+b^2\\
&=a^2+2ab+b^2.
\end{aligned}
$$

Therefore

$$
\boxed{(a+b)^2=a^2+2ab+b^2.}
$$

The middle term is $2ab$, not $ab$.

### 7.2 Square of a difference

$$
\begin{aligned}
(a-b)^2&=(a-b)(a-b)\\
&=a^2-ab-ba+b^2\\
&=a^2-2ab+b^2.
\end{aligned}
$$

Thus

$$
\boxed{(a-b)^2=a^2-2ab+b^2.}
$$

The final term is positive because $(-b)(-b)=b^2$.

### 7.3 Difference of two squares

$$
\begin{aligned}
(a+b)(a-b)
&=a^2-ab+ab-b^2\\
&=a^2-b^2.
\end{aligned}
$$

Hence

$$
\boxed{(a+b)(a-b)=a^2-b^2.}
$$

The cross terms cancel. This identity is not the same as $(a-b)^2$.

### 7.4 Product of two binomials with a common leading variable

For real constants $r$ and $s$,

$$
\begin{aligned}
(x+r)(x+s)
&=x^2+sx+rx+rs\\
&=x^2+(r+s)x+rs.
\end{aligned}
$$

Therefore

$$
\boxed{(x+r)(x+s)=x^2+(r+s)x+rs.}
$$

This is a multiplication identity. The reverse use of such patterns as a factoring method is developed in Chapter 09.

## 8. Evaluating a polynomial

To **evaluate** a polynomial at $x=c$, replace every occurrence of $x$ by $c$ and carry out the arithmetic. Evaluation produces a number, not a new polynomial.

For

$$
P(x)=2x^3-3x^2+5,
$$

we obtain

$$
P(2)=2(2)^3-3(2)^2+5=16-12+5=9.
$$

The input may be an integer, rational number, or real approximation. If exactness matters, use exact rational inputs and coefficients rather than binary floating-point approximations.

### 8.1 Horner's method

A polynomial written in descending powers can be evaluated using nested multiplication. For example,

$$
2x^3-3x^2+0x+5=((2x-3)x+0)x+5.
$$

At $x=2$, the nested calculation is

$$
((2\cdot2-3)\cdot2+0)\cdot2+5=9.
$$

Horner's method reduces repeated power calculations and is convenient for exact computation. It does not change the mathematical value of the polynomial.

## 9. Common errors and checks

| Common error | Why it is wrong | Better check |
|---|---|---|
| Calling $x^{-2}+1$ a polynomial | Polynomial exponents must be nonnegative integers. | Inspect every exponent and every variable denominator. |
| Calling the zero polynomial degree zero | It has no nonzero term from which to choose a degree. | State separately that its degree is undefined in this volume. |
| Combining $3x^2$ and $4x^3$ | Their exponents differ, so they are unlike terms. | Combine only coefficients attached to the same power. |
| Forgetting to change every sign in subtraction | Subtracting a polynomial means adding its opposite. | Put parentheses around the entire second polynomial before distributing $-1$. |
| Multiplying only first terms | Distribution requires every term in one factor to multiply every term in the other. | Use a grid or write every pairwise product. |
| Writing $(a+b)^2=a^2+b^2$ | The two cross-products $ab$ and $ba$ are missing. | Expand $(a+b)(a+b)$ explicitly. |
| Assuming degree of a sum is always the larger input degree | Leading terms can cancel. | Combine like terms before reading the degree. |
| Treating a few numerical checks as proof of an identity | Agreement at selected inputs does not establish equality for all inputs. | Expand and compare coefficients or provide an algebraic derivation. |

## 10. Worked examples

### Example 1 — Is the expression a polynomial?

Classify each expression in $x$.

1. $5x^4-2x+1$: polynomial; all exponents are nonnegative integers.
2. $3x^{1/2}+1$: not a polynomial; the exponent $1/2$ is not an integer.
3. $\dfrac{x^2+1}{x}$: not a polynomial as written; it contains a variable in the denominator and simplifies to $x+x^{-1}$ on $x\ne0$.
4. $7$: nonzero constant polynomial of degree $0$.
5. $0$: zero polynomial; its degree is undefined in this volume.

### Example 2 — Identify degree and coefficients

Write $4-3x^2+0x^5+8x^4-2x^2$ in standard form and identify the degree and leading coefficient.

First combine the $x^2$ terms and remove the zero term:

$$
4-3x^2+8x^4-2x^2=8x^4-5x^2+4.
$$

The degree is $4$ and the leading coefficient is $8$.

### Example 3 — Add and subtract

Let $P(x)=2x^3-x^2+3x-4$ and $Q(x)=-x^3+4x^2-x+6$.

$$
P(x)+Q(x)=x^3+3x^2+2x+2.
$$

For subtraction, reverse every sign in $Q$:

$$
\begin{aligned}
P(x)-Q(x)
&=2x^3-x^2+3x-4+x^3-4x^2+x-6\\
&=3x^3-5x^2+4x-10.
\end{aligned}
$$

### Example 4 — Multiply a monomial and a trinomial

Expand $5x(2x^2-3x+4)$:

$$
5x(2x^2-3x+4)=10x^3-15x^2+20x.
$$

Each of the three terms was multiplied by $5x$.

### Example 5 — Multiply two binomials

Expand $(2x-3)(x+5)$:

$$
\begin{aligned}
(2x-3)(x+5)
&=2x^2+10x-3x-15\\
&=2x^2+7x-15.
\end{aligned}
$$

### Example 6 — Use a special product

Expand $(3x+4)^2$:

$$
(3x+4)^2=(3x)^2+2(3x)(4)+4^2=9x^2+24x+16.
$$

### Example 7 — Difference of squares

Expand $(5x-2)(5x+2)$:

$$
(5x)^2-2^2=25x^2-4.
$$

### Example 8 — Degree and leading coefficient of a product

Let $P(x)=-2x^4+3x-1$ and $Q(x)=5x^2-x+7$. The degrees are $4$ and $2$, and the leading coefficients are $-2$ and $5$. Their product has degree $6$ and leading coefficient $-10$, even before all lower terms are expanded.

### Example 9 — Evaluate exactly at a rational input

Let $P(x)=2x^2-\frac13x+\frac12$. Evaluate at $x=\frac32$:

$$
\begin{aligned}
P\left(\frac32\right)
&=2\left(\frac32\right)^2-\frac13\left(\frac32\right)+\frac12\\
&=\frac92-\frac12+\frac12=\frac92.
\end{aligned}
$$

### Example 10 — Verify an identity by expansion

Check whether $(x+2)^2-(x-2)^2=8x$ is an identity.

$$
\begin{aligned}
(x+2)^2-(x-2)^2
&=(x^2+4x+4)-(x^2-4x+4)\\
&=8x.
\end{aligned}
$$

The expansions agree for every real $x$, so the equality is an identity.

## 11. Exact polynomial computation with Python

A polynomial can be stored as a dictionary whose keys are exponents and whose values are coefficients. For example, `{3: Fraction(2), 1: Fraction(-3), 0: Fraction(5)}` represents $2x^3-3x+5$. Missing powers have coefficient zero. The empty dictionary `{}` represents the zero polynomial.

The self-contained Python implementation in the example below implements normalization, addition, subtraction, multiplication, degree, leading coefficient, and evaluation. It accepts integers and `Fraction` coefficients but rejects floating-point coefficients so exact results are not silently lost. Exponents must be nonnegative integers.

```python
from __future__ import annotations

# --- Inlined implementation: polynomial_core ---
"""Exact arithmetic helpers for univariate polynomials.

Representation: {exponent: coefficient}, with nonnegative integer exponents.
Coefficients are integers or fractions.Fraction values. The empty dictionary
represents the zero polynomial. Floating-point coefficients are rejected so
that exact rational arithmetic is not silently weakened.
"""


from fractions import Fraction
from typing import Mapping

Polynomial = dict[int, Fraction]


def _coerce_coefficient(value: object) -> Fraction:
    if isinstance(value, bool):
        raise TypeError("Boolean values are not polynomial coefficients")
    if isinstance(value, Fraction):
        return value
    if isinstance(value, int):
        return Fraction(value, 1)
    raise TypeError("coefficients must be integers or fractions.Fraction values")


def normalize(poly: Mapping[int, object]) -> Polynomial:
    """Validate a sparse polynomial and remove zero coefficients."""
    if not isinstance(poly, Mapping):
        raise TypeError("a polynomial must be supplied as a mapping")

    result: Polynomial = {}
    for exponent, raw_coefficient in poly.items():
        if isinstance(exponent, bool) or not isinstance(exponent, int):
            raise TypeError("exponents must be integers, not Booleans")
        if exponent < 0:
            raise ValueError("polynomial exponents must be nonnegative")
        coefficient = _coerce_coefficient(raw_coefficient)
        if coefficient:
            result[exponent] = result.get(exponent, Fraction(0)) + coefficient
    return dict(sorted(
        ((power, coeff) for power, coeff in result.items() if coeff),
        key=lambda item: item[0],
    ))


def add(left: Mapping[int, object], right: Mapping[int, object]) -> Polynomial:
    """Return the sum of two exact sparse polynomials."""
    a = normalize(left)
    b = normalize(right)
    result = dict(a)
    for exponent, coefficient in b.items():
        result[exponent] = result.get(exponent, Fraction(0)) + coefficient
    return normalize(result)


def subtract(left: Mapping[int, object], right: Mapping[int, object]) -> Polynomial:
    """Return left minus right."""
    a = normalize(left)
    b = normalize(right)
    result = dict(a)
    for exponent, coefficient in b.items():
        result[exponent] = result.get(exponent, Fraction(0)) - coefficient
    return normalize(result)


def multiply(left: Mapping[int, object], right: Mapping[int, object]) -> Polynomial:
    """Return the product using coefficient convolution."""
    a = normalize(left)
    b = normalize(right)
    result: Polynomial = {}
    for exp_a, coeff_a in a.items():
        for exp_b, coeff_b in b.items():
            exponent = exp_a + exp_b
            result[exponent] = (
                result.get(exponent, Fraction(0)) + coeff_a * coeff_b
            )
    return normalize(result)


def degree(poly: Mapping[int, object]) -> int:
    """Return the degree; the zero polynomial has no degree."""
    normalized = normalize(poly)
    if not normalized:
        raise ValueError("the zero polynomial has no degree in this convention")
    return max(normalized)


def leading_coefficient(poly: Mapping[int, object]) -> Fraction:
    """Return the coefficient of the highest nonzero power."""
    normalized = normalize(poly)
    if not normalized:
        raise ValueError("the zero polynomial has no leading coefficient")
    return normalized[max(normalized)]


def evaluate(poly: Mapping[int, object], value: object) -> Fraction:
    """Evaluate by Horner's method at an exact integer or Fraction input."""
    normalized = normalize(poly)
    x = _coerce_coefficient(value)
    if not normalized:
        return Fraction(0)

    highest = max(normalized)
    result = Fraction(0)
    for exponent in range(highest, -1, -1):
        result = result * x + normalized.get(exponent, Fraction(0))
    return result

# --- Chapter example ---
add = add
subtract = subtract
multiply = multiply
degree = degree
leading_coefficient = leading_coefficient
evaluate = evaluate

from fractions import Fraction




p = {2: Fraction(2), 1: Fraction(-3), 0: Fraction(4)}
q = {2: Fraction(1), 1: Fraction(5), 0: Fraction(-2)}

print("P + Q:", add(p, q))
print("P - Q:", subtract(p, q))
print("P * Q:", multiply(p, q))
print("degree(P):", degree(p))
print("leading coefficient of P:", leading_coefficient(p))
print("P(3/2):", evaluate(p, Fraction(3, 2)))

# A zero polynomial is represented by {} and has no degree.
zero = subtract(p, p)
print("P - P:", zero)
```

The dictionary is a computational representation, not a replacement for the algebraic definitions. The functions validate their input, combine coefficients with the same exponent, and remove zero coefficients after each operation. The exact arithmetic is useful for checking examples, but a computational output alone is not a proof of a general identity.

## 12. Exercises

### A. Recognition and vocabulary

1. Decide whether each expression is a polynomial in $x$: (a) $7x^3-2x+9$; (b) $x^{-1}+4$; (c) $\sqrt{x}+3$; (d) $-8$; (e) $0$.
2. For $P(x)=5x^6-2x^3+\frac14x-11$, state the degree, leading term, leading coefficient, and constant term.
3. Rewrite $3x^2-5+2x^4-7x^2+x-4$ in standard form.
4. Simplify $2x^3+4x-5x^3+7-4x+1$. State the degree and number of nonzero terms.
5. Explain why the zero polynomial has no degree under the convention used in this chapter.

### B. Addition and subtraction

6. Add $(3x^2-2x+5)+(x^2+7x-9)$.
7. Subtract $(2x^3-x+4)-(x^3+3x^2-5x-2)$.
8. Find the polynomial $R$ such that $R(x)+(2x^2-3x+1)=5x^2+x-4$.
9. Give an example of two degree-four polynomials whose sum has degree less than four. Explain the cancellation.

### C. Multiplication and special products

10. Expand $-4x^2(3x^3-2x+5)$.
11. Expand $(x+7)(x-3)$.
12. Expand $(2x-5)^2$.
13. Expand $(4x+1)(4x-1)$.
14. Expand $(x-2)(x+3)$ and collect like terms.
15. Multiply $P(x)=x^2-2x+1$ and $Q(x)=2x-3$.
16. If nonzero $P$ has degree $5$ and nonzero $Q$ has degree $3$, what is the degree of $PQ$? Explain why the leading coefficient cannot vanish.
17. Can the degree of $P+Q$ be smaller than both degrees of nonzero $P$ and $Q$? Explain or give a counterexample.

### D. Evaluation and reasoning

18. Evaluate $P(x)=3x^3-2x^2+x-4$ at $x=-2$.
19. Evaluate $Q(x)=\frac12x^2-\frac34x+1$ exactly at $x=2$.
20. Verify algebraically that $(x+3)^2-(x-3)^2=12x$.
21. A rectangle has side lengths $(x+2)$ and $(x+5)$. Write its area as a polynomial and state its degree.
22. A square has side length $(2t-1)$. Express its area as a polynomial in standard form.

### E. Computational thinking

23. Use the self-contained Python implementation in this chapter to add $P(x)=2x^3-x+1$ and $Q(x)=-2x^3+4x^2+x-1$. What is the resulting polynomial and why is its degree lower than the degree of either input?
24. Use exact rational coefficients to evaluate $R(x)=\frac23x^2-\frac15x+\frac17$ at $x=\frac32$. Report the answer as a reduced fraction.

## 13. Selected answers

1. (a) polynomial; (b) not a polynomial; (c) not a polynomial; (d) nonzero constant polynomial of degree $0$; (e) zero polynomial, degree undefined.
2. Degree $6$; leading term $5x^6$; leading coefficient $5$; constant term $-11$.
3. $2x^4-4x^2+x-9$.
4. $-3x^3+8$; degree $3$; two nonzero terms.
5. Every coefficient is zero, so there is no greatest exponent with a nonzero coefficient.
6. $4x^2+5x-4$.
7. $x^3-3x^2+4x+6$.
8. $R(x)=3x^2+4x-5$.
9. Example: $(x^4+2x)+( -x^4+3x^2)=3x^2+2x$; the degree-four leading terms cancel.
10. $-12x^5+8x^3-20x^2$.
11. $x^2+4x-21$.
12. $4x^2-20x+25$.
13. $16x^2-1$.
14. $x^2+x-6$.
15. $2x^3-7x^2+8x-3$.
16. Degree $8$. The product of the nonzero leading coefficients is nonzero in $\mathbb R$.
17. No. Since the degree of a nonzero sum is at most the larger input degree, it cannot be smaller than both if the input degrees differ; if they are equal, leading terms may cancel, but further terms can remain. It can be smaller than both: $P=x^3+x$, $Q=-x^3+x^2$ gives $P+Q=x^2+x$, degree $2$, which is smaller than each degree $3$.
18. $-38$.
19. $\frac32$.
20. Expanding gives $(x^2+6x+9)-(x^2-6x+9)=12x$.
21. $x^2+7x+10$, degree $2$.
22. $4t^2-4t+1$.
23. $4x^2$; the $x^3$, $x$, and constant terms cancel.
24. $\frac{47}{35}$.

## 14. Chapter summary

- A polynomial in one variable has real coefficients and only nonnegative integer exponents.
- The degree of a nonzero polynomial is the highest exponent with a nonzero coefficient. The zero polynomial has no degree in this volume's convention.
- Standard form lists powers in descending order after like terms are combined.
- Addition and subtraction combine coefficients of like powers; subtraction changes every sign in the second polynomial.
- Multiplication uses the distributive property for every pair of terms.
- For nonzero real polynomials, the degree of a product is the sum of the degrees.
- Special-product identities are consequences of distribution, not separate rules without proof.
- Evaluating a polynomial substitutes a value for its variable; exact rational arithmetic should use `Fraction`.
- Numerical checks support debugging but do not replace an algebraic proof of an identity.

## 15. Next chapter

**Chapter 09 — Factoring and Polynomial Equations** develops the reverse process of polynomial multiplication: greatest common factors, factoring by grouping, standard identities, the zero-product property, and solving polynomial equations. This chapter has used special-product identities only for expansion; systematic factoring begins in Chapter 09.

## References

- Math-Atlas Algebra, Chapter 01 — Algebraic Language and Expressions.
- Math-Atlas Algebra, Chapter 07 — Exponents and Scientific Notation.
- Math-Atlas Algebra Conventions — domains, exact arithmetic, and notation.
- OpenStax, *Algebra and Trigonometry 2e*, sections on polynomials and polynomial operations.

**Next chapter:** Chapter 09 — Factoring and Polynomial Equations.
