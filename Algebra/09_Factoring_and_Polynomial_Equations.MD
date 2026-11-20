# Algebra 09 — Factoring and Polynomial Equations

## 1. Introduction

Chapter 08 developed polynomial addition and multiplication. This chapter studies an important reverse process: **factoring**. To factor a polynomial is to express it as a product of simpler polynomial factors. Factoring is useful in its own right, but it is especially powerful when a polynomial equation is equal to zero.

The central logical principle is the **zero-product property**: over the real numbers, a finite product is zero if and only if at least one factor is zero. This turns a factored polynomial equation into simpler equations. The property does not say that each factor of a nonzero product must be zero; that distinction is essential.

The chapter covers greatest common factors, factoring by grouping, quadratic trinomials, standard identities, and solving polynomial equations by factoring. It does not yet develop the general factor theorem, remainder theorem, or full analysis of polynomial functions; those topics are reserved for Chapter 14.

### Learning objectives

By the end of this chapter, a learner should be able to:

- Explain factoring as the reverse of polynomial multiplication.
- Factor out a greatest common monomial factor, including a rational numerical content.
- Factor four-term expressions by grouping when a common binomial factor appears.
- Factor quadratic trinomials over the integers or rationals when suitable factors exist.
- Recognize and justify difference-of-squares, perfect-square-trinomial, and sum/difference-of-cubes identities.
- Distinguish a factorization over the integers or rationals from one over the reals or complex numbers.
- State and apply the zero-product property with the correct hypotheses.
- Solve polynomial equations by factoring and check the resulting candidates in the original equation.
- Use exact Python arithmetic to extract a greatest common factor and verify a proposed factorization.

## 2. Factoring and the coefficient domain

A **factorization** writes a polynomial as a product:

$$
P(x)=A(x)B(x).
$$

For example,

$$
x^2-5x+6=(x-2)(x-3).
$$

Expanding the right-hand side recovers the left-hand side. Thus, expansion and factoring reverse one another in this example.

### 2.1 What does “completely factored” mean?

A polynomial may factor differently depending on the allowed coefficients. For instance,

$$
x^2-2=(x-\sqrt{2})(x+\sqrt{2})
$$

is a factorization into real linear factors, but it does not factor into linear factors with rational coefficients. By contrast, $x^2+1$ has no real linear factorization, although over the complex numbers it factors as $(x-i)(x+i)$.

Therefore, statements such as “irreducible” or “completely factored” must name the coefficient domain when it matters. In the elementary techniques of this chapter, we usually seek factors with integer or rational coefficients. We explicitly identify when a quadratic has no real linear factors.

### 2.2 Factoring is not solving

Factoring is an identity between expressions. Solving an equation is a search for values in a stated domain. The expression

$$
x^2-5x+6=(x-2)(x-3)
$$

is an identity for every real $x$. It does not by itself assert that $x=2$ or $x=3$. Those values are solutions only after the equation is set equal to zero:

$$
x^2-5x+6=0.
$$

This distinction will be used throughout the chapter.

## 3. Greatest common factor

The **greatest common factor (GCF)** of the terms of a polynomial is a common numerical and variable factor that can be removed from every term. Factoring out the GCF should be the first check before using more specialized patterns.

For integer coefficients, take the greatest common divisor of their absolute values. For powers of the same variable, take the smallest exponent that occurs among the nonzero terms.

Example:

$$
18x^4-24x^3=6x^3(3x-4).
$$

The numerical GCF is $6$, and the smallest power of $x$ is $x^3$.

### 3.1 Rational coefficients

For rational coefficients, a positive rational content can be extracted. One consistent convention is to take the greatest common divisor of the absolute numerators divided by the least common multiple of the positive denominators. For example,

$$
\frac{2}{3}x^3+\frac{4}{9}x^2
=\frac{2}{9}x^2(3x+2).
$$

The extracted factor is positive; signs remain in the polynomial inside the parentheses. A negative common factor may also be valid, but choosing a positive numerical content gives a consistent standard form.

### 3.2 Why the GCF step is useful

Suppose every term contains $x^2$. Removing it can reveal a simpler polynomial:

$$
5x^4-20x^2=5x^2(x^2-4).
$$

The remaining difference of squares can then be factored:

$$
5x^2(x^2-4)=5x^2(x-2)(x+2).
$$

A polynomial is not fully factored merely because its GCF has been removed; inspect the remaining factor again.

