# Algebra 10 — Rational Expressions and Equations

## 1. Introduction

A **rational expression** is a quotient of two polynomials. Rational expressions extend ordinary fractions from numbers to algebraic quantities, but they introduce an essential issue: a denominator must not be zero. Every simplification and every equation-solving step must preserve that restriction.

For example,

$$
\frac{x^2-1}{x-1}=\frac{(x-1)(x+1)}{x-1}=x+1
$$

is valid only when $x\ne1$. The simplified formula is easier to use, but it does not restore the excluded input $x=1$ to the domain of the original expression.

This chapter develops domain restrictions, simplification, arithmetic with rational expressions, complex fractions, and rational equations. Its central habit is simple: **record restrictions before simplifying, preserve them through every operation, and check every candidate in the original equation.**

### Learning objectives

By the end of this chapter, a learner should be able to:

- Define the domain of a rational expression from its original denominator.
- Distinguish cancellation of a common factor from cancellation of a restriction.
- Simplify rational expressions by factoring numerator and denominator.
- Multiply, divide, add, and subtract rational expressions using valid common factors and least common denominators.
- Simplify complex fractions while retaining all original restrictions.
- Solve rational equations by multiplying by a least common denominator (LCD).
- Explain why clearing denominators can produce candidates that are not solutions of the original equation.
- Classify rational equations as having no solution, finitely many solutions, or an identity on their admissible domain.
- Use exact polynomial and rational arithmetic in Python without silently replacing exact values by floating-point approximations.

## 2. Rational expressions and their domains

A **rational expression in $x$** has the form

$$
R(x)=\frac{P(x)}{Q(x)},
$$

where $P$ and $Q$ are polynomials with real coefficients and $Q$ is not the zero polynomial. Its natural real domain is

$$
D_R=\lbrace x\in\mathbb R:Q(x)\ne0 \rbrace.
$$

The restriction comes from the denominator of the expression as originally given. A numerator may be zero; a denominator may not.

### Example 1 — Find a domain

Find the real domain of

$$
R(x)=\frac{3x+1}{x^2-5x+6}.
$$

Factor the denominator:

$$
x^2-5x+6=(x-2)(x-3).
$$

The denominator is zero at $x=2$ and $x=3$. Therefore,

$$
D_R=\mathbb R\setminus\lbrace 2,3 \rbrace.
$$

### Example 2 — A numerator zero is allowed

For

$$
S(x)=\frac{x-4}{x+2},
$$

only $x=-2$ is excluded. The value $x=4$ is allowed and makes the expression equal to zero:

$$
D_S=\mathbb R\setminus\lbrace -2 \rbrace,\qquad S(4)=0.
$$

### 2.1 Domain restrictions survive simplification

Suppose

$$
R(x)=\frac{(x-a)A(x)}{(x-a)B(x)}.
$$

For inputs where the original expression is defined, cancellation gives

$$
R(x)=\frac{A(x)}{B(x)},
$$

but the original restrictions still apply: $x\ne a$ and $B(x)\ne0$. Cancellation removes a common factor from the displayed formula; it does **not** change the original domain.

This distinction is sometimes described by saying that the simplified formula may fill a removable hole in a graph, whereas the original rational expression remains undefined at that input. The graph of the original expression does not contain the missing point.

### Example 3 — Simplify and preserve the hole

Simplify

$$
\frac{x^2-9}{x^2-3x}.
$$

First record the original denominator restriction:

$$
x^2-3x=x(x-3)\ne0\quad\Longrightarrow\quad x\ne0,\;x\ne3.
$$

Now factor and cancel:

$$
\frac{(x-3)(x+3)}{x(x-3)}=\frac{x+3}{x},\qquad x\ne0,3.
$$

The simplified formula alone would be defined at $x=3$, but the original expression is not. The correct result is the simplified expression together with both restrictions.

## 3. Equality of rational expressions

Let $P,Q,S,T$ be polynomials. At any input where both denominators are nonzero,

