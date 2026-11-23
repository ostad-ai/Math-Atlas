# Algebra 11 — Radicals and Rational Exponents

## 1. Introduction

Chapter 07 introduced integer exponents, and Chapters 08–10 used polynomial and rational expressions. This chapter extends exponent notation to rational exponents and studies the corresponding roots. It also develops methods for simplifying radical expressions and solving equations that contain radicals.

The most important habits in this chapter are to state the real domain, distinguish an even root from an odd root, use the principal-root convention, and check every candidate after a transformation that may not be reversible. In particular, squaring both sides can create an extraneous solution.

### Learning objectives

By the end of this chapter, a learner should be able to:

- Define real roots of index $n$ and distinguish even-root and odd-root domains.
- Interpret the principal square root correctly.
- Simplify numerical and algebraic radicals without losing absolute values.
- Add, subtract, multiply, and divide radicals under valid domain conditions.
- Rationalize simple radical denominators using a radical or a conjugate.
- Define rational exponents, including the real-valued cases for negative bases.
- State safe laws for rational exponents and recognize when a familiar-looking law can fail.
- Solve radical equations while checking all candidates in the original equation.
- Use exact Python helpers for integer and rational roots, and recognize when a result is irrational.

## 2. Real roots of integer index

Let $n$ be a positive integer. A real root of index $n$ of a real number $a$ is a real number $r$ such that $r^n=a$.

- If $n$ is odd, every real number has exactly one real root of index $n$. Negative radicands are allowed.
- If $n$ is even and $a>0$, the equation $r^n=a$ has two real solutions, one positive and one negative. The radical symbol denotes only the nonnegative one.
- If $n$ is even and $a=0$, the equation $r^n=0$ has the single solution $r=0$.
- If $n$ is even and $a<0$, there is no real root of index $n$.

For even $n$, the symbol $\sqrt[n]{a}$ means the **principal root**, the unique nonnegative real number whose power with exponent $n$ is $a$, when $a\geq0$. For odd $n$, $\sqrt[n]{a}$ denotes the unique real root for every real $a$.

### Example 1 — Equation roots versus the radical symbol

The equation $u^2=25$ has two solutions, $u=-5$ and $u=5$. However,

$$
\sqrt{25}=5,
$$

because the square-root symbol denotes the principal, nonnegative square root. The radical is not a two-valued symbol.

By contrast,

$$
\sqrt[3]{-27}=-3,
$$

because an odd root preserves the sign of a negative radicand.

### 2.1 Radicand domains

For real-valued radicals:

- An even-index radical $\sqrt[n]{f(x)}$ requires $f(x)\geq0$.
- An odd-index radical $\sqrt[n]{f(x)}$ is defined for every real value of $f(x)$.
- A radical in a denominator must also be nonzero. For example, $1/\sqrt{f(x)}$ requires $f(x)>0$, not merely $f(x)\geq0$.

These restrictions are part of the domain of the original expression and must be recorded before simplifying or solving.

## 3. Simplifying radicals

A radical is simplified by extracting perfect powers from its radicand. For a square root, write the radicand as a product containing the largest convenient perfect-square factor.

### Example 2 — Extract a perfect square

$$
\sqrt{72}=\sqrt{36\cdot2}=6\sqrt2.
$$

The remaining radicand $2$ has no perfect-square factor greater than $1$.

### Example 3 — Simplify a rational radicand

$$
\sqrt{\frac{72}{25}}
=\frac{\sqrt{72}}{\sqrt{25}}
=\frac{6\sqrt2}{5}.
$$

The denominator is positive, so the quotient rule used here is valid.

### 3.1 Variables and absolute values

The principal-square-root convention gives

$$
\sqrt{x^2}=\lvert x\rvert,
$$

not simply $x$. The absolute value is necessary because the principal square root is nonnegative even when $x$ is negative.

More generally,

$$
\sqrt{(x-3)^2}=\lvert x-3\rvert.
$$

If an additional condition is known, the absolute value may be removed appropriately:

$$
\sqrt{x^2}=x\quad\text{when }x\geq0,
$$

and

$$
\sqrt{x^2}=-x\quad\text{when }x<0.
$$

For an odd index, there is no absolute value:

$$
\sqrt[3]{x^3}=x\qquad\text{for every real }x.
$$

### Example 4 — Simplify with an unrestricted variable

Simplify $\sqrt{50x^2}$ for real $x$.

$$
\sqrt{50x^2}=\sqrt{25\cdot2\cdot x^2}
=5\lvert x\rvert\sqrt2.
$$

If the problem additionally states $x\geq0$, this becomes $5x\sqrt2$. Without that condition, replacing $\lvert x\rvert$ by $x$ is not valid.

## 4. Products and quotients of radicals

For square roots, if $a\geq0$ and $b\geq0$, then

$$
\sqrt a\,\sqrt b=\sqrt{ab}.
$$

If $a\geq0$ and $b>0$, then

$$
\frac{\sqrt a}{\sqrt b}=\sqrt{\frac ab}.
$$

The strict condition $b>0$ is needed because the denominator cannot be zero. Similar product and quotient rules hold for odd-index real roots, with a nonzero denominator for division.

### Example 5 — Multiply square roots

$$
\sqrt{12}\,\sqrt{3}=\sqrt{36}=6.
$$

### Example 6 — Divide square roots

$$
\frac{\sqrt{75}}{\sqrt3}=\sqrt{25}=5.
$$

### 4.1 The sum rule does not exist

In general,

$$
\sqrt{a+b}\ne\sqrt a+\sqrt b.
$$

For example, $\sqrt{9+16}=5$, whereas $\sqrt9+\sqrt{16}=7$. The product rule is not an addition rule.

## 5. Adding and subtracting radical terms

Only **like radicals** can be combined directly. Like radicals have the same index and the same simplified radicand; their coefficients are then added or subtracted just as with like algebraic terms.

### Example 7 — Simplify before combining

$$
\begin{aligned}
\sqrt{12}+\sqrt{27}
&=2\sqrt3+3\sqrt3\\
&=5\sqrt3.
\end{aligned}
$$

The original radicands differ, but both terms simplify to multiples of $\sqrt3$.

By contrast, $\sqrt2+\sqrt3$ cannot be combined into a single like-radical term using the elementary rules of this chapter.

## 6. Rationalizing denominators

A denominator containing a radical is sometimes rewritten so that the denominator is rational. This process is called **rationalizing the denominator**. It does not change the value of the expression; it multiplies by a form of $1$ that is chosen to remove the radical from the denominator.

### Example 8 — One square root in the denominator

$$
\frac{5}{\sqrt{20}}
=\frac{5}{2\sqrt5}\cdot\frac{\sqrt5}{\sqrt5}
=\frac{\sqrt5}{2}.
$$

### 6.1 Conjugates

The conjugate of $a+b\sqrt c$ is $a-b\sqrt c$. Their product is a difference of squares:

$$
(a+b\sqrt c)(a-b\sqrt c)=a^2-b^2c.
$$

This identity can remove a square root from a binomial denominator.

### Example 9 — Rationalize using a conjugate

$$
\begin{aligned}
\frac{1}{\sqrt5-2}
&=\frac{1}{\sqrt5-2}\cdot\frac{\sqrt5+2}{\sqrt5+2}\\
&=\frac{\sqrt5+2}{5-4}\\
&=\sqrt5+2.
\end{aligned}
$$

The multiplier is valid because $\sqrt5+2\ne0$.

Rationalizing is a matter of form and convenience; it does not make an irrational number rational. The numerator may still contain a radical.

## 7. Rational exponents

Chapter 07 defined integer exponents. Rational exponents extend that notation to roots. Before using the definition with a negative base, first write the exponent in lowest terms.

### 7.1 Positive bases

Let $r=\frac{p}{q}$ be a rational number in lowest terms, where $p$ is an integer and $q$ is a positive integer.

For $a>0$, define

$$
a^{p/q}=\left(\sqrt[q]{a}\right)^p.
$$

This definition is real for every rational $p/q$. If $p<0$, the value is a reciprocal, so the base must be nonzero; the condition $a>0$ already guarantees that.

For example,

$$
16^{3/4}=\left(\sqrt[4]{16}\right)^3=2^3=8.
$$

### 7.2 Zero as a base

For $a=0$:

- $0^{p/q}=0$ when $p/q>0$.
- $0^{0}$ is undefined under this volume's convention.
- $0^{p/q}$ is undefined when $p/q<0$, because it would require division by zero.

### 7.3 Negative bases

For $a<0$, a real value exists under this rational-exponent convention only when the **reduced denominator $q$ is odd**. In that case, the odd root is real and unique, and

$$
a^{p/q}=\left(\sqrt[q]{a}\right)^p.
$$

If the reduced denominator is even, the real value is undefined. Reduce the fraction $p/q$ before applying this rule.

Examples:

$$
(-8)^{1/3}=-2,
\qquad
(-8)^{2/3}=(-2)^2=4,
$$

and

$$
(-8)^{-1/3}=\frac{1}{-2}=-\frac12.
$$

But $(-8)^{1/2}$ has no real value.

### Example 10 — Reduce the exponent first

Evaluate $(-8)^{2/6}$ over the reals.

Reduce the exponent: $2/6=1/3$. Its denominator is odd, so

$$
(-8)^{2/6}=(-8)^{1/3}=-2.
$$

The reduced-denominator condition avoids ambiguity caused by writing the same rational number in different forms.

## 8. Laws of rational exponents and their conditions

For positive real bases $a,b>0$ and rational exponents $r,s$, the familiar exponent laws hold:

| Law | Formula | Conditions |
|---|---|---|
| Product of powers | $a^r a^s=a^{r+s}$ | $a>0$ |
| Quotient of powers | $a^r/a^s=a^{r-s}$ | $a>0$ |
| Power of a power | $(a^r)^s=a^{rs}$ | $a>0$ |
| Power of a product | $(ab)^r=a^r b^r$ | $a>0$, $b>0$ |
| Negative exponent | $a^{-r}=1/a^r$ | $a>0$ |

These positive-base conditions are deliberately conservative: they make every rational power real and avoid parity exceptions. Some identities also hold for particular negative bases and exponents, but there is no need to extend every law without checking the real-domain conditions.

### 8.1 Why the laws hold for positive bases

The positivity condition lets us use a unique positive root at every step. A common-denominator argument reduces the rational-exponent rules to the integer-exponent laws from Chapter 07.

For example, choose a positive integer $L$ that is a common multiple of the denominators of $r$ and $s$, and write $r=R/L$ and $s=S/L$ with integers $R,S$. Let $t=\sqrt[L]{a}>0$. Then $a^r=t^R$ and $a^s=t^S$, so

$$
a^r a^s=t^R t^S=t^{R+S}=a^{r+s}.
$$

For the power-of-a-power rule, write $r=p/q$ and $s=m/n$ in lowest terms and let $t=\sqrt[qn]{a}>0$. Because $a=t^{qn}$,

$$
a^r=t^{pn},\qquad (a^r)^s=(\sqrt[n]{t^{pn}})^m=t^{pm}=a^{rs}.
$$

For the power-of-a-product rule, let $u=\sqrt[q]{a}>0$ and $v=\sqrt[q]{b}>0$. Since $(uv)^q=ab$, uniqueness of the positive root of index $q$ gives

$$
(ab)^{p/q}=(uv)^p=u^p v^p=a^{p/q}b^{p/q}.
$$

The quotient rule follows by applying the product rule to $a\cdot(1/a)=1$, with $a>0$. Positivity matters because it keeps every intermediate rational power real and selects a unique positive root.

### 8.2 A power-of-a-power warning for negative bases

The identity $(a^r)^s=a^{rs}$ is not valid for all negative bases and rational exponents, even when both sides happen to be real. For example,

$$
\left((-1)^2\right)^{1/2}=1,
\qquad
(-1)^{2\cdot(1/2)}=(-1)^1=-1.
$$

Therefore, use the listed laws freely for positive bases. For negative bases, return to the definition and check each expression separately.

### Example 11 — Evaluate a rational power

$$
64^{2/3}=\left(\sqrt[3]{64}\right)^2=4^2=16.
$$

### Example 12 — A negative rational exponent

$$
81^{-3/4}
=\frac{1}{81^{3/4}}
=\frac{1}{(\sqrt[4]{81})^3}
=\frac{1}{3^3}
=\frac1{27}.
$$