## 4. Factoring by grouping

Factoring by grouping is often useful for a polynomial with four terms. Group the terms into pairs, factor a GCF from each pair, and look for a common binomial factor.

Example:

$$
\begin{aligned}
2x^3+6x^2+5x+15
&=(2x^3+6x^2)+(5x+15)\\
&=2x^2(x+3)+5(x+3)\\
&=(x+3)(2x^2+5).
\end{aligned}
$$

The common factor is $(x+3)$. Over the reals, $2x^2+5$ has no real linear factors because it is strictly positive for every real $x$.

### 4.1 Grouping must produce the same common factor

Not every arbitrary pairing succeeds. Consider

$$
3x^2-6x+2xy-4y.
$$

Group the first two and last two terms:

$$
3x(x-2)+2y(x-2)=(x-2)(3x+2y).
$$

If a chosen grouping does not produce a common binomial, try a different grouping or return to the GCF and identities. Do not invent a common factor that is not present.

## 5. Factoring quadratic trinomials

A quadratic trinomial has the form

$$
ax^2+bx+c,
$$

where $a\ne0$. Some quadratics factor over the integers or rationals; others do not. The coefficient domain must be kept in mind.

### 5.1 Monic trinomials: $x^2+bx+c$

For a factorization

$$
x^2+bx+c=(x+m)(x+n),
$$
expansion gives

$$
x^2+(m+n)x+mn.
$$

Therefore, we need two numbers $m,n$ satisfying

$$
m+n=b,\qquad mn=c.
$$

Example:

$$
x^2+7x+12=(x+3)(x+4),
$$

because $3+4=7$ and $3\cdot4=12$.

Example with signs:

$$
x^2-x-20=(x-5)(x+4),
$$

because $-5+4=-1$ and $(-5)(4)=-20$.

### 5.2 Non-monic trinomials: the split-middle-term method

For $ax^2+bx+c$, with integer coefficients and $a\ne0$, seek integers $m,n$ such that

$$
m+n=b,\qquad mn=ac.
$$

Then split the middle term and factor by grouping. This is often called the $ac$ method.

Example:

$$
6x^2-x-2.
$$

Here $ac=6(-2)=-12$. The integers $3$ and $-4$ have product $-12$ and sum $-1$:

$$
\begin{aligned}
6x^2-x-2
&=6x^2+3x-4x-2\\
&=3x(2x+1)-2(2x+1)\\
&=(3x-2)(2x+1).
\end{aligned}
$$

The method is a search for a suitable pair; it is not a guarantee that integer factors exist. If no such pair exists, the trinomial may be irreducible over the integers, even though it still has real or complex roots.

## 6. Standard factoring identities

The following identities are the reverse forms of products developed in Chapter 08. They follow from the distributive property.

### 6.1 Difference of two squares

$$
a^2-b^2=(a-b)(a+b).
$$

The middle terms cancel when the right-hand side is expanded:

$$
(a-b)(a+b)=a^2+ab-ab-b^2=a^2-b^2.
$$

A **sum of two real squares** does not factor into real linear factors by this identity. For example, $x^2+9$ is not a difference of squares over the reals.

### 6.2 Perfect-square trinomials

$$
a^2+2ab+b^2=(a+b)^2,
$$

$$
a^2-2ab+b^2=(a-b)^2.
$$

To recognize one, check both square terms and the middle term. The middle term must be exactly twice the product of the square roots, with the appropriate sign.

Example:

$$
9x^2-30x+25=(3x-5)^2.
$$

### 6.3 Sum and difference of cubes

For any real $a,b$,

$$
a^3+b^3=(a+b)(a^2-ab+b^2),
$$

$$
a^3-b^3=(a-b)(a^2+ab+b^2).
$$

The quadratic factor in either identity is positive for all real $a,b$ except at $a=b=0$ in the corresponding zero case, because

$$
a^2\mp ab+b^2=\left(a\mp\frac{b}{2}\right)^2+\frac{3b^2}{4}\geq0.
$$

For a nonzero sum or difference of cubes, the remaining quadratic factor does not split into real linear factors.

Example:

$$
8x^3-27=(2x-3)(4x^2+6x+9).
$$

## 7. A systematic factoring strategy

Use the following order as a guide, not as a rigid algorithm:

1. **Check the GCF.** Factor it out before doing anything else.
2. **Count and inspect terms.** Four terms may suggest grouping; two terms may suggest a difference of squares or cubes.
3. **Check quadratic patterns.** Look for a perfect-square trinomial or a general trinomial factorization.
4. **Use standard identities.** Match the expression to the exact identity; verify by expansion.
5. **Repeat.** A factor produced in one step may factor further.
6. **State the coefficient domain.** A factorization may be complete over the integers but not over the reals or complex numbers.
7. **Verify.** Expand the proposed product and compare coefficients with the original polynomial.

For example,

$$
\begin{aligned}
2x^3-18x
&=2x(x^2-9)\\
&=2x(x-3)(x+3).
\end{aligned}
$$

Stopping at $2x(x^2-9)$ would leave a factor that can still be factored over the integers.

## 8. Polynomial equations and the zero-product property

The **zero-product property** states that for real numbers $u,v$,

$$
uv=0\iff u=0\text{ or }v=0.
$$

For a finite product, the product equals zero if and only if at least one factor equals zero. The statement relies on the fact that the real numbers have no zero divisors. The same property holds over the rational and complex numbers.

**Why the two-factor statement is true.** If $uv=0$ and $u=0$, the conclusion already holds. If $u\ne0$, then $u$ has a multiplicative inverse in a field, so multiplying $uv=0$ by $u^{-1}$ gives $v=0$. The converse is immediate: if either factor is zero, the product is zero. Applying this argument repeatedly proves the result for any finite product.

Thus, if

$$
(x-2)(x+5)=0,
$$
then

$$
x-2=0\quad\text{or}\quad x+5=0,
$$
so the real solution set is $\{-5,2\}$.

### 8.1 The equation must be equal to zero

The property does **not** allow us to set factors equal to zero when their product is nonzero. From

$$
(x-2)(x+5)=7,
$$
we cannot conclude $x-2=0$ or $x+5=0$. First move all terms to one side and obtain a product equal to zero, if possible.

### 8.2 Solving by factoring

A reliable procedure is:

1. Move every term to one side so the equation has the form $P(x)=0$.
2. Factor $P(x)$ as completely as the chosen coefficient domain permits.
3. Apply the zero-product property to the factors.
4. Solve each resulting factor equation.
5. Substitute each candidate into the original equation and check it.
6. State the solution set in the domain specified by the problem.

Example:

$$
\begin{aligned}
2x^2-7x+3&=0\\
(2x-1)(x-3)&=0\\
2x-1=0&\quad\text{or}\quad x-3=0\\
x=\frac12&\quad\text{or}\quad x=3.
\end{aligned}
$$

Both values satisfy the original equation, so the real solution set is $\left\{\frac12,3\right\}$.

### 8.3 Repeated factors and distinct solutions

If

$$
(x-4)^2=0,
$$
then the only distinct solution is $x=4$. The factor appears twice, but it does not create two different values in the solution set. Chapter 14 will develop multiplicity as a property of polynomial zeros.

### 8.4 When factoring does not produce real solutions

Consider

$$
x^2+4=0.
$$

Over the reals, $x^2=-4$ has no solution because every real square is nonnegative. Therefore the real solution set is empty. Over the complex numbers, the solutions are $x=2i$ and $x=-2i$; complex numbers are developed in Chapter 13.

Factoring methods in this chapter do not guarantee that every polynomial factors into real linear factors. If a quadratic factor remains and has no real roots, state that it has no real linear factorization rather than forcing one.

## 9. Common errors and checks

| Common error | Why it is wrong | Better check |
|---|---|---|
| Stopping after removing only the GCF | The remaining polynomial may still factor. | Inspect every factor again. |
| Treating $a^2+b^2$ as $(a+b)(a-b)$ | The latter expands to $a^2-b^2$. | Expand the proposed product. |
| Using the wrong sign in the cube identities | Sum and difference of cubes have different signs in the quadratic factor. | Expand the full identity. |
| Applying zero-product reasoning to a product equal to $7$ | The property applies when the product is zero. | First write the equation as $P(x)=0$. |
| Reporting repeated factors as distinct solutions | A solution set contains values, not repetitions. | List each value once. |
| Claiming every quadratic factors over the integers | Some have no integer or rational linear factors. | State the coefficient domain and check the discriminant if needed. |
| Forgetting to check a proposed solution | Transformations or restrictions may change admissibility. | Substitute into the original equation. |

## 10. Worked examples

### Example 1 — Factor out the GCF