$$
\frac{P(x)}{Q(x)}=\frac{S(x)}{T(x)}
\quad\Longleftrightarrow\quad
P(x)T(x)=S(x)Q(x).
$$

The cross-multiplication equivalence depends on $Q(x)\ne0$ and $T(x)\ne0$. It does not authorize values excluded by either original denominator.

For example,

$$
\frac{x^2-1}{x-1}=x+1
$$

holds for every $x\in\mathbb R\setminus\lbrace 1 \rbrace$, not for every real number as an equality of the original partially defined expressions. The polynomial identity

$$
x^2-1=(x-1)(x+1)
$$

is valid for all real $x$, but the quotient still has a denominator restriction.

## 4. Simplifying rational expressions

A reliable simplification procedure is:

1. Factor the numerator and denominator completely as far as the chosen coefficient domain allows.
2. Record every real value that makes the **original denominator** zero.
3. Cancel only common nonzero factors, not terms joined by addition or subtraction.
4. State the simplified expression together with the original restrictions.
5. When useful, verify the resulting identity by cross multiplication on the admissible domain.

### Example 4 — Factoring before cancelling

Simplify

$$
\frac{x^2-16}{x^2+x-20}.
$$

The original denominator factors as $(x+5)(x-4)$, so $x\ne-5,4$. Then

$$
\frac{(x-4)(x+4)}{(x+5)(x-4)}
=\frac{x+4}{x+5},\qquad x\ne-5,4.
$$

### 4.1 What may be cancelled?

A common **factor** may be cancelled when it is nonzero on the original domain. A term may not be cancelled across addition or subtraction.

Incorrect:

$$
\frac{x+3}{x}\ne\frac{3}{1}.
$$

The numerator is a sum, not a product with a common factor $x$. In general,

$$
\frac{A+B}{A}\ne\frac{B}{1}.
$$

A numerical check such as $x=2$ already shows that $(x+3)/x$ is not $3$.

### Example 5 — A correct cancellation

$$
\frac{x^2-4}{x^2+3x+2}
=\frac{(x-2)(x+2)}{(x+1)(x+2)}
=\frac{x-2}{x+1},
$$

where the original denominator requires $x\ne-1,-2$. Both restrictions remain after cancellation.

## 5. Multiplication of rational expressions

To multiply rational expressions, factor first when possible, multiply numerators and denominators, and then cancel common factors. Keep every restriction inherited from the original expressions.

$$
\frac{A}{B}\cdot\frac{C}{D}=\frac{AC}{BD},
$$

provided $B\ne0$ and $D\ne0$ on the chosen domain.

### Example 6 — Multiply and retain all restrictions

Simplify

$$
\frac{x^2-1}{x^2-4}\cdot\frac{x-2}{x+1}.
$$

The original denominators require $x\ne-2,2,-1$. Factor:

$$
\begin{aligned}
\frac{(x-1)(x+1)}{(x-2)(x+2)}\cdot\frac{x-2}{x+1}
&=\frac{x-1}{x+2}.
\end{aligned}
$$

The result is

$$
\frac{x-1}{x+2},\qquad x\ne-2,2,-1.
$$

The restrictions $x\ne2$ and $x\ne-1$ remain because they came from denominators before cancellation.

## 6. Division of rational expressions

To divide by a rational expression, multiply by its reciprocal. In addition to the original denominator restrictions, the divisor itself must not equal zero.

$$
\frac{A/B}{C/D}=\frac{A}{B}\cdot\frac{D}{C}
=\frac{AD}{BC},
$$

where $B\ne0$, $D\ne0$, and $C\ne0$. The condition $C\ne0$ is essential: division by zero is undefined.

### Example 7 — Divide and identify the extra restriction

Simplify

$$
\frac{x^2-9}{x^2-4}\div\frac{x-3}{x+2}.
$$

The first denominator requires $x\ne-2,2$. The divisor is defined only for $x\ne-2$, and it must also be nonzero, so $x\ne3$. Thus the original expression requires $x\ne-2,2,3$.