## 9. Equivalence between radicals and rational exponents

For $a\geq0$ and a positive integer $n$,

$$
\sqrt[n]{a}=a^{1/n}.
$$

For an even index, the radical is the principal nonnegative root. Thus,

$$
\sqrt{x^2}=\lvert x\rvert=(x^2)^{1/2},
$$

and not $x$ for every real $x$.

For an odd index, the real-root convention gives

$$
\sqrt[n]{a}=a^{1/n}
$$

for negative as well as nonnegative real $a$.

For a positive base, rational exponent notation can make nested-root expressions easier to interpret. However, the power-of-a-power warning in Section 8 still matters when the base is negative.

## 10. Solving equations involving radicals

The safe method is:

1. State the real domain of every even-index radical.
2. Isolate one radical if possible.
3. Record any sign condition forced by the principal-root convention. In particular, if $\sqrt{F(x)}=G(x)$, then $G(x)\geq0$ is necessary.
4. Raise both sides to the required power, noting whether this operation is reversible on the stated domain.
5. Solve the resulting equation.
6. Check every candidate in the **original equation** and reject any candidate that violates the original domain or equality.

### 10.1 Squaring both sides can introduce candidates

For a real equation $\sqrt{F(x)}=G(x)$, a useful equivalent system is

$$
F(x)=G(x)^2,\qquad G(x)\geq0.
$$

The squared equation alone is not equivalent unless the sign condition is also retained. Squaring maps both a number and its negative to the same square, so it is not one-to-one on all real numbers.

### Example 13 — Solve and check

Solve

$$
\sqrt{x+6}=x.
$$

The left side is nonnegative, so $x\geq0$. Square both sides:

$$
x+6=x^2
\quad\Longleftrightarrow\quad
(x-3)(x+2)=0.
$$

The candidates are $x=3$ and $x=-2$. The sign condition $x\geq0$ rejects $-2$. Check $x=3$ in the original equation: $\sqrt{3+6}=3$, so the solution set is $\{3\}$.

### Example 14 — Squaring produces an extraneous candidate

Solve

$$
\sqrt{2x+3}=x.
$$

The domain and sign condition require $2x+3\geq0$ and $x\geq0$, so $x\geq0$. Squaring gives

$$
2x+3=x^2
\quad\Longleftrightarrow\quad
(x-3)(x+1)=0.
$$

The candidates are $3$ and $-1$. The condition $x\geq0$ already excludes $-1$. Checking $x=3$ gives $\sqrt9=3$, so the solution is $\{3\}$.

### Example 15 — A sign condition proves there is no solution

The equation

$$
\sqrt{x+1}=-2
$$

has no real solution. Whenever its left side is defined, it is nonnegative, whereas the right side is negative. No squaring is needed.

### 10.2 Odd-root equations

An odd-power function is one-to-one on the real numbers. Therefore, applying the same odd power to both sides of an equation involving an isolated real odd root preserves equivalence.

### Example 16 — Solve a cube-root equation

$$
\sqrt[3]{2x-1}=3
\quad\Longleftrightarrow\quad
2x-1=27
\quad\Longleftrightarrow\quad
x=14.
$$

Cubing is reversible over the reals because every real number has exactly one real cube root. The candidate also satisfies the original equation.

## 11. Applications

### Example 17 — Side length from area

A square has area $A=98\text{ cm}^2$. Its side length $s$ satisfies $s^2=98$ and, because a length is nonnegative, $s\geq0$. Thus,

$$
s=\sqrt{98}=7\sqrt2\text{ cm}.
$$

The equation $s^2=98$ also has the algebraic solution $s=-7\sqrt2$, but a negative side length is not physically admissible.

### Example 18 — A geometric measurement equation

A rectangle has width $w=\sqrt{12}$ metres and length $l=\sqrt{27}$ metres. Its perimeter is

$$
P=2(l+w)=2(3\sqrt3+2\sqrt3)=10\sqrt3\text{ m}.
$$

The simplification uses like radicals; it does not combine unlike radicals directly.

## 12. Exact radical calculations with Python

The standard library's `math.isqrt` gives the floor of an integer square root. The self-contained Python implementation below extends this idea to exact integer roots, rational roots, square-root simplification, and rational powers whose exact result is rational.