Factor $18x^4-24x^3$:

$$
18x^4-24x^3=6x^3(3x-4).
$$

The numerical GCF is $6$, and the smallest exponent is $3$.

### Example 2 — Factor a polynomial with rational coefficients

Factor $\frac23x^3+\frac49x^2$:

$$
\frac23x^3+\frac49x^2=\frac29x^2(3x+2).
$$

The coefficient $\frac29$ is a positive rational content common to both coefficients.

### Example 3 — Factor by grouping

Factor $3x^2-6x+2xy-4y$:

$$
\begin{aligned}
3x^2-6x+2xy-4y
&=3x(x-2)+2y(x-2)\\
&=(x-2)(3x+2y).
\end{aligned}
$$

### Example 4 — Factor a four-term polynomial

Factor $2x^3+6x^2+5x+15$:

$$
\begin{aligned}
2x^3+6x^2+5x+15
&=2x^2(x+3)+5(x+3)\\
&=(x+3)(2x^2+5).
\end{aligned}
$$

Over the reals, $2x^2+5$ has no real linear factors.

### Example 5 — Factor a monic trinomial

Factor $x^2+7x+12$. The numbers $3$ and $4$ add to $7$ and multiply to $12$:

$$
x^2+7x+12=(x+3)(x+4).
$$

### Example 6 — Factor a non-monic trinomial

Factor $6x^2-x-2$. Since $ac=-12$, choose $3$ and $-4$:

$$
\begin{aligned}
6x^2-x-2
&=6x^2+3x-4x-2\\
&=3x(2x+1)-2(2x+1)\\
&=(3x-2)(2x+1).
\end{aligned}
$$

### Example 7 — Difference of two squares

$$
25x^2-49=(5x-7)(5x+7).
$$

### Example 8 — Perfect-square trinomial

$$
9x^2-30x+25=(3x-5)^2.
$$

The middle term is $-2(3x)(5)=-30x$.

### Example 9 — Sum of cubes

$$
x^3+64=(x+4)(x^2-4x+16).
$$

### Example 10 — A multi-step factorization

Factor $2x^3-18x$ completely over the integers:

$$
\begin{aligned}
2x^3-18x&=2x(x^2-9)\\
&=2x(x-3)(x+3).
\end{aligned}
$$

### Example 11 — Solve a quadratic equation by factoring

$$
\begin{aligned}
x^2-5x+6&=0\\
(x-2)(x-3)&=0\\
x&=2\quad\text{or}\quad x=3.
\end{aligned}
$$

The real solution set is $\{2,3\}$.

### Example 12 — Solve a non-monic quadratic equation

$$
\begin{aligned}
3x^2+x-2&=0\\
(3x-2)(x+1)&=0\\
x&=\frac23\quad\text{or}\quad x=-1.
\end{aligned}
$$

### Example 13 — Solve a cubic equation with a GCF

$$
\begin{aligned}
x^3-9x&=0\\
x(x^2-9)&=0\\
x(x-3)(x+3)&=0.
\end{aligned}
$$

Therefore $x=0$, $x=3$, or $x=-3$. The real solution set is $\{-3,0,3\}$.

### Example 14 — A repeated factor gives one distinct solution

$$
\begin{aligned}
4x^2-12x+9&=0\\
(2x-3)^2&=0\\
2x-3&=0\\
x&=\frac32.
\end{aligned}
$$

There is one distinct real solution, $\frac32$.

### Example 15 — No real solutions

Solve $2x^2+1=0$ over $\mathbb R$. Since $2x^2\geq0$ for real $x$, the left-hand side is at least $1$. It cannot equal zero. The real solution set is $\varnothing$.

### Example 16 — Why the zero-product property cannot be misused

The equation $(x-1)(x+2)=6$ does not imply $x=1$ or $x=-2$. Expanding and moving all terms to one side gives

$$
x^2+x-8=0.
$$

This quadratic has discriminant $1+32=33$, so its real solutions are $\frac{-1\pm\sqrt{33}}{2}$, not $1$ or $-2$.

## 11. Exact factorization checks with Python

Symbolic factoring in full generality is a substantial topic. The small chapter implementation the chapter implementation does not claim to factor every polynomial. It performs two limited, transparent tasks:

1. Extracts the positive rational content and the smallest common power of $x$ from a sparse polynomial representation.
2. Verifies a proposed product of factors by multiplying the factors with the exact polynomial routines from the chapter implementation and comparing normalized coefficients.

