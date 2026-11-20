# Algebra 07 — Exponents and Scientific Notation

## 1. Introduction

An exponent is a compact way to describe repeated multiplication. Exponents also make it possible to represent extremely large and extremely small quantities without writing long strings of zeros. They appear in algebraic simplification, geometry, science, computing, and mathematical models.

This chapter develops **integer exponents** and scientific notation. It explains the conditions under which the exponent laws are valid, including the special cases of zero and negative bases. It then applies powers of ten to calculations, measurement, scaling, and repeated multiplicative change.

The chapter does not yet develop general rational exponents or radical equations; those belong to Chapter 11. Nor does it develop exponential functions with a real-valued input; those belong to Chapter 16. Here, repeated change is described at integer steps.

### Learning objectives

By the end of this chapter, a learner should be able to:

- Interpret positive integer powers as repeated multiplication.
- Explain the definitions of zero and negative integer exponents and state their restrictions.
- Apply the product, quotient, power-of-a-power, and power-of-a-product laws with valid domains.
- Distinguish a negative base from a leading negative sign.
- Simplify expressions involving integer powers without expanding unnecessarily.
- Write a nonzero number in normalized scientific notation and convert back.
- Multiply, divide, add, and subtract numbers in scientific notation.
- Interpret significant figures and rounding without confusing a rounded measurement with an exact value.
- Model repeated multiplicative change and determine how length, area, and volume scale.
- Use Python's integer, `Fraction`, and `Decimal` types appropriately for exact or controlled calculations.

## 2. What an integer exponent means

For a real number $a$ and a positive integer $n$, the power $a^n$ means that $a$ is used as a factor $n$ times:

$$
a^n=\underbrace{a\cdot a\cdots a}_{n\text{ factors}}.
$$

The number $a$ is the **base** and $n$ is the **exponent**. For example,

$$
4^3=4\cdot4\cdot4=64.
$$

An exponent is not a multiplier. In particular, $4^3$ is not $4\cdot3$.

### 2.1 First examples and sign of the base

The parentheses show whether the negative sign belongs to the base:

$$
(-3)^2=(-3)(-3)=9,
\qquad
-3^2=-(3^2)=-9.
$$

Exponentiation is performed before a leading unary negative sign unless parentheses make the negative number the base. Thus $(-3)^2$ and $-3^2$ are different expressions.

For a negative base, parity determines the sign of an integer power:

- If $n$ is even and positive, $(-a)^n$ is nonnegative; it is positive when $a\ne0$.
- If $n$ is odd and positive, $(-a)^n$ has the opposite sign from $a^n$ when $a>0$.

For example, $(-2)^4=16$ while $(-2)^3=-8$.

### 2.2 The zero exponent

For every nonzero real number $a$, define

$$
a^0:=1,\qquad a\ne0.
$$

This definition is consistent with the quotient law. If $a\ne0$, then

$$
\frac{a^n}{a^n}=1
$$

and the quotient law requires the same ratio to be $a^{n-n}=a^0$. Therefore $a^0=1$.

The expression $0^0$ is **left undefined in this elementary-algebra volume**. Some advanced areas adopt context-specific conventions, but no such convention is needed here. The value $0^0$ must not be obtained by applying the nonzero-base zero-exponent rule to a zero base.

For a positive integer $n$, $0^n=0$.

### 2.3 Negative integer exponents

For a nonzero real number $a$ and a positive integer $n$, define

$$
a^{-n}:=\frac{1}{a^n},\qquad a\ne0.
$$

A negative exponent means **take the reciprocal of the corresponding positive power**. It does not make the value negative.

For example,

$$
2^{-3}=\frac{1}{2^3}=\frac18,
\qquad
(-2)^{-2}=\frac{1}{(-2)^2}=\frac14,
\qquad
(-2)^{-3}=\frac{1}{(-2)^3}=-\frac18.
$$

The base must be nonzero. Therefore $0^{-n}$ is undefined because it would require division by zero.