It deliberately raises an error when the exact result is irrational or when a real value does not exist. It does not silently approximate an irrational number.

### Example 19 — Simplify a rational square root

```python
from __future__ import annotations

# --- Inlined implementation: radical_core ---
#!/usr/bin/env python3
"""Exact helpers for selected radical and rational-power calculations.

This is a small teaching module, not a computer algebra system. It handles
integer/rational inputs and reports when a requested exact rational result
would be irrational.
"""


from fractions import Fraction


ExactInput = int | Fraction


def _as_fraction(value: ExactInput, name: str) -> Fraction:
    if isinstance(value, bool) or not isinstance(value, (int, Fraction)):
        raise TypeError(f"{name} must be an int or Fraction; floats and bools are rejected")
    return value if isinstance(value, Fraction) else Fraction(value)


def _check_index(index: int) -> None:
    if isinstance(index, bool) or not isinstance(index, int):
        raise TypeError("root index must be an integer")
    if index < 1:
        raise ValueError("root index must be positive")


def integer_nth_root(value: int, index: int) -> int:
    """Return the exact integer nth root; raise ValueError if none exists.

    Odd roots of negative integers are supported. Even roots of negative
    integers are not real and are rejected.
    """
    if isinstance(value, bool) or not isinstance(value, int):
        raise TypeError("value must be an integer")
    _check_index(index)
    if value < 0:
        if index % 2 == 0:
            raise ValueError("an even root of a negative number is not real")
        return -integer_nth_root(-value, index)
    if value in (0, 1) or index == 1:
        return value

    low = 0
    high = 1 << ((value.bit_length() + index - 1) // index)
    while low <= high:
        mid = (low + high) // 2
        power = mid ** index
        if power == value:
            return mid
        if power < value:
            low = mid + 1
        else:
            high = mid - 1
    raise ValueError(f"{value} is not a perfect {index}th power")


def rational_nth_root(value: ExactInput, index: int) -> Fraction:
    """Return an exact rational nth root when it exists."""
    value = _as_fraction(value, "value")
    _check_index(index)
    if value < 0 and index % 2 == 0:
        raise ValueError("an even root of a negative rational is not real")
    numerator_root = integer_nth_root(value.numerator, index)
    denominator_root = integer_nth_root(value.denominator, index)
    return Fraction(numerator_root, denominator_root)


def _squarefree_decomposition(value: int) -> tuple[int, int]:
    """Return outside, inside with value = outside**2 * inside."""
    outside = 1
    inside = 1
    remaining = value
    divisor = 2
    while divisor * divisor <= remaining:
        exponent = 0
        while remaining % divisor == 0:
            remaining //= divisor
            exponent += 1
        if exponent:
            outside *= divisor ** (exponent // 2)
            if exponent % 2:
                inside *= divisor
        divisor = 3 if divisor == 2 else divisor + 2
    if remaining > 1:
        inside *= remaining
    return outside, inside


def simplify_square_root(value: ExactInput) -> tuple[Fraction, int]:
    """Return (outside, radicand) so sqrt(value)=outside*sqrt(radicand).

    The result uses a square-free nonnegative integer radicand. For zero the
    canonical result is (Fraction(0), 1). No floating-point approximation is
    performed.
    """
    value = _as_fraction(value, "value")
    if value < 0:
        raise ValueError("the real square root requires a nonnegative radicand")
    if value == 0:
        return Fraction(0), 1
    combined = value.numerator * value.denominator
    outside_integer, radicand = _squarefree_decomposition(combined)
    outside = Fraction(outside_integer, value.denominator)
    return outside, radicand


def exact_rational_power(base: ExactInput, exponent: ExactInput) -> Fraction:
    """Evaluate a rational power exactly when its value is rational.

    The exponent is reduced automatically by Fraction. Negative bases are
    allowed only when the reduced denominator is odd. A zero base requires a
    strictly positive exponent. Irrational results raise ValueError rather
    than being approximated silently.
    """
    base = _as_fraction(base, "base")
    exponent = _as_fraction(exponent, "exponent")
    p, q = exponent.numerator, exponent.denominator

    if base == 0:
        if p <= 0:
            raise ZeroDivisionError("zero to a zero or negative exponent is undefined")
        return Fraction(0)
    if base < 0 and q % 2 == 0:
        raise ValueError("a negative base has no real value for an exponent with even reduced denominator")

    root = rational_nth_root(base, q)
    try:
        return root ** p
    except ZeroDivisionError as exc:
        raise ZeroDivisionError("zero cannot be raised to a negative exponent") from exc

# --- Chapter example ---
simplify_square_root = simplify_square_root

from fractions import Fraction


outside, inside = simplify_square_root(Fraction(72, 25))
print(outside, inside)  # 6/5 2
# Therefore sqrt(72/25) = (6/5) * sqrt(2).
```