The representation is the same sparse format used in Chapter 08: a dictionary maps an exponent to an integer or `Fraction` coefficient. Floating-point coefficients are rejected so exact checks remain exact.

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

# Bind imported names from prerequisite implementations.
multiply = multiply
normalize = normalize

# --- Inlined implementation: factoring_core ---
"""Exact factoring utilities for Chapter 09.

The module intentionally does not attempt general symbolic factorization.
It extracts the positive rational content and the common variable power,
and verifies a proposed product by exact coefficient multiplication.
Polynomials use the sparse representation {exponent: coefficient} from
the corresponding chapter implementation. Coefficients must be integers or fractions.Fraction.
"""


from fractions import Fraction
from math import gcd, lcm
from typing import Iterable, Mapping



Polynomial = dict[int, Fraction]


def rational_content(poly: Mapping[int, object]) -> Fraction:
    """Return the positive rational content of a nonzero polynomial.

    For rational coefficients this is gcd(abs(numerators)) divided by
    lcm(positive denominators). The zero polynomial has no content under
    this convention and raises ValueError.
    """
    normalized = normalize(poly)
    if not normalized:
        raise ValueError("the zero polynomial has no rational content")

    numerator_gcd = 0
    denominator_lcm = 1
    for coefficient in normalized.values():
        numerator_gcd = gcd(numerator_gcd, abs(coefficient.numerator))
        denominator_lcm = lcm(denominator_lcm, coefficient.denominator)
    return Fraction(numerator_gcd, denominator_lcm)


def factor_out_gcf(poly: Mapping[int, object]) -> tuple[Fraction, int, Polynomial]:
    """Extract positive rational content and the smallest common power.

    Returns (content, common_power, remaining_polynomial), so that
    poly(x) = content * x**common_power * remaining_polynomial(x).
    The inner polynomial keeps the original signs.
    """
    normalized = normalize(poly)
    if not normalized:
        raise ValueError("cannot extract a GCF from the zero polynomial")

    common_power = min(normalized)
    content = rational_content(normalized)
    remaining = {
        exponent - common_power: coefficient / content
        for exponent, coefficient in normalized.items()
    }
    return content, common_power, normalize(remaining)


def verify_factorization(
    original: Mapping[int, object],
    factors: Iterable[Mapping[int, object]],
) -> bool:
    """Return whether the exact product of factors equals original.

    The empty factor list represents the multiplicative identity 1.
    Invalid polynomial representations raise the same TypeError/ValueError
    exceptions as polynomial_core.normalize.
    """
    product: Polynomial = {0: Fraction(1)}
    for factor in factors:
        product = multiply(product, factor)
    return normalize(original) == normalize(product)

# --- Chapter example ---
factor_out_gcf = factor_out_gcf
verify_factorization = verify_factorization

from fractions import Fraction


p = {3: -6, 2: 9}  # -6*x^3 + 9*x^2
content, common_power, remaining = factor_out_gcf(p)
print(content, common_power, remaining)
# 3 2 {0: Fraction(3, 1), 1: Fraction(-2, 1)}

# Verify 3*x^2 * (3 - 2*x) = -6*x^3 + 9*x^2.
assert verify_factorization(p, [
    {2: Fraction(3)},
    {1: Fraction(-2), 0: Fraction(3)},
])

# A proposed factorization that expands to a different polynomial is rejected.
assert not verify_factorization(p, [
    {2: 3},
    {1: -2, 0: 4},
])