### 2.4 A compact definition for integer powers

For an integer $n$, the usual real-valued integer power is defined by

$$
a^n=\begin{cases}
\underbrace{a\cdot a\cdots a}_{n\text{ factors}}, & n>0,\\
1, & n=0\text{ and }a\ne0,\\
\dfrac{1}{a^{-n}}, & n<0\text{ and }a\ne0.
\end{cases}
$$

This definition makes clear why zero is allowed as a base for positive exponents but not for zero or negative exponents.

## 3. The laws of integer exponents

The exponent laws are consequences of the definition of powers and the properties of multiplication. They are not rules that can be applied without checking the base and the exponent.

### 3.1 Product of powers with the same base

For a nonzero real number $a$ and integers $m,n$,

$$
a^m a^n=a^{m+n}.
$$

For nonnegative $m$ and $n$, this follows by counting the total number of factors. The rule extends to negative integer exponents using the reciprocal definition. The nonzero-base restriction is needed when a negative exponent occurs.

Example:

$$
5^2\cdot5^3=5^{2+3}=5^5=3125.
$$

The bases must be the same. In general, $2^3\cdot3^2$ cannot be combined by adding the exponents because the bases differ.

### 3.2 Quotient of powers with the same base

For $a\ne0$ and integers $m,n$,

$$
\frac{a^m}{a^n}=a^{m-n}.
$$

The denominator is a power of $a$, so $a$ must be nonzero. For example,

$$
\frac{7^5}{7^2}=7^{5-2}=7^3=343.
$$

If the exponents are equal, the quotient is $1$ for a nonzero base: $a^4/a^4=a^0=1$. It is not defined when $a=0$.

### 3.3 A power raised to a power

For $a\ne0$ and integers $m,n$,

$$
(a^m)^n=a^{mn}.
$$

For positive exponents, this follows by counting repeated groups of factors. The reciprocal definition extends the result to negative integer exponents when the base is nonzero.

Example:

$$
(2^3)^4=2^{3\cdot4}=2^{12}=4096.
$$

### 3.4 Power of a product

For real numbers $a,b$ and a positive integer $n$,

$$
(ab)^n=a^n b^n.
$$

For $n=0$, the rule also applies when both $a$ and $b$ are nonzero. For a negative integer $n$, it is valid when both $a$ and $b$ are nonzero, because the reciprocal of $ab$ must be defined.

Example:

$$
(2\cdot5)^3=2^3\cdot5^3=8\cdot125=1000.
$$

### 3.5 Power of a quotient

For real $a$, nonzero real $b$, and a positive integer $n$,

$$
\left(\frac ab\right)^n=\frac{a^n}{b^n}.
$$

For $n=0$ or a negative integer $n$, the rule also requires $a\ne0$. In all cases $b\ne0$ is required because the original quotient must be defined.

Example:

$$
\left(\frac23\right)^3=\frac{2^3}{3^3}=\frac8{27}.
$$

### 3.6 Summary of laws and conditions

| Law | Formula | Conditions |
|---|---|---|
| Product, same base | $a^m a^n=a^{m+n}$ | $a\ne0$ for arbitrary integers $m,n$; if $m,n>0$, $a=0$ is also allowed. |
| Quotient, same base | $a^m/a^n=a^{m-n}$ | $a\ne0$. |
| Power of a power | $(a^m)^n=a^{mn}$ | $a\ne0$ for unrestricted integer $m,n$. |
| Power of a product | $(ab)^n=a^n b^n$ | Any real $a,b$ if $n>0$; $a,b\ne0$ if $n\le0$. |
| Power of a quotient | $(a/b)^n=a^n/b^n$ | $b\ne0$ if $n>0$; $a,b\ne0$ if $n\le0$. |

### 3.7 Why the product law works

For positive integers $m,n$, expand each power using repeated multiplication:

$$
a^m a^n=
\underbrace{a\cdots a}_{m\text{ factors}}
\underbrace{a\cdots a}_{n\text{ factors}}
=a^{m+n}.
$$