### Example 20 — Evaluate exact rational powers

```python
from __future__ import annotations

# --- Inlined implementation: radical_core ---
#!/usr/bin/env python3
"""Exact helpers for selected radical and rational-power calculations.

This is a small teaching module, not a computer algebra system. It handles
integer/rational inputs and reports when a requested exact rational result
would be irrational.
"""


from fractions import Fraction


ExactInput = int | Fraction


def _as_fraction(value: ExactInput, name: str) -> Fraction:
    if isinstance(value, bool) or not isinstance(value, (int, Fraction)):
        raise TypeError(f"{name} must be an int or Fraction; floats and bools are rejected")
    return value if isinstance(value, Fraction) else Fraction(value)


def _check_index(index: int) -> None:
    if isinstance(index, bool) or not isinstance(index, int):
        raise TypeError("root index must be an integer")
    if index < 1:
        raise ValueError("root index must be positive")


def integer_nth_root(value: int, index: int) -> int:
    """Return the exact integer nth root; raise ValueError if none exists.

    Odd roots of negative integers are supported. Even roots of negative
    integers are not real and are rejected.
    """
    if isinstance(value, bool) or not isinstance(value, int):
        raise TypeError("value must be an integer")
    _check_index(index)
    if value < 0:
        if index % 2 == 0:
            raise ValueError("an even root of a negative number is not real")
        return -integer_nth_root(-value, index)
    if value in (0, 1) or index == 1:
        return value

    low = 0
    high = 1 << ((value.bit_length() + index - 1) // index)
    while low <= high:
        mid = (low + high) // 2
        power = mid ** index
        if power == value:
            return mid
        if power < value:
            low = mid + 1
        else:
            high = mid - 1
    raise ValueError(f"{value} is not a perfect {index}th power")


def rational_nth_root(value: ExactInput, index: int) -> Fraction:
    """Return an exact rational nth root when it exists."""
    value = _as_fraction(value, "value")
    _check_index(index)
    if value < 0 and index % 2 == 0:
        raise ValueError("an even root of a negative rational is not real")
    numerator_root = integer_nth_root(value.numerator, index)
    denominator_root = integer_nth_root(value.denominator, index)
    return Fraction(numerator_root, denominator_root)


def _squarefree_decomposition(value: int) -> tuple[int, int]:
    """Return outside, inside with value = outside**2 * inside."""
    outside = 1
    inside = 1
    remaining = value
    divisor = 2
    while divisor * divisor <= remaining:
        exponent = 0
        while remaining % divisor == 0:
            remaining //= divisor
            exponent += 1
        if exponent:
            outside *= divisor ** (exponent // 2)
            if exponent % 2:
                inside *= divisor
        divisor = 3 if divisor == 2 else divisor + 2
    if remaining > 1:
        inside *= remaining
    return outside, inside


def simplify_square_root(value: ExactInput) -> tuple[Fraction, int]:
    """Return (outside, radicand) so sqrt(value)=outside*sqrt(radicand).

    The result uses a square-free nonnegative integer radicand. For zero the
    canonical result is (Fraction(0), 1). No floating-point approximation is
    performed.
    """
    value = _as_fraction(value, "value")
    if value < 0:
        raise ValueError("the real square root requires a nonnegative radicand")
    if value == 0:
        return Fraction(0), 1
    combined = value.numerator * value.denominator
    outside_integer, radicand = _squarefree_decomposition(combined)
    outside = Fraction(outside_integer, value.denominator)
    return outside, radicand


def exact_rational_power(base: ExactInput, exponent: ExactInput) -> Fraction:
    """Evaluate a rational power exactly when its value is rational.

    The exponent is reduced automatically by Fraction. Negative bases are
    allowed only when the reduced denominator is odd. A zero base requires a
    strictly positive exponent. Irrational results raise ValueError rather
    than being approximated silently.
    """
    base = _as_fraction(base, "base")
    exponent = _as_fraction(exponent, "exponent")
    p, q = exponent.numerator, exponent.denominator

    if base == 0:
        if p <= 0:
            raise ZeroDivisionError("zero to a zero or negative exponent is undefined")
        return Fraction(0)
    if base < 0 and q % 2 == 0:
        raise ValueError("a negative base has no real value for an exponent with even reduced denominator")

    root = rational_nth_root(base, q)
    try:
        return root ** p
    except ZeroDivisionError as exc:
        raise ZeroDivisionError("zero cannot be raised to a negative exponent") from exc

# --- Chapter example ---
exact_rational_power = exact_rational_power

from fractions import Fraction


print(exact_rational_power(64, Fraction(2, 3)))   # 16
print(exact_rational_power(-8, Fraction(2, 3)))   # 4
print(exact_rational_power(81, Fraction(-3, 4)))  # 1/27
```