Now multiply by the reciprocal:

$$
\begin{aligned}
\frac{(x-3)(x+3)}{(x-2)(x+2)}\cdot\frac{x+2}{x-3}
&=\frac{x+3}{x-2}.
\end{aligned}
$$

The simplified result is

$$
\frac{x+3}{x-2},\qquad x\ne-2,2,3.
$$

The restriction $x\ne3$ comes from dividing by the original expression $(x-3)/(x+2)$, even though the factor $x-3$ cancels.

## 7. Addition and subtraction

To add or subtract rational expressions, use a common denominator. The **least common denominator (LCD)** is a least common multiple of the denominator factors, with each distinct factor included to its highest required power.

For rational expressions with denominators $B$ and $D$,

$$
\frac{A}{B}+\frac{C}{D}=\frac{AD+BC}{BD}
$$

is a valid common-denominator construction when $B$ and $D$ are nonzero. A factored LCD is often shorter and makes restrictions easier to see.

### Example 8 — Addition with a factored LCD

Simplify

$$
\frac{1}{x-1}+\frac{3}{x+2}.
$$

The original restrictions are $x\ne1,-2$. The LCD is $(x-1)(x+2)$:

$$
\begin{aligned}
\frac{1}{x-1}+\frac{3}{x+2}
&=\frac{x+2+3(x-1)}{(x-1)(x+2)}\\
&=\frac{4x-1}{(x-1)(x+2)},\qquad x\ne1,-2.
\end{aligned}
$$

### Example 9 — Subtraction

Simplify

$$
\frac{2}{x}-\frac{1}{x+1}.
$$

The restrictions are $x\ne0,-1$. Then

$$
\begin{aligned}
\frac{2}{x}-\frac{1}{x+1}
&=\frac{2(x+1)-x}{x(x+1)}\\
&=\frac{x+2}{x(x+1)},\qquad x\ne0,-1.
\end{aligned}
$$

Do not subtract numerators while leaving the denominator unchanged. The denominator must be made common first.

## 8. Complex fractions

A **complex fraction** is a fraction whose numerator, denominator, or both contain fractions. Simplify it by multiplying its numerator and denominator by a common denominator for the smaller fractions, while retaining all restrictions from the original form.

### Example 10 — Simplify a complex fraction

Simplify

$$
\frac{\frac{1}{x}+1}{\frac{1}{x}-1}.
$$

The original inner fractions require $x\ne0$. The denominator of the large fraction must also be nonzero:

$$
\frac{1}{x}-1\ne0\quad\Longrightarrow\quad x\ne1.
$$

Multiply the numerator and denominator of the large fraction by $x$:

$$
\frac{\frac{1}{x}+1}{\frac{1}{x}-1}
=\frac{1+x}{1-x},\qquad x\ne0,1.
$$

Both restrictions remain, even though the simplified formula is defined at $x=0$.

## 9. Rational equations: a safe method

A **rational equation** contains one or more rational expressions and asks for values in a stated domain that make the equation true.

Use this procedure:

1. **State the original domain restrictions.** Set every original denominator unequal to zero. If dividing by a rational expression, also require that divisor to be nonzero.
2. **Find the LCD.** Factor denominators so the LCD is visible.
3. **Multiply every term on both sides by the LCD.** This is valid on the original domain because the LCD is nonzero there.
4. **Solve the resulting equation.** It is often polynomial or linear.
5. **Check every candidate in the original equation.** Reject any candidate that violates an original restriction or fails the original equation.
6. **State the final solution set in the original domain.**

Clearing denominators creates an equation that is equivalent to the original equation only on the original domain. If the cleared equation is considered over all real numbers, it may contain candidates that were excluded from the start. Such rejected candidates are often called **extraneous solutions** (more precisely, extraneous candidates): they solve a transformed equation but do not solve the original equation in its domain.

### Example 11 — A rational equation with valid solutions