The zero- and negative-exponent definitions make the same identity consistent for every integer exponent when $a\ne0$. For example, if $m=2$ and $n=-2$, then

$$
a^2a^{-2}=a^2\frac{1}{a^2}=1=a^0,
\qquad a\ne0.
$$

The restriction is essential: if $a=0$, the term $a^{-2}$ is undefined.

### 3.8 Common false rules

The following are not exponent laws:

$$
(a+b)^n\ne a^n+b^n\quad\text{in general},
$$

and

$$
a^m+b^m\ne a^{m+b}\quad\text{in general}.
$$

For example, $(2+3)^2=25$ while $2^2+3^2=13$. Exponents combine under multiplication or division of like bases, not under addition of terms.

## 4. Simplifying expressions with integer exponents

A reliable simplification process is:

1. Identify the base of each power, including any parentheses.
2. Record restrictions caused by zero or negative exponents and by denominators.
3. Apply one exponent law at a time.
4. Keep numerical coefficients separate from powers until their bases can legitimately be combined.
5. Rewrite negative exponents as reciprocals when a form with positive exponents is requested.
6. Check that the final expression has the same value for every value in the original domain.

### Example 1 — Product of like bases

Simplify $x^4x^7$.

The base is the same, so add the exponents:

$$
x^4x^7=x^{4+7}=x^{11}.
$$

No restriction on $x$ is needed because all exponents are positive integers.

### Example 2 — Quotient of like bases

Simplify $\dfrac{y^9}{y^3}$.

The denominator requires $y\ne0$. Subtract the exponents:

$$
\frac{y^9}{y^3}=y^{9-3}=y^6,
\qquad y\ne0.
$$

Even though the simplified expression $y^6$ is defined at $y=0$, the original quotient is not. The restriction $y\ne0$ must be retained.

### Example 3 — Negative exponents

Rewrite $\dfrac{a^{-2}b^3}{c^{-1}}$ using positive exponents, assuming $a\ne0$ and $c\ne0$.

A negative exponent indicates a reciprocal:

$$
\frac{a^{-2}b^3}{c^{-1}}
=\frac{b^3/a^2}{1/c}
=\frac{b^3c}{a^2}.
$$

The final form is $\dfrac{b^3c}{a^2}$ with restrictions $a\ne0$ and $c\ne0$ inherited from the original expression. No nonzero restriction on $b$ is required.

### Example 4 — Power of a product and a quotient

Simplify $\left(\dfrac{3x^2}{2y}\right)^2$, where $y\ne0$.

$$
\left(\frac{3x^2}{2y}\right)^2
=\frac{3^2(x^2)^2}{2^2y^2}
=\frac{9x^4}{4y^2}.
$$

The restriction $y\ne0$ remains. The value $x=0$ is permitted.

### Example 5 — Distinguish a negative base from a negative sign

Evaluate $(-4)^2$, $-4^2$, and $(-4)^{-2}$.

$$
(-4)^2=16,\qquad -4^2=-16,
\qquad (-4)^{-2}=\frac1{16}.
$$

The parentheses change the base; the negative exponent takes a reciprocal.

### Example 6 — A mixed numerical expression

Evaluate $\dfrac{2^3\cdot 2^{-5}}{2^{-1}}$.

All bases are equal and nonzero:

$$
\frac{2^3\cdot2^{-5}}{2^{-1}}
=2^{3+(-5)-(-1)}=2^{-1}=\frac12.
$$

### Example 7 — A variable expression with explicit restrictions

Simplify $\dfrac{(p^{-2}q^3)^2}{p q^{-1}}$.

The original expression requires $p\ne0$ and $q\ne0$. Apply the power laws:

$$
\frac{p^{-4}q^6}{p q^{-1}}
=p^{-4-1}q^{6-(-1)}
=p^{-5}q^7
=\frac{q^7}{p^5}.
$$