An irrational exact result, such as $2^{1/2}$, is intentionally not returned as a `Fraction`. Use an explicitly approximate numerical method when a decimal approximation is required, and state the precision or tolerance.

### 12.1 What computation establishes

A program can check an exact example, verify a proposed rational root, or detect that a rational root does not exist. It cannot replace a proof of a general identity such as $\sqrt{x^2}=\lvert x\rvert$. That identity follows from the definition of the principal square root and the nonnegativity of absolute value.

## 13. Common errors and how to avoid them

| Common error | Correct reasoning |
|---|---|
| Writing $\sqrt{x^2}=x$ for every real $x$ | Use $\sqrt{x^2}=\lvert x\rvert$; remove absolute value only with a sign condition. |
| Treating $\sqrt{a}$ as both roots | The radical symbol denotes the principal nonnegative root. Solve $u^2=a$ separately when both roots are requested. |
| Taking an even root of a negative real number | There is no real value; state when a complex-number extension is intended. |
| Splitting a square root across a sum | The product rule does not distribute over addition. |
| Combining unlike radicals | Simplify each radical first; combine only like radical terms. |
| Applying rational-exponent laws to negative bases without checking | Reduce the exponent and check the real-domain/parity conditions. |
| Assuming $(a^r)^s=a^{rs}$ for all negative $a$ | This law is listed without parity exceptions only for positive bases. |
| Squaring both sides and accepting every candidate | Check candidates in the original equation and retain sign/domain conditions. |
| Omitting the condition that a radical denominator is nonzero | For $1/\sqrt{F(x)}$, require $F(x)>0$. |

## 14. Exercises

### A. Real roots and simplification

1. Evaluate $\sqrt{169}$ and solve $u^2=169$.
2. Evaluate $\sqrt[3]{-216}$.
3. Simplify $\sqrt{200}$.
4. Simplify $\sqrt{98/49}$.
5. Simplify $\sqrt{(x-2)^2}$ for real $x$.
6. Simplify $\sqrt{50x^2}$ for real $x$, and then state the result if $x\geq0$.
7. Simplify $\sqrt{12}+\sqrt{27}$.
8. Simplify $\sqrt3\,\sqrt{12}$.
9. Simplify $\sqrt{5/8}$.
10. Rationalize $5/\sqrt{20}$.

### B. Rational exponents

11. Evaluate $64^{2/3}$.
12. Evaluate $(-32)^{2/5}$.
13. Evaluate $16^{-3/4}$.
14. Evaluate $(-27)^{-2/3}$.
15. State whether $0^{2/3}$ and $0^{-2/3}$ are defined over the reals.
16. State whether $(-8)^{1/4}$ and $(-8)^{1/3}$ are real; evaluate the one that has an exact integer value.

### C. Radical equations