Solve over the real numbers:

$$
\frac{2}{x}+\frac{3}{x-1}=1.
$$

The original restrictions are $x\ne0$ and $x\ne1$. The LCD is $x(x-1)$. Multiply every term by it:

$$
\begin{aligned}
2(x-1)+3x&=x(x-1)\\
5x-2&=x^2-x\\
x^2-6x+2&=0.
\end{aligned}
$$

The quadratic formula gives

$$
x=\frac{6\pm\sqrt{36-8}}{2}=3\pm\sqrt7.
$$

Neither value is $0$ or $1$, so both satisfy the original domain restrictions. The solution set is

$$
\lbrace 3-\sqrt7,\;3+\sqrt7 \rbrace.
$$

### Example 12 — A candidate excluded by the original domain

Solve

$$
\frac{x+1}{x-1}=\frac{2}{x-1}.
$$

The original denominator requires $x\ne1$. Multiplying by $x-1$ on this domain gives

$$
x+1=2\quad\Longrightarrow\quad x=1.
$$

But $x=1$ is excluded from the original equation. Therefore the equation has **no solution**:

$$
S=\varnothing.
$$

The cleared equation produced a candidate, not an admissible solution.

### Example 13 — An identity on a restricted domain

Solve

$$
\frac{x^2-1}{x-1}=x+1.
$$

The original domain is $x\ne1$. On this domain,

$$
\frac{(x-1)(x+1)}{x-1}=x+1
$$

is true for every admissible $x$. The solution set is therefore

$$
S=\mathbb R\setminus\lbrace 1 \rbrace.
$$

This is an identity on the original domain, not a statement that the original quotient is defined at $x=1$.

### Example 14 — A contradiction

Solve

$$
\frac{1}{x-1}=\frac{1}{x-1}+1.
$$

The domain requires $x\ne1$. Subtracting the common rational expression from both sides gives $0=1$, which is impossible. Hence $S=\varnothing$.

## 10. Applications and modelling

Rational expressions naturally occur when a quantity is divided by another quantity, such as rate, density, unit cost, and average speed. A model must state which inputs are meaningful and where denominators are nonzero.

### Example 15 — Combined work rates

Worker A completes a job in $6$ hours, and worker B completes the same job in $3$ hours. Their constant rates are $1/6$ and $1/3$ job per hour. Working together, their rate is

$$
\frac16+\frac13=\frac12
$$

job per hour. The time for one job is the reciprocal rate:

$$
T=\frac{1}{1/2}=2\text{ hours}.
$$

The model assumes both workers maintain their stated constant rates and can work simultaneously without interference. A reciprocal is taken only after the combined rate is known to be nonzero.

### Example 16 — Average speed is not the arithmetic mean of speeds

A vehicle travels equal distances at speeds $v_1>0$ and $v_2>0$. Let each distance be $d$. The total distance is $2d$, while the total time is

$$
\frac{d}{v_1}+\frac{d}{v_2}.
$$

Therefore the average speed is

$$
v_{\mathrm{avg}}=\frac{2d}{d/v_1+d/v_2}
=\frac{2v_1v_2}{v_1+v_2}.
$$

This is the harmonic mean of the two speeds, not generally their arithmetic mean. The equality-distance assumption is essential; for unequal distances the model changes.

## 11. Exact rational-expression checks with Python

The self-contained Python implementation in the example below uses the sparse polynomial representation from Chapter 08. It performs exact polynomial division over rational coefficients, computes a monic polynomial GCD, simplifies rational expressions, and performs rational operations while retaining the nonzero conditions inherited from original denominators.

A rational expression is represented by:

- a normalized numerator polynomial;
- a normalized denominator polynomial;
- a tuple of polynomial conditions that must remain nonzero.

The conditions are deliberately retained after cancellation. This prevents a simplified formula from silently filling a hole in the original domain. The module is a teaching aid for exact univariate rational expressions; it is not a general computer algebra system and does not solve arbitrary rational equations symbolically.

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
poly_add = add
poly_evaluate = evaluate
leading_coefficient = leading_coefficient
poly_multiply = multiply
normalize = normalize
poly_subtract = subtract