The complete result is $\dfrac{q^7}{p^5}$ for $p\ne0$ and $q\ne0$.

## 5. Powers of ten

Powers of ten are especially useful in the base-ten number system:

$$
10^3=1000,\qquad 10^2=100,\qquad 10^1=10,
$$

$$
10^0=1,\qquad 10^{-1}=0.1,\qquad 10^{-2}=0.01.
$$

For a positive integer $n$, $10^n$ is 1 followed by $n$ zeros. The reciprocal definition gives $10^{-n}=1/10^n$.

Multiplication by $10^n$ shifts the decimal point $n$ places to the right for positive $n$ and $n$ places to the left for negative $n$. This is a place-value description, not a separate arithmetic law.

For example,

$$
4.73\cdot10^3=4730,
\qquad
4.73\cdot10^{-3}=0.00473.
$$

## 6. Scientific notation

A nonzero real number is in **normalized scientific notation** when it is written as

$$
x=a\times10^n,
\qquad 1\le |a|<10,
\qquad n\in\mathbb Z.
$$

The coefficient $a$ may be negative; the condition is on its absolute value. The exponent $n$ records the decimal scale. Zero is written as $0$ and is treated separately because it has no unique normalized exponent.

### 6.1 Converting a number to scientific notation

To convert a nonzero decimal number:

1. Move the decimal point until the coefficient has absolute value at least 1 and less than 10.
2. Count the places moved.
3. Use a positive exponent when the decimal point was moved left, and a negative exponent when it was moved right.
4. Keep the sign of the original number.

Examples:

$$
58\,300\,000=5.83\times10^7,
$$

because the decimal point moves seven places left, and

$$
0.000072=7.2\times10^{-5},
$$

because it moves five places right.

For a negative number,

$$
-0.00091=-9.1\times10^{-4}.
$$

### 6.2 Converting scientific notation to ordinary decimal notation

Use the exponent to move the decimal point in the opposite direction:

$$
6.04\times10^5=604\,000,
\qquad
3.7\times10^{-4}=0.00037.
$$

### 6.3 Multiplication in scientific notation

Multiply the coefficients and add the powers of ten:

$$
(a\times10^m)(b\times10^n)
=(ab)\times10^{m+n}.
$$

The result may need to be normalized. For example,

$$
(3.0\times10^4)(2.0\times10^{-3})
=6.0\times10^{1}.
$$

### 6.4 Division in scientific notation

Divide the coefficients and subtract the exponents, provided the divisor is nonzero:

$$
\frac{a\times10^m}{b\times10^n}
=\frac ab\times10^{m-n},
\qquad b\ne0.
$$

For example,

$$
\frac{8.4\times10^8}{2.1\times10^3}
=4.0\times10^5.
$$

### 6.5 Addition and subtraction in scientific notation

Before adding or subtracting, express both numbers with the **same power of ten**. Then add or subtract the coefficients:

$$
4.2\times10^6+3.1\times10^5
=4.2\times10^6+0.31\times10^6
=4.51\times10^6.
$$

Similarly,

$$
1.05\times10^{-3}-2.0\times10^{-4}
=1.05\times10^{-3}-0.20\times10^{-3}
=0.85\times10^{-3}
=8.5\times10^{-4}.
$$

Adding coefficients while leaving unequal powers of ten unchanged is invalid. The powers must first be aligned.

## 7. Significant figures, precision, and rounding

Scientific notation can communicate how many digits of a measured value are being reported. The **significant figures** of a measured quantity are its meaningful reported digits, interpreted according to the measurement and reporting convention.

Examples:

- $4.72\times10^5$ has three significant figures.
- $4.720\times10^5$ has four significant figures; the trailing zero is reported as meaningful.
- $4.7\times10^{-3}$ has two significant figures.
- The notation $4700$ by itself may be ambiguous about whether trailing zeros are significant. Scientific notation can remove that ambiguity.

To round a nonzero positive or negative number to a specified number of significant figures:

1. Identify the first nonzero digit.
2. Keep the requested number of significant digits.
3. Inspect the next digit to decide whether to round up or leave the last kept digit unchanged under the adopted rounding rule.
4. If appropriate, rewrite the rounded result in normalized scientific notation.

For example, to three significant figures,

$$
0.000047286\approx4.73\times10^{-5}.
$$

The symbol $\approx$ is used because rounding changes the value. It is not an exact equality.

**Precision is not the same as accuracy.** Precision concerns the granularity or repeatability of reported measurements; accuracy concerns closeness to the true or accepted value. A long decimal expansion is not automatically accurate. The number of digits reported should be justified by the measurement or calculation context.

For multiplication and division of measured quantities, a common introductory convention is to report no more significant figures than the least precise measured factor. For addition and subtraction, a common convention is to round according to the least precise decimal place. These are measurement-reporting conventions, not algebraic identities; follow the rules specified by the scientific context.

## 8. Repeated multiplicative change and scaling

A repeated additive change uses the same amount each step. A repeated multiplicative change uses the same factor each step. The latter naturally produces powers.

If a quantity begins at $Q_0$ and is multiplied by a fixed factor $r$ at each integer step, then after $n$ steps,

$$
Q_n=Q_0r^n,
\qquad n\in\mathbb N.
$$

Here $Q_0$ is the initial quantity and $r$ is the per-step multiplier. If $r>1$, the quantity increases at each step when $Q_0>0$. If $0<r<1$, it decreases at each step when $Q_0>0$. The model assumes the same multiplier at every step and does not by itself explain why that multiplier is appropriate.

### Example 8 — Repeated tripling

A culture begins with 500 cells in a simplified model and triples at each observation interval. After four intervals,

$$
Q_4=500\cdot3^4=500\cdot81=40\,500.
$$

This is a discrete-step model. The example assumes the tripling factor is constant and ignores resource limits and measurement error.

### Example 9 — Length, area, and volume scaling

If every length in a similar geometric object is multiplied by a positive scale factor $k$, then:

- lengths are multiplied by $k$;
- areas are multiplied by $k^2$;
- volumes are multiplied by $k^3$.

For a square with side length $s$, the original area is $s^2$. If its side is doubled, the new area is $(2s)^2=4s^2$, so the area is four times as large. For a cube with side length $s$, doubling the side gives volume $(2s)^3=8s^3$, eight times the original volume.

The exponents 2 and 3 arise from multiplying two or three length dimensions, respectively. The scale-factor statement assumes the objects are geometrically similar and all corresponding dimensions are scaled by the same factor.

### Example 10 — Comparing polynomial and exponential patterns

For positive integers $n$, compare $n^2$ and $2^n$:

| $n$ | $n^2$ | $2^n$ |
|---:|---:|---:|
| 1 | 1 | 2 |
| 2 | 4 | 4 |
| 3 | 9 | 8 |
| 4 | 16 | 16 |
| 5 | 25 | 32 |
| 6 | 36 | 64 |

The table shows that the exponential pattern eventually exceeds the quadratic pattern in these values. A finite table illustrates the comparison but does not prove a general statement for every positive integer. Formal comparison of growth rates belongs to later study.

## 9. Common errors and how to avoid them