17. Solve $\sqrt{3x+4}=4$.
18. Solve $\sqrt{x+6}=x$ and check all candidates.
19. Solve $\sqrt[3]{5x+1}=-2$.
20. Solve $\sqrt{x+1}=-2$ over the reals.
21. Solve $\sqrt{x+4}=\sqrt{2x+1}$.
22. Solve $2\sqrt{x-1}=\sqrt{3x+5}$, checking the original equation.

### D. Reasoning and applications

23. Explain why $\sqrt{x^2}=\lvert x\rvert$ for every real $x$.
24. Give a numerical counterexample to $\sqrt{a+b}=\sqrt a+\sqrt b$.
25. Explain why $\sqrt{x+6}=x$ requires $x\geq0$ before squaring.
26. Find the real domain of $1/\sqrt{2x-6}$.
27. A square has area $72\text{ m}^2$. Find its side length exactly.
28. Explain why the power-of-a-power identity in Section 8 is stated for positive bases.

## 15. Selected answers and solution outlines

1. $\sqrt{169}=13$; the equation has solutions $u=\pm13$.
2. $-6$.
3. $10\sqrt2$.
4. $\sqrt2$.
5. $|x-2|$.
6. $5\lvert x\rvert\sqrt2$; if $x\geq0$, this is $5x\sqrt2$.
7. $5\sqrt3$.
8. $6$.
9. $\sqrt{10}/4$.
10. $\sqrt5/2$.
11. $16$.
12. $4$.
13. $1/8$.
14. $1/9$.
15. $0^{2/3}=0$ is defined; $0^{-2/3}$ is undefined.
16. $(-8)^{1/4}$ is not real; $(-8)^{1/3}=-2$.
17. $x=4$.
18. Candidates are $3$ and $-2$; only $x=3$ satisfies the original equation.
19. $x=-9/5$.
20. No real solution, because a principal square root cannot be negative.
21. Domain requires $x\geq-1/2$. Squaring gives $x+4=2x+1$, so $x=3$, which is valid.
22. Domain requires $x\geq1$. Squaring gives $4(x-1)=3x+5$, so $x=9$. Substitution verifies both sides equal $4\sqrt2$.
23. The principal square root is nonnegative. If $x\geq0$, it equals $x$; if $x<0$, it equals $-x$. Both cases equal $\lvert x\rvert$.
24. For $a=9$ and $b=16$, the left side is $5$ and the right side is $7$.
25. The left side is nonnegative, so equality forces the right side $x$ to be nonnegative.
26. $2x-6>0$, so $x>3$; the domain is $(3,\infty)$.
27. The side length is $\sqrt{72}=6\sqrt2$ metres.
28. Nested rational powers of negative bases can fail because the principal even root is nonnegative and rational powers of negative bases depend on parity. For example, $((-1)^2)^{1/2}=1$ but $(-1)^1=-1$.

## 16. Chapter summary

- Even-index real roots require nonnegative radicands and denote principal, nonnegative roots.
- Odd-index real roots exist uniquely for every real radicand.
- Simplifying square roots of squares requires absolute values: $\sqrt{x^2}=\lvert x\rvert$.
- Product and quotient rules for square roots require nonnegative radicands, and a strictly positive denominator radicand for division.
- Rational exponents are defined after reducing the exponent to lowest terms. For a negative base, the reduced denominator must be odd for a real value.
- Standard rational-exponent laws are safest when stated for positive bases.
- Squaring both sides may introduce extraneous candidates; check every candidate in the original equation.
- Exact computation should remain exact when possible, and irrational values should not be silently rounded.

## 17. Next chapter

Chapter 12 develops quadratic equations and quadratic models, building on the factoring and equation-solving methods developed in earlier chapters.

## References and connections

- Math-Atlas Foundations, Chapter 04 — Number Systems and Mathematical Structures.
- Math-Atlas Foundations, Chapter 05 — Mathematical Proof Techniques.
- Math-Atlas Algebra, Chapter 07 — Exponents and Scientific Notation.
- Math-Atlas Algebra, Chapter 10 — Rational Expressions and Equations.
- Math-Atlas Algebra, `ALGEBRA_CONVENTIONS.MD` — real domains, exponents, radicals, and exact computation.

**Next chapter:** Chapter 12 — Quadratic Equations and Quadratic Models.