rational_p = {3: Fraction(2, 3), 2: Fraction(4, 9)}
r_content, r_power, r_remaining = factor_out_gcf(rational_p)
assert (r_content, r_power) == (Fraction(2, 9), 2)
assert r_remaining == {0: Fraction(2), 1: Fraction(3)}
```

This tool is a verification aid, not an automatic general-purpose factorizer. A proof that a proposed identity is true still comes from valid algebraic reasoning; exact coefficient comparison simply checks the computation reliably.

## 12. Exercises

### A. Greatest common factor

1. Factor $15x^4-20x^3$.
2. Factor $-8x^3+12x^2$ using a positive numerical GCF.
3. Factor $14x^5+21x^3$ completely.
4. Factor $\frac23x^3+\frac49x^2$ using a positive rational content.

### B. Grouping and trinomials

5. Factor $ax+ay+bx+by$ by grouping.
6. Factor $3x^2-6x+2xy-4y$.
7. Factor $2x^3+6x^2+5x+15$.
8. Factor $x^2+9x+20$.
9. Factor $x^2-2x-24$.
10. Factor $2x^2+9x+10$.
11. Factor $6x^2-x-2$.
12. Factor $4x^2+4x-15$.
13. Factor $3x^2-12x+12$ completely.

### C. Standard identities

14. Factor $x^2-49$.
15. Factor $25x^2+30x+9$.
16. Factor $8x^3-27$.
17. Factor $x^3+64$.
18. Explain why $x^2+16$ does not factor into real linear factors.

### D. Polynomial equations

19. Solve $x^2-5x+6=0$ over $\mathbb R$.
20. Solve $3x^2+x-2=0$ over $\mathbb R$.
21. Solve $x^3-9x=0$ over $\mathbb R$.
22. Solve $x^2-10x+25=0$. State the number of distinct solutions.
23. Solve $2x^2+1=0$ over $\mathbb R$.
24. Solve $x(x-3)(x+4)=0$ over $\mathbb R$.
25. Explain why $(x-1)(x+2)=7$ does not imply $x=1$ or $x=-2$.
26. Factor $2x^3+5x^2-18x-45$ completely over the integers.

## 13. Selected answers

1. $5x^3(3x-4)$.
2. $4x^2(3-2x)$.
3. $7x^3(2x^2+3)$.
4. $\frac29x^2(3x+2)$.
5. $(a+b)(x+y)$.
6. $(x-2)(3x+2y)$.
7. $(x+3)(2x^2+5)$.
8. $(x+4)(x+5)$.
9. $(x-6)(x+4)$.
10. $(2x+5)(x+2)$.
11. $(3x-2)(2x+1)$.
12. $(2x+5)(2x-3)$.
13. $3(x-2)^2$.
14. $(x-7)(x+7)$.
15. $(5x+3)^2$.
16. $(2x-3)(4x^2+6x+9)$.
17. $(x+4)(x^2-4x+16)$.
18. $x^2+16>0$ for all real $x$, so it has no real zero and no real linear factorization.
19. $(x-2)(x-3)=0$, so the solution set is $\{2,3\}$.
20. $\left\{-1,\frac23\right\}$.
21. $\{-3,0,3\}$.
22. One distinct solution, $x=5$.
23. $\varnothing$ over $\mathbb R$.
24. $\{-4,0,3\}$.
25. The zero-product property applies only when the product equals zero. Here the product equals $7$; expand to $x^2+x-9=0$, whose real solutions are $\frac{-1\pm\sqrt{37}}{2}$.
26. $(2x+5)(x-3)(x+3)$.

## 14. Chapter summary

- Factoring expresses a polynomial as a product; it reverses expansion.
- “Completely factored” depends on the coefficient domain.
- Extract the GCF before applying more specialized patterns.
- Grouping works when the chosen pairs produce a common binomial factor.
- Quadratic trinomials can be factored by finding numbers with a required sum and product; the split-middle-term method extends this idea to non-monic trinomials.
- Difference of squares, perfect-square trinomials, and sum/difference of cubes are identities derived from multiplication.
- The zero-product property applies to a product equal to zero, not to an arbitrary nonzero product.
- After factoring an equation in the form $P(x)=0$, set each factor equal to zero and solve within the specified domain.
- Repeated factors do not create repeated distinct values in a solution set.
- Verify proposed factorizations by expansion or exact coefficient comparison.

## 15. Next chapter

**Chapter 10 — Rational Expressions and Equations** studies expressions with polynomial denominators, domain restrictions, simplifying rational expressions, operations with rational expressions, rational equations, and extraneous solutions. Chapter 09 has used polynomial factorization as a tool; Chapter 10 will use it to identify and preserve denominator restrictions.

## References

- Math-Atlas Algebra, Chapter 03 — Linear Equations and Literal Equations.
- Math-Atlas Algebra, Chapter 07 — Exponents and Scientific Notation.
- Math-Atlas Algebra, Chapter 08 — Polynomials and Polynomial Operations.
- Math-Atlas Algebra Conventions — polynomial coefficient domains and exact arithmetic.
- OpenStax, *Algebra and Trigonometry 2e*, sections on factoring polynomials and solving polynomial equations.

**Next chapter:** Chapter 10 — Rational Expressions and Equations.