1. **Treating an exponent as multiplication.** $3^4$ is four factors of 3, not $3\cdot4$.
2. **Forgetting parentheses around a negative base.** $(-2)^4=16$, whereas $-2^4=-16$.
3. **Thinking a negative exponent makes a value negative.** $a^{-n}$ is a reciprocal, not a sign instruction.
4. **Using $a^0=1$ when $a=0$.** The zero-exponent rule here requires $a\ne0$; $0^0$ is left undefined.
5. **Applying a negative exponent to a zero base.** $0^{-n}$ is undefined.
6. **Adding exponents when adding terms.** The product law applies to multiplication of like bases, not to sums.
7. **Combining unlike bases.** $2^3\cdot3^3$ can be combined as $(2\cdot3)^3$, but $2^3\cdot3^2$ cannot be combined by simply adding exponents.
8. **Using the power-of-a-sum false rule.** In general, $(a+b)^n$ is not $a^n+b^n$.
9. **Dropping an inherited restriction.** Simplifying $x^5/x^2$ to $x^3$ does not make the original quotient defined at $x=0$.
10. **Moving a decimal point in the wrong direction.** A small nonzero number between 0 and 1 has a negative exponent in normalized scientific notation.
11. **Adding scientific-notation coefficients before aligning exponents.** Rewrite both terms with the same power of ten first.
12. **Confusing exactness with the number of displayed digits.** A rounded value is an approximation even if it has many digits.
13. **Assuming a repeated-factor model is automatically realistic.** State the interval, multiplier, and assumptions behind the model.

## 10. Python: exact integer powers and scientific notation

Python integers support arbitrarily large integer values within available memory, so positive integer powers can be calculated exactly. For negative exponents, use `Fraction` when an exact rational answer is required; Python's built-in integer power with a negative exponent otherwise produces a floating-point result.

The helper below deliberately accepts only integer bases and integer exponents, rejects booleans (which are a subclass of `int` in Python), and rejects zero to a nonpositive exponent under this chapter's convention.

```python
from fractions import Fraction


def exact_integer_power(base: int, exponent: int) -> Fraction:
    """Return an exact integer power as a Fraction.

    Assumptions:
    - base and exponent are integers, not booleans;
    - 0**0 and zero to a negative exponent are rejected.
    """
    if isinstance(base, bool) or not isinstance(base, int):
        raise TypeError("base must be an integer")
    if isinstance(exponent, bool) or not isinstance(exponent, int):
        raise TypeError("exponent must be an integer")
    if base == 0 and exponent <= 0:
        raise ValueError("zero cannot have a zero or negative exponent here")
    return Fraction(base, 1) ** exponent


assert exact_integer_power(2, 10) == Fraction(1024, 1)
assert exact_integer_power(2, -3) == Fraction(1, 8)
assert exact_integer_power(-2, 5) == Fraction(-32, 1)
print("Exact integer-power examples passed.")
```

Python's `Decimal` type can represent decimal inputs without first converting them to binary floating point. The following function returns the coefficient and exponent of a finite nonzero decimal in normalized scientific notation. It constructs the coefficient from the decimal's digit tuple, so it does not need a context-rounded multiplication to move the decimal point.

```python
from decimal import Decimal, InvalidOperation


def scientific_parts(text: str) -> tuple[Decimal, int]:
    """Return (coefficient, exponent) for a finite decimal string.

    For nonzero inputs, 1 <= abs(coefficient) < 10 and
    Decimal(text) == coefficient * 10**exponent exactly.
    Zero is represented as (Decimal('0'), 0).
    """
    if not isinstance(text, str):
        raise TypeError("pass the decimal as text to avoid float conversion")
    try:
        value = Decimal(text)
    except InvalidOperation as exc:
        raise ValueError("text is not a valid decimal number") from exc

    if not value.is_finite():
        raise ValueError("scientific notation requires a finite value")
    if value.is_zero():
        return Decimal("0"), 0

    sign, digits, decimal_exponent = value.as_tuple()
    power = decimal_exponent + len(digits) - 1
    coefficient = Decimal((sign, digits, -(len(digits) - 1)))
    return coefficient, power


coefficient, power = scientific_parts("0.0000720")
assert coefficient == Decimal("7.20")
assert power == -5
coefficient, power = scientific_parts("-58300000")
assert coefficient == Decimal("-5.8300000")
assert power == 7
print("Scientific-notation normalization examples passed.")
```

For arithmetic with measured decimal quantities, choose a decimal precision suitable for the task and round only at the reporting stage. The following multiplication uses decimal strings and a local precision of 20 significant decimal digits.