# --- Inlined implementation: rational_core ---
"""Exact univariate rational-expression helpers for Chapter 10.

Polynomials use the sparse representation {exponent: coefficient} from
the corresponding chapter implementation. Coefficients and evaluation inputs must be integers or
fractions.Fraction values; floats are rejected to preserve exactness.

A RationalExpression stores its simplified numerator and denominator AND all
polynomial nonzero conditions inherited from the original denominators (and,
for division, the original divisor's numerator). This preserves holes after
cancellation. It is a small teaching aid, not a general computer algebra
system or a symbolic equation solver.
"""

from dataclasses import dataclass
from fractions import Fraction
from typing import Mapping

Polynomial = dict[int, Fraction]

def _scale(poly: Mapping[int, object], scalar: Fraction) -> Polynomial:
    p = normalize(poly)
    return normalize({power: coefficient * scalar for power, coefficient in p.items()})

def _divmod_poly(dividend: Mapping[int, object], divisor: Mapping[int, object]) -> tuple[Polynomial, Polynomial]:
    """Polynomial long division over Q[x]."""
    remainder = normalize(dividend)
    divisor_n = normalize(divisor)
    if not divisor_n:
        raise ZeroDivisionError("cannot divide a polynomial by the zero polynomial")
    quotient: Polynomial = {}
    divisor_degree = max(divisor_n)
    divisor_lc = divisor_n[divisor_degree]

    while remainder and max(remainder) >= divisor_degree:
        power = max(remainder) - divisor_degree
        coefficient = remainder[max(remainder)] / divisor_lc
        term = {power: coefficient}
        quotient = poly_add(quotient, term)
        remainder = poly_subtract(remainder, poly_multiply(term, divisor_n))
    return normalize(quotient), normalize(remainder)

def _exact_divide(dividend: Mapping[int, object], divisor: Mapping[int, object]) -> Polynomial:
    quotient, remainder = _divmod_poly(dividend, divisor)
    if remainder:
        raise ArithmeticError("polynomial division was not exact")
    return quotient

def polynomial_gcd(left: Mapping[int, object], right: Mapping[int, object]) -> Polynomial:
    """Return the monic greatest common divisor over Q[x]."""
    a = normalize(left)
    b = normalize(right)
    while b:
        _, remainder = _divmod_poly(a, b)
        a, b = b, remainder
    if not a:
        return {}
    return _scale(a, Fraction(1, 1) / leading_coefficient(a))

def _normalize_conditions(conditions: tuple[Mapping[int, object], ...]) -> tuple[Polynomial, ...]:
    normalized: list[Polynomial] = []
    for condition in conditions:
        p = normalize(condition)
        if not p:
            raise ValueError("a nonzero condition cannot be the zero polynomial")
        if p not in normalized:
            normalized.append(p)
    return tuple(normalized)

@dataclass(frozen=True)
class RationalExpression:
    """A simplified rational formula with preserved nonzero conditions."""
    numerator: Polynomial
    denominator: Polynomial
    nonzero_conditions: tuple[Polynomial, ...]

def _from_parts(
    numerator: Mapping[int, object],
    denominator: Mapping[int, object],
    conditions: tuple[Mapping[int, object], ...],
) -> RationalExpression:
    num = normalize(numerator)
    den = normalize(denominator)
    if not den:
        raise ZeroDivisionError("a rational expression needs a nonzero denominator polynomial")

    # Every denominator introduced by an operation must remain nonzero.
    all_conditions = _normalize_conditions(conditions + (den,))

    common = polynomial_gcd(num, den)
    if common:
        num = _exact_divide(num, common)
        den = _exact_divide(den, common)

    # Use a monic denominator for a stable canonical representation.
    denominator_lc = leading_coefficient(den)
    scale = Fraction(1, 1) / denominator_lc
    num = _scale(num, scale)
    den = _scale(den, scale)

    return RationalExpression(num, den, all_conditions)