```python
from decimal import Decimal, localcontext

with localcontext() as context:
    context.prec = 20
    product = Decimal("3.0e4") * Decimal("2.0e-3")
    quotient = Decimal("8.4e8") / Decimal("2.1e3")

assert product == Decimal("6.0e1")
assert quotient == Decimal("4.0e5")
print("Controlled Decimal arithmetic examples passed.")
```

### 10.1 What the code does and does not establish

The functions demonstrate exact integer powers, exact normalization of a decimal string into coefficient/exponent form, and controlled decimal arithmetic. They do not prove the exponent laws; those laws are justified mathematically in Section 3. Python's `Decimal` arithmetic is governed by a precision context, so calculations can be rounded when the exact result requires more digits than the context allows. The input string should be used instead of a Python float when decimal input must not first pass through binary floating-point representation.

## 11. Exercises

Unless otherwise stated, simplify over the real numbers and state restrictions inherited from the original expression. Give exact answers unless a question explicitly requests rounding.

### A. Meaning, signs, and definitions

1. Evaluate $5^3$ and explain why the result is not $5\cdot3$.
2. Evaluate $(-4)^2$, $-4^2$, and $(-4)^3$.
3. Evaluate $3^0$, $(-7)^0$, and $0^4$. State which of $0^0$ and $0^{-2}$ is defined under this chapter's convention.
4. Rewrite $2^{-4}$ and $(-3)^{-3}$ as fractions.

### B. Exponent laws

5. Simplify $x^5x^8$.
6. Simplify $\dfrac{a^{11}}{a^4}$ and state the restriction.
7. Simplify $(m^3)^5$.
8. Expand $(2xy)^3$.
9. Simplify $\left(\dfrac{3p^2}{2q}\right)^2$ and state the restriction.
10. Rewrite $\dfrac{r^{-3}s^2}{t^{-2}}$ using positive exponents and state restrictions.
11. Simplify $\dfrac{z^4z^{-7}}{z^{-1}}$ and state the restriction.
12. Explain why $(u+v)^2=u^2+v^2$ is not an identity; give one counterexample.

### C. Scientific notation

13. Write $72\,500\,000$ in normalized scientific notation.
14. Write $0.00000631$ in normalized scientific notation.
15. Convert $4.08\times10^6$ to ordinary decimal notation.
16. Convert $-6.5\times10^{-4}$ to ordinary decimal notation.
17. Calculate $(4.0\times10^5)(2.5\times10^{-3})$ and give the normalized result.
18. Calculate $\dfrac{9.6\times10^7}{3.2\times10^2}$.
19. Calculate $3.6\times10^5+4.2\times10^4$.
20. Calculate $1.2\times10^{-3}-3.5\times10^{-4}$.
21. Round $0.000083746$ to three significant figures and write the result in scientific notation.

### D. Modeling and reasoning

22. A quantity begins at 240 and is multiplied by 1.5 at each of three steps. Find the value after three steps.
23. Every length in a geometrically similar model is scaled by a factor of 4. By what factors do its area and volume change?
24. A bacteria model starts with 800 units and doubles every observation interval. Write a formula for the number after $n$ intervals and calculate the value after six intervals. State one limitation of the model.
25. For positive integers $n$, compare $n^2$ and $2^n$ at $n=3,4,5,6$. What does this table suggest, and why is the table not a proof for all positive integers?

## 12. Selected answers and solution outlines

1. $5^3=5\cdot5\cdot5=125$; the exponent counts the factors.
2. $(-4)^2=16$, $-4^2=-16$, and $(-4)^3=-64$.
3. $3^0=1$, $(-7)^0=1$, and $0^4=0$. Both $0^0$ and $0^{-2}$ are undefined here.
4. $2^{-4}=1/16$ and $(-3)^{-3}=-1/27$.
5. $x^{13}$.
6. $a^7$, with $a\ne0$ inherited from the denominator.
7. $m^{15}$.
8. $8x^3y^3$.
9. $9p^4/(4q^2)$, with $q\ne0$.
10. $s^2t^2/r^3$, with $r\ne0$ and $t\ne0$.
11. $z^{-2}=1/z^2$, with $z\ne0$.
12. For $u=v=1$, $(u+v)^2=4$ but $u^2+v^2=2$.
13. $7.25\times10^7$.
14. $6.31\times10^{-6}$.
15. $4\,080\,000$.
16. $-0.00065$.
17. $10.0\times10^2=1.0\times10^3$ after normalization.
18. $3.0\times10^5$.
19. $3.6\times10^5+0.42\times10^5=4.02\times10^5$.
20. $1.2\times10^{-3}-0.35\times10^{-3}=0.85\times10^{-3}=8.5\times10^{-4}$.
21. $8.37\times10^{-5}$.
22. $240(1.5)^3=810$.
23. Area factor $4^2=16$; volume factor $4^3=64$.
24. $Q_n=800\cdot2^n$ and $Q_6=800\cdot64=51\,200$. The model assumes a constant doubling factor and ignores resource limits or other changes.
25. At $n=3$, $9>8$; at $n=4$, both are 16; at $n=5$, $32>25$; at $n=6$, $64>36$. The table suggests that $2^n$ begins to exceed $n^2$ in this range, but finitely many checks cannot prove a statement for all positive integers.

## 13. Chapter summary

- Positive integer exponents represent repeated multiplication.
- For $a\ne0$, $a^0=1$ and $a^{-n}=1/a^n$ for positive integer $n$.
- In this volume, $0^0$ and $0^{-n}$ are undefined; $0^n=0$ for positive $n$.
- Exponent laws combine powers under multiplication or division of like bases, and under powers of powers, products, and quotients. Their domain restrictions must be retained.
- Parentheses determine whether a negative sign belongs to the base: $(-a)^2$ is not the same as $-a^2$.
- Normalized scientific notation has the form $a\times10^n$ with $1\le|a|<10$ and integer $n$, for nonzero numbers.
- Multiply or divide scientific-notation numbers by operating on coefficients and powers of ten; align powers of ten before addition or subtraction.
- Rounding produces an approximation. Significant figures describe reported measurement precision, not mathematical exactness.
- A repeated multiplicative change by factor $r$ over $n$ integer steps is modeled by $Q_n=Q_0r^n$ under the stated assumptions.
- If all lengths are scaled by $k$, corresponding areas scale by $k^2$ and volumes by $k^3$ for geometrically similar objects.
- Python integers and `Fraction` support exact integer-power calculations; `Decimal` supports decimal arithmetic with an explicit precision context.

## 14. References and connections

- Math-Atlas, [**Foundations 04 — Number Systems and Mathematical Structures**](../Foundations/04_Number_Systems_and_Mathematical_Structures.MD): real-number field properties used by the exponent laws.
- Math-Atlas, [**Foundations 05 — Mathematical Proof Techniques**](../Foundations/05_Mathematical_Proof_Techniques.MD): proof structure for identities and algebraic laws.
- Math-Atlas, [**Foundations 07 — Mathematical Notation and Symbols**](../Foundations/07_Mathematical_Notation_and_Symbols.MD): shared notation and symbol conventions.
- Math-Atlas, [**Algebra 02 — Real-Number Properties and Algebraic Simplification**](02_Real_Number_Properties_and_Algebraic_Simplification.MD): order of operations and exact arithmetic.
- Math-Atlas, [**Algebra 04 — Linear Inequalities and Absolute Value**](04_Linear_Inequalities_and_Absolute_Value.MD): interval and absolute-value notation used in later algebra.
- Math-Atlas, **Algebra 11 — Radicals and Rational Exponents** (planned): later extension from integer exponents to rational exponents, with domain restrictions.
- Math-Atlas, **Algebra 16 — Exponential Functions and Models** (planned): extension from integer-step multiplicative models to exponential functions.

**Next chapter:** Chapter 08 — Polynomials and Polynomial Operations.