def make_rational_expression(
    numerator: Mapping[int, object], denominator: Mapping[int, object]
) -> RationalExpression:
    """Build and simplify P(x)/Q(x), retaining Q(x) != 0."""
    den = normalize(denominator)
    if not den:
        raise ZeroDivisionError("the original denominator cannot be the zero polynomial")
    return _from_parts(numerator, den, (den,))

def add(left: RationalExpression, right: RationalExpression) -> RationalExpression:
    num = poly_add(
        poly_multiply(left.numerator, right.denominator),
        poly_multiply(right.numerator, left.denominator),
    )
    den = poly_multiply(left.denominator, right.denominator)
    return _from_parts(num, den, left.nonzero_conditions + right.nonzero_conditions)

def subtract(left: RationalExpression, right: RationalExpression) -> RationalExpression:
    num = poly_subtract(
        poly_multiply(left.numerator, right.denominator),
        poly_multiply(right.numerator, left.denominator),
    )
    den = poly_multiply(left.denominator, right.denominator)
    return _from_parts(num, den, left.nonzero_conditions + right.nonzero_conditions)

def multiply(left: RationalExpression, right: RationalExpression) -> RationalExpression:
    num = poly_multiply(left.numerator, right.numerator)
    den = poly_multiply(left.denominator, right.denominator)
    return _from_parts(num, den, left.nonzero_conditions + right.nonzero_conditions)

def divide(left: RationalExpression, right: RationalExpression) -> RationalExpression:
    """Divide by right, requiring right to be defined and nonzero."""
    if not right.numerator:
        raise ZeroDivisionError("cannot divide by the zero rational expression")
    num = poly_multiply(left.numerator, right.denominator)
    den = poly_multiply(left.denominator, right.numerator)
    conditions = left.nonzero_conditions + right.nonzero_conditions + (right.numerator,)
    return _from_parts(num, den, conditions)

def is_defined(expression: RationalExpression, value: object) -> bool:
    """Return whether an exact integer/Fraction input meets all restrictions."""
    if isinstance(value, bool) or not isinstance(value, (int, Fraction)):
        raise TypeError("evaluation input must be an integer or Fraction")
    x = Fraction(value)
    return all(poly_evaluate(condition, x) != 0 for condition in expression.nonzero_conditions)

def evaluate(expression: RationalExpression, value: object) -> Fraction:
    """Evaluate exactly, raising ValueError outside the original domain."""
    if isinstance(value, bool) or not isinstance(value, (int, Fraction)):
        raise TypeError("evaluation input must be an integer or Fraction")
    x = Fraction(value)
    if not is_defined(expression, x):
        raise ValueError("the input is excluded by an original denominator or divisor")
    denominator_value = poly_evaluate(expression.denominator, x)
    if denominator_value == 0:
        # Defensive check: the retained conditions should already imply this.
        raise ValueError("the simplified denominator is zero at this input")
    return poly_evaluate(expression.numerator, x) / denominator_value

# --- Chapter example ---
make_rational_expression = make_rational_expression
add = add
divide = divide
evaluate = evaluate
is_defined = is_defined

from fractions import Fraction

# (x^2 - 1)/(x - 1) simplifies to x + 1, but x = 1 remains excluded.
expression = make_rational_expression(
    {2: 1, 0: -1},  # x^2 - 1
    {1: 1, 0: -1},  # x - 1
)
assert expression.numerator == {1: Fraction(1), 0: Fraction(1)}
assert expression.denominator == {0: Fraction(1)}
assert evaluate(expression, Fraction(2)) == Fraction(3)
assert is_defined(expression, Fraction(1)) is False

# Add 1/(x - 1) and 1/(x + 1). Restrictions x != -1, 1 are preserved.
left = make_rational_expression({0: 1}, {1: 1, 0: -1})
right = make_rational_expression({0: 1}, {1: 1, 0: 1})
sum_expression = add(left, right)
assert evaluate(sum_expression, Fraction(2)) == Fraction(4, 3)
assert not is_defined(sum_expression, Fraction(1))
assert not is_defined(sum_expression, Fraction(-1))

# Division requires the divisor to be nonzero as well as defined.
quotient = divide(left, right)
assert is_defined(quotient, Fraction(2))

# A rational expression cannot be divided by the zero expression.
zero = make_rational_expression({}, {0: 1})
try:
    divide(left, zero)
except ZeroDivisionError:
    pass
else:
    raise AssertionError("division by the zero rational expression must fail")
```

The module accepts only integer and `fractions.Fraction` coefficients and integer or `Fraction` evaluation inputs. It rejects floating-point coefficients rather than silently claiming exact arithmetic. For a decimal that must be exact, construct it from a string, such as `Fraction("0.1")`.

## 12. Common errors and checks

- **Cancelling terms instead of factors.** Factor the numerator and denominator first; cancellation applies only to common factors.
- **Forgetting original restrictions.** A cancelled factor still records excluded inputs from the original denominator.
- **Dividing by a rational expression that may be zero.** Require its numerator to be nonzero on the domain where division is performed.
- **Adding numerators without an LCD.** Rewrite both fractions over a common denominator first.
- **Multiplying only some terms by the LCD.** When clearing denominators in an equation, multiply every term on both sides.
- **Treating every cleared candidate as a solution.** Check each candidate in the original equation and against every original restriction.
- **Using a formula outside its domain.** State all nonzero denominator conditions before using a reciprocal or cancelling a factor.
- **Confusing an identity with an unrestricted equality.** An equation may be true for every admissible input while still having excluded values.

## 13. Exercises

### A. Domains and simplification

1. Find the real domain of $\dfrac{3x-2}{x^2-7x+12}$.
2. Simplify $\dfrac{x^2-16}{x^2+x-20}$ and state all original restrictions.
3. Simplify $\dfrac{x^2-4}{x^2+3x+2}$ and state all original restrictions.
4. Explain why $\dfrac{x^2-1}{x-1}$ is not defined at $x=1$, even though its simplified formula is $x+1$.
5. Identify the error in the claim $\dfrac{x+5}{x}=5$.

### B. Operations

6. Simplify $\dfrac{x^2-1}{x^2-4}\cdot\dfrac{x-2}{x+1}$ with all restrictions.
7. Simplify $\dfrac{x^2-9}{x^2-4}\div\dfrac{x-3}{x+2}$ with all restrictions.
8. Simplify $\dfrac{1}{x-1}+\dfrac{3}{x+2}$.
9. Simplify $\dfrac{2}{x}-\dfrac{1}{x+1}$.
10. Simplify $\dfrac{\frac1x+1}{\frac1x-1}$ and state the complete original domain.

### C. Rational equations

11. Solve $\dfrac{2}{x}+\dfrac{3}{x-1}=1$ over $\mathbb R$.
12. Solve $\dfrac{x+1}{x-1}=\dfrac{2}{x-1}$ over $\mathbb R$ and explain why checking is essential.
13. Solve $\dfrac{x^2-1}{x-1}=x+1$ over its original domain.
14. Solve $\dfrac{1}{x-1}=\dfrac{1}{x-1}+1$ over its original domain.
15. Solve $\dfrac{1}{x}+\dfrac{1}{x+1}=1$ over $\mathbb R$.

### D. Reasoning and applications

16. Prove that $\dfrac{A(x)C(x)}{B(x)C(x)}=\dfrac{A(x)}{B(x)}$ whenever $B(x)\ne0$ and $C(x)\ne0$.
17. Explain why the divisor in $\dfrac{P(x)}{Q(x)}\div\dfrac{R(x)}{S(x)}$ requires both $S(x)\ne0$ and $R(x)\ne0$.
18. Two workers complete a job in $8$ hours and $4$ hours, respectively. Under a constant-rate model, how long do they take together?
19. A vehicle covers equal distances at $40$ km/h and $60$ km/h. Find its average speed for the whole journey and explain why it is not $50$ km/h.
20. Give an example of two simplified rational formulas that agree wherever both original expressions are defined but have different original domains.

## 14. Selected answers

1. $\mathbb R\setminus\lbrace 3,4 \rbrace$, since $x^2-7x+12=(x-3)(x-4)$.
2. $\dfrac{x+4}{x+5}$, with $x\ne4,-5$.
3. $\dfrac{x-2}{x+1}$, with $x\ne-2,-1$.
4. The original denominator is zero at $x=1$; cancellation does not change the original domain.
5. The numerator is a sum, not a product with a cancellable factor $x$; for instance, at $x=1$ the left side is $6$, not $5$.
6. $\dfrac{x-1}{x+2}$, with $x\ne-2,2,-1$.
7. $\dfrac{x+3}{x-2}$, with $x\ne-2,2,3$.
8. $\dfrac{4x-1}{(x-1)(x+2)}$, with $x\ne1,-2$.
9. $\dfrac{x+2}{x(x+1)}$, with $x\ne0,-1$.
10. $\dfrac{x+1}{1-x}$, with $x\ne0,1$.
11. $\lbrace 3-\sqrt7,\,3+\sqrt7 \rbrace$.
12. No solution. Clearing the denominator gives $x=1$, but that value is excluded from the original equation.
13. $\mathbb R\setminus\lbrace 1 \rbrace$; the equality is an identity on the original domain.
14. $\varnothing$, because the equation reduces to $0=1$ on its domain.
15. $\lbrace \dfrac{1-\sqrt5}{2},\dfrac{1+\sqrt5}{2} \rbrace$; neither candidate is $0$ or $-1$.
18. $\dfrac{1}{1/8+1/4}=\dfrac{8}{3}$ hours.
19. $\dfrac{2(40)(60)}{40+60}=48$ km/h, the harmonic mean for equal distances.
20. Example: $(x^2-1)/(x-1)$ and $x+1$. Their formulas agree for $x\ne1$, but the first original expression excludes $1$ and the second does not.

## 15. Chapter summary

- A rational expression is a quotient of polynomials with a nonzero denominator polynomial; its domain excludes every real zero of the original denominator.
- Simplifying a rational expression cancels common factors but never restores values excluded by the original expression.
- Equality by cross multiplication is valid only where both denominators are nonzero.
- Multiplication and division require the original denominators to be nonzero; division also requires the divisor's numerator to be nonzero.
- Addition and subtraction require a common denominator, usually the LCD.
- Complex fractions can be simplified by multiplying numerator and denominator by a common denominator for their inner fractions.
- To solve a rational equation, record restrictions, multiply by the LCD on the admissible domain, solve, and check every candidate in the original equation.
- A rational equation may have no solution, finitely many solutions, or every point of its admissible domain as a solution.
- Exact computation can verify examples but does not replace proof of a general identity.

## 16. Next chapter

**Chapter 11 — Radicals and Rational Exponents** develops real roots, radical simplification and operations, rational exponents, equations involving radicals, and domain checks. It builds on polynomial factoring from Chapters 08–09 and the domain discipline developed here.

## References

- Math-Atlas Algebra, Chapter 03 — Linear Equations and Literal Equations.
- Math-Atlas Algebra, Chapter 07 — Exponents and Scientific Notation.
- Math-Atlas Algebra, Chapter 08 — Polynomials and Polynomial Operations.
- Math-Atlas Algebra, Chapter 09 — Factoring and Polynomial Equations.
- Math-Atlas Algebra Conventions — domains, equality-preserving transformations, and exact arithmetic.
- OpenStax, *Algebra and Trigonometry 2e*, sections on rational expressions and rational equations.

**Next chapter:** Chapter 11 — Radicals and Rational Exponents.
