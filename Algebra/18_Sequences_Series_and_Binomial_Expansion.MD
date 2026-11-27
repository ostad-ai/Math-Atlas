# Algebra 18 — Sequences, Series, and Binomial Expansion

## 1. Introduction

A sequence is an ordered list of terms whose positions carry meaning. A series is the sum of terms from a sequence. This distinction is simple but fundamental: a formula for the $n$ th term does not by itself give the sum of the first $n$ terms. This chapter develops arithmetic and geometric sequences, recursive descriptions, finite and infinite geometric series, sigma notation, and the Binomial Theorem.

The chapter connects several earlier ideas. A geometric sequence is the integer-time sampling of a discrete exponential model from Chapter 16. The Binomial Theorem extends the special products studied in Chapters 08 and 09. Exact arithmetic is used whenever the data are rational; convergence statements are proved rather than inferred from numerical experiments.

### Learning objectives

By the end of this chapter, a learner should be able to:

- Distinguish a sequence from the series formed by summing its terms.
- Interpret sequence notation and state the indexing convention.
- Recognize, construct, and use arithmetic and geometric sequences.
- Move between explicit and recursive descriptions for these two sequence families.
- Derive and apply arithmetic-series and finite-geometric-series formulas.
- Determine when an infinite geometric series converges and find its sum.
- Read, evaluate, and manipulate finite sums using sigma notation.
- Construct Pascal's triangle and calculate binomial coefficients.
- State, explain, and apply the Binomial Theorem for nonnegative integer exponents.
- Use exact Python arithmetic to check finite examples while distinguishing computation from proof.

## 2. Sequences, indexing, and notation

A **sequence** is a function whose domain is an ordered set of integer indices, usually the positive integers or the nonnegative integers. In this chapter, unless a problem explicitly says otherwise, a sequence is indexed from $n=1$:

$$
a_1,a_2,a_3,\ldots
$$

The symbol $a_n$ denotes the term at position $n$. The first term is $a_1$, the second is $a_2$, and so on. A sequence may be finite, such as $(a_1,\ldots,a_N)$, or infinite.

A formula that gives $a_n$ directly in terms of $n$ is an **explicit formula**. A rule that defines later terms from earlier terms, together with enough starting values, is a **recursive definition** or **recurrence**.

A **series** is a sum of terms of a sequence. The $N$ th partial sum is

$$
S_N=\sum_{n=1}^{N}a_n=a_1+a_2+\cdots+a_N.
$$

The sequence $(a_n)$ and the series $\sum_{n=1}^{\infty}a_n$ are different objects. The sequence lists terms; the series asks about sums and, in the infinite case, the limit of partial sums.

### Example 1 — Read sequence notation

If $a_n=3n-2$ for $n\geq1$, then

$$
a_1=1,\quad a_2=4,\quad a_3=7,\quad a_4=10.
$$

The corresponding fourth partial sum is $S_4=1+4+7+10=22$. Notice that $a_4=10$ is not the same as $S_4=22$.

### 2.1 Explicit and recursive descriptions

An explicit formula describes a term directly. A recursive definition describes how to generate a term from earlier terms. A recurrence must include starting value(s); without them, it may describe many different sequences.

For example, the rules

$$
a_1=5,\qquad a_{n+1}=a_n+4
$$

define the sequence $5,9,13,17,\ldots$. The starting value determines which sequence the recurrence describes.

A recurrence can be useful even when a simple explicit formula is unavailable. The Fibonacci sequence is defined by $F_1=1$, $F_2=1$, and $F_{n+2}=F_{n+1}+F_n$ for $n\geq1$; its first terms are $1,1,2,3,5,8,\ldots$.

## 3. Arithmetic sequences

A sequence is **arithmetic** when the difference between consecutive terms is constant. This constant is the **common difference** $d$:

$$
a_{n+1}-a_n=d.
$$

Starting with $a_1$, each new term is obtained by adding $d$. Thus

$$
a_2=a_1+d,\quad a_3=a_1+2d,\quad a_4=a_1+3d.
$$

In general,

$$
\boxed{a_n=a_1+(n-1)d.}
$$

**Derivation.** To reach term $n$ from term $1$, exactly $n-1$ common differences are added. This gives $a_n=a_1+(n-1)d$.

If $d>0$, the sequence is increasing; if $d<0$, it is decreasing; if $d=0$, it is constant. These statements describe the terms as the index increases.

### Example 2 — Find an arithmetic term

An arithmetic sequence begins with $a_1=7$ and has common difference $d=3$. Its twelfth term is

$$
a_{12}=7+(12-1)3=40.
$$

### Example 3 — Recover the common difference

An arithmetic sequence has $a_4=17$ and $a_{10}=41$. Since

$$
a_{10}-a_4=(10-4)d,
$$
we get $24=6d$, so $d=4$. Then $a_1=a_4-3d=5$.

### 3.1 Arithmetic sequences and linear functions

The formula $a_n=a_1+(n-1)d$ is linear in the index $n$. If the index is treated as a real input, the corresponding line has slope $d$. The sequence itself is defined only at its allowed integer indices; a line through its plotted points is a useful representation, not a change in its discrete domain.

## 4. Arithmetic series

The sum of the first $N$ terms of an arithmetic sequence is an **arithmetic series**. Pairing the first and last terms gives

$$
S_N=a_1+a_2+\cdots+a_N.
$$

Write the same sum in reverse order:

$$
S_N=a_N+a_{N-1}+\cdots+a_1.
$$

Adding term by term gives $2S_N=N(a_1+a_N)$, because each of the $N$ pairs has sum $a_1+a_N$. Hence

$$
\boxed{S_N=\frac{N}{2}(a_1+a_N).}
$$

Substituting $a_N=a_1+(N-1)d$ gives the equivalent form

$$
\boxed{S_N=\frac{N}{2}\bigl(2a_1+(N-1)d\bigr).}
$$

The formula is valid for every positive integer $N$, including a decreasing arithmetic sequence.

### Example 4 — Sum an arithmetic sequence

Find the sum of the first seven terms of $4,7,10,13,\ldots$. Here $a_1=4$, $d=3$, and

$$
a_7=4+6(3)=22.
$$

Therefore

$$
S_7=\frac72(4+22)=91.
$$

### Example 5 — Determine how many terms are used

An arithmetic sequence begins at $12$ and has common difference $-2$. The term $-18$ occurs when

$$
-18=12+(n-1)(-2),
$$
so $n=16$. The sum through that term is

$$
S_{16}=\frac{16}{2}(12-18)=-48.
$$

## 5. Geometric sequences

A sequence is **geometric** when the ratio of each term to the preceding term is a constant $r$, provided the preceding term is nonzero when the ratio is formed. The recurrence form is

$$
a_{n+1}=ra_n.
$$

Starting from $a_1$, repeated multiplication gives

$$
a_2=a_1r,\quad a_3=a_1r^2,\quad a_4=a_1r^3,
$$
so the explicit formula is

$$
\boxed{a_n=a_1r^{n-1}.}
$$

The recurrence definition remains meaningful when a term is zero. If $a_1=0$, every term is zero for any chosen multiplier $r$. If a later term is zero, all following terms are zero. In such cases, a ratio computed by dividing by a zero term is not defined; use the recurrence or explicit formula rather than attempting that quotient.

The sign and size of $r$ determine the pattern:

- $r>1$: positive starting values grow in magnitude and stay positive.
- $0<r<1$: positive starting values decrease toward zero.
- $r<0$: nonzero terms alternate sign.
- $r=1$: the sequence is constant.
- $r=0$: every term after the first is zero.

### Example 6 — Find a geometric term

For $a_1=3$ and $r=2$,

$$
a_8=3\cdot2^7=384.
$$

### Example 7 — Find a ratio from two terms

A geometric sequence has $a_2=6$ and $a_5=162$. Then $a_5/a_2=r^3=27$, so $r=3$. Therefore $a_1=2$.

### Example 8 — A negative common ratio

For $a_1=16$ and $r=-1/2$, the first five terms are

$$
16,-8,4,-2,1.
$$

The sign alternates, while the magnitude is multiplied by $1/2$ at each step.

## 6. Finite geometric series

For a geometric sequence with first term $a_1$ and ratio $r$, the sum of its first $N$ terms is

$$
S_N=a_1+a_1r+a_1r^2+\cdots+a_1r^{N-1}.
$$

If $r\ne1$, multiply by $r$ and subtract:

$$
\begin{aligned}
S_N&=a_1+a_1r+\cdots+a_1r^{N-1},\\
rS_N&=a_1r+a_1r^2+\cdots+a_1r^N.
\end{aligned}
$$

All middle terms cancel, leaving $(1-r)S_N=a_1(1-r^N)$. Thus

$$
\boxed{S_N=a_1\frac{1-r^N}{1-r}\quad(r\ne1).}
$$

When $r=1$, every term equals $a_1$, so $S_N=Na_1$. This separate case avoids division by zero.

### Example 9 — Sum a finite geometric series

For $a_1=2$, $r=3$, and $N=5$,

$$
S_5=2\frac{1-3^5}{1-3}=242.
$$

### Example 10 — A ratio between zero and one

The sum of the first four terms of $80,40,20,10,\ldots$ is

$$
S_4=80\frac{1-(1/2)^4}{1-1/2}=150.
$$

## 7. Infinite geometric series and convergence

An infinite series is defined through its sequence of partial sums. The series

$$
\sum_{n=1}^{\infty}a_n
$$
**converges** to $L$ if the sequence of partial sums $S_N$ approaches the finite limit $L$ as $N\to\infty$. If no finite limit exists, the series diverges.

For a geometric series with first term $a_1$ and ratio $r$, the $N$ th partial sum for $r\ne1$ is

$$
S_N=a_1\frac{1-r^N}{1-r}.
$$

If $|r|<1$, then $r^N\to0$. Therefore

$$
\boxed{\sum_{n=1}^{\infty}a_1r^{n-1}=\frac{a_1}{1-r}\quad\text{when }|r|<1.}
$$

This is the infinite geometric-series formula.

### Why the condition matters

If $a_1\ne0$ and $|r|\geq1$, the terms $a_1r^{n-1}$ do not approach zero. A necessary condition for any series to converge is that its terms approach zero, so the geometric series diverges in this case. In particular:

- If $r=1$, the partial sums are $Na_1$ and do not approach a finite limit when $a_1\ne0$.
- If $r=-1$, the partial sums alternate between two values when $a_1\ne0$.
- If $|r|>1$, the magnitude of the terms grows and does not approach zero.

There is one harmless special case: if $a_1=0$, every term is zero, so the series converges to zero for every real $r$. The usual condition $|r|<1$ is the condition for a nonzero geometric series to converge.

### Example 11 — Find an infinite geometric sum

For $a_1=6$ and $r=1/3$, $|r|<1$, so

$$
S=\frac{6}{1-1/3}=9.
$$

### Example 12 — An alternating convergent series

For $a_1=4$ and $r=-1/2$,

$$
S=\frac{4}{1-(-1/2)}=\frac83.
$$

The terms alternate in sign, but their magnitudes approach zero quickly enough for the partial sums to converge.

### Example 13 — Recognize divergence

The series $5-5+5-5+\cdots$ has $r=-1$. Its partial sums alternate between $5$ and $0$, so they have no limit. The series diverges even though its terms remain bounded.

## 8. Recursive sequences and modeling

A recursive rule is especially useful when a process is described step by step. Arithmetic and geometric sequences are important examples:

- Arithmetic: $a_1=c$ and $a_{n+1}=a_n+d$.
- Geometric: $a_1=c$ and $a_{n+1}=ra_n$.

An arithmetic recurrence represents a fixed additive change. A geometric recurrence represents a fixed multiplicative change. This is the discrete distinction developed in Chapter 16: a geometric sequence with $a_1=A_0$ is the sequence of values $A_n=A_0r^{n-1}$, or $A_n=A_0b^n$ if the indexing is shifted to begin at $n=0$.

### Example 14 — Compare additive and multiplicative change

A savings plan receives a fixed deposit of 25 units at the end of each week, starting from zero. The amount after $n$ deposits is $25n$, an arithmetic pattern. By contrast, an account whose balance is multiplied by $1.02$ every month follows a geometric pattern $A_n=A_0(1.02)^n$ when $A_0$ is the balance before the first monthly update.

### Example 15 — Generate a recursive sequence

The Fibonacci recurrence starts with $F_1=1$ and $F_2=1$. For $n\geq1$, $F_{n+2}=F_{n+1}+F_n$. A short loop produces a finite list:

```python
first, second = 1, 1
terms = [first, second]
for _ in range(8):
    first, second = second, first + second
    terms.append(second)
print(terms)
```

This prints the first ten terms. The program generates terms; it does not prove a general formula for them.

## 9. Sigma notation

The Greek capital letter sigma, $\Sigma$, represents a finite sum. For example,

$$
\sum_{k=1}^{5}(2k-1)=1+3+5+7+9=25.
$$

The index $k$ is a **dummy index**: its name can be changed without changing the sum, provided the expression and bounds are changed consistently. Thus

$$
\sum_{k=1}^{N}a_k=\sum_{j=1}^{N}a_j.
$$

The lower and upper bounds specify which integer values are used. A sum with lower bound larger than upper bound is the empty sum, conventionally equal to zero.

### 9.1 Basic summation rules

For finite sums with matching bounds,

$$
\sum_{k=m}^{n}(a_k+b_k)=\sum_{k=m}^{n}a_k+\sum_{k=m}^{n}b_k,
$$

and for a constant $c$,

$$
\sum_{k=m}^{n}ca_k=c\sum_{k=m}^{n}a_k.
$$

A constant summed over $N$ indices satisfies

$$
\sum_{k=1}^{N}c=Nc.
$$

Changing an index requires changing the expression and bounds together. For example, setting $j=k+1$ gives

$$
\sum_{k=0}^{N-1}a_{k+1}=\sum_{j=1}^{N}a_j.
$$

### Example 16 — Evaluate a sum of squares

$$
\sum_{k=1}^{4}k^2=1^2+2^2+3^2+4^2=30.
$$

### Example 17 — Separate a sum

$$
\sum_{k=1}^{5}(3k+2)=3\sum_{k=1}^{5}k+\sum_{k=1}^{5}2
=3(15)+5(2)=55.
$$

## 10. Binomial coefficients and Pascal's triangle

For integers $n\geq0$ and $0\leq k\leq n$, the **binomial coefficient** is

$$
\binom{n}{k}=\frac{n!}{k!(n-k)!}.
$$

It counts the number of ways to choose $k$ objects from $n$ distinct objects when order does not matter. The endpoint values are $\binom n0=\binom nn=1$. For $0<k<n$, the coefficients satisfy Pascal's identity:

$$
\boxed{\binom nk=\binom{n-1}{k-1}+\binom{n-1}{k}.}
$$

The identity follows by separating selections into those that include a chosen final object and those that do not. It also follows algebraically from the factorial definition.

Pascal's triangle begins:

| $n$ | Binomial coefficients $\binom nk$ from $k=0$ to $k=n$ |
|---:|---|
| 0 | 1 |
| 1 | 1, 1 |
| 2 | 1, 2, 1 |
| 3 | 1, 3, 3, 1 |
| 4 | 1, 4, 6, 4, 1 |
| 5 | 1, 5, 10, 10, 5, 1 |

Each interior entry is the sum of the two entries directly above it. The first and last entries in each row are 1.

## 11. The Binomial Theorem

For any two commuting quantities $a$ and $b$, and any nonnegative integer $n$,

$$
\boxed{(a+b)^n=\sum_{k=0}^{n}\binom nk a^{n-k}b^k.}
$$

The theorem gives a finite expansion. The exponent $n$ must be a nonnegative integer in this statement. Negative and noninteger exponents lead to different, generally infinite expansions under additional conditions; those are not part of this finite Binomial Theorem.

### Why the coefficients appear

For $n=1$, the identity is immediate. Suppose the formula holds for $n$. Multiply the expansion by $(a+b)$:

$$
(a+b)^{n+1}=(a+b)\sum_{k=0}^{n}\binom nk a^{n-k}b^k.
$$

After distributing, the coefficient of $a^{n+1-j}b^j$ is the sum $\binom nj+\binom n{j-1}$ for an interior index $j$. Pascal's identity makes this coefficient $\binom{n+1}{j}$. The endpoint coefficients are 1. Thus the formula holds for $n+1$. By induction, it holds for every nonnegative integer $n$.

### Example 18 — Expand a fourth power

Using the row $1,4,6,4,1$ of Pascal's triangle,

$$
(a+b)^4=a^4+4a^3b+6a^2b^2+4ab^3+b^4.
$$

### Example 19 — Expand a difference

Write $x-2$ as $x+(-2)$. Then

$$
\begin{aligned}
(x-2)^5={}&x^5+5x^4(-2)+10x^3(-2)^2\\
&+10x^2(-2)^3+5x(-2)^4+(-2)^5\\
={}&x^5-10x^4+40x^3-80x^2+80x-32.
\end{aligned}
$$

The alternating signs come from the powers of the negative term; they are not a separate rule to memorize.

### Example 20 — Find one coefficient without expanding everything

The coefficient of $x^4y^3$ in $(2x-y)^7$ corresponds to $k=3$:

$$
\binom73(2x)^4(-y)^3=35\cdot16\cdot(-1)x^4y^3.
$$

Therefore the coefficient is $-560$.

### Example 21 — A numerical binomial identity

For $a=2$, $b=3$, and $n=4$,

$$
2^4+4(2^3)(3)+6(2^2)(3^2)+4(2)(3^3)+3^4=625=5^4.
$$

The example illustrates the theorem; the induction proof establishes it for all allowed $n$.

## 12. Computational exploration with exact arithmetic

The self-contained Python implementation in the example below provides exact arithmetic for common sequence and series calculations with integers and `Fraction`. It includes arithmetic and geometric terms, finite sums, infinite geometric sums when convergence conditions hold, Pascal rows, and binomial expansion terms.

The module is intentionally limited. It does not prove a sequence is arithmetic or geometric from arbitrary data, sum an arbitrary infinite series, or symbolically simplify arbitrary expressions. A numerical pattern is not proof of a general formula.

### Example 22 — Exact arithmetic and a finite geometric sum

```python
from __future__ import annotations

# --- Inlined implementation: sequences_core ---
"""Exact sequence, series, and binomial helpers for Math-Atlas Algebra, Chapter 18.

The helpers use integers and fractions only. They are educational utilities, not a
symbolic sequence-recognition system or a general infinite-series engine.
"""


from fractions import Fraction
from math import comb
from typing import TypeAlias

ExactRational: TypeAlias = int | Fraction


def _fraction(value: ExactRational, name: str) -> Fraction:
    if isinstance(value, bool) or not isinstance(value, (int, Fraction)):
        raise TypeError(f"{name} must be an int or Fraction; floats are not accepted")
    return Fraction(value)


def _positive_int(value: int, name: str) -> int:
    if isinstance(value, bool) or not isinstance(value, int):
        raise TypeError(f"{name} must be an integer")
    if value <= 0:
        raise ValueError(f"{name} must be positive")
    return value


def _nonnegative_int(value: int, name: str) -> int:
    if isinstance(value, bool) or not isinstance(value, int):
        raise TypeError(f"{name} must be an integer")
    if value < 0:
        raise ValueError(f"{name} must be nonnegative")
    return value


def _index(value: int, name: str) -> int:
    """Validate a nonnegative integer index (supporting both n=0 and n=1)."""
    return _nonnegative_int(value, name)


def arithmetic_term(
    first: ExactRational,
    difference: ExactRational,
    n: int,
    *,
    start_index: int = 1,
) -> Fraction:
    """Return the term at index n; ``first`` is the term at ``start_index``."""
    a = _fraction(first, "first")
    d = _fraction(difference, "difference")
    start = _index(start_index, "start_index")
    index = _index(n, "n")
    if index < start:
        raise ValueError("n must be greater than or equal to start_index")
    return a + (index - start) * d


def geometric_term(
    first: ExactRational,
    ratio: ExactRational,
    n: int,
    *,
    start_index: int = 1,
) -> Fraction:
    """Return a geometric term; ``first`` is the term at ``start_index``."""
    a = _fraction(first, "first")
    r = _fraction(ratio, "ratio")
    start = _index(start_index, "start_index")
    index = _index(n, "n")
    if index < start:
        raise ValueError("n must be greater than or equal to start_index")
    return a * r ** (index - start)


def arithmetic_sequence(
    first: ExactRational, difference: ExactRational, terms: int
) -> tuple[Fraction, ...]:
    """Generate a finite arithmetic sequence of the requested positive length."""
    a = _fraction(first, "first")
    d = _fraction(difference, "difference")
    count = _positive_int(terms, "terms")
    return tuple(a + i * d for i in range(count))


def geometric_sequence(
    first: ExactRational, ratio: ExactRational, terms: int
) -> tuple[Fraction, ...]:
    """Generate a finite geometric sequence of the requested positive length."""
    a = _fraction(first, "first")
    r = _fraction(ratio, "ratio")
    count = _positive_int(terms, "terms")
    return tuple(a * r**i for i in range(count))


def arithmetic_sum(
    first: ExactRational, difference: ExactRational, terms: int
) -> Fraction:
    """Return the sum of the first ``terms`` arithmetic-sequence terms exactly."""
    a = _fraction(first, "first")
    d = _fraction(difference, "difference")
    count = _positive_int(terms, "terms")
    last = a + (count - 1) * d
    return Fraction(count, 2) * (a + last)


def geometric_sum(
    first: ExactRational, ratio: ExactRational, terms: int
) -> Fraction:
    """Return the sum of the first ``terms`` geometric-sequence terms exactly."""
    a = _fraction(first, "first")
    r = _fraction(ratio, "ratio")
    count = _positive_int(terms, "terms")
    if r == 1:
        return count * a
    return a * (1 - r**count) / (1 - r)


def infinite_geometric_sum(first: ExactRational, ratio: ExactRational) -> Fraction:
    """Return an infinite geometric sum when it converges.

    If the first term is zero, every term is zero and the sum is zero for any
    finite rational ratio. Otherwise convergence requires abs(ratio) < 1.
    """
    a = _fraction(first, "first")
    r = _fraction(ratio, "ratio")
    if a == 0:
        return Fraction(0)
    if abs(r) >= 1:
        raise ValueError("a nonzero infinite geometric series converges only when |ratio| < 1")
    return a / (1 - r)


def binomial_coefficients(n: int) -> tuple[int, ...]:
    """Return C(n,0), ..., C(n,n) for a nonnegative integer n."""
    degree = _nonnegative_int(n, "n")
    return tuple(comb(degree, k) for k in range(degree + 1))


def pascal_row(n: int) -> tuple[int, ...]:
    """Return row n of Pascal's triangle (row zero is (1,))."""
    return binomial_coefficients(n)


def binomial_terms(
    a: ExactRational, b: ExactRational, n: int
) -> tuple[Fraction, ...]:
    """Return the exact ordered terms of (a+b)**n for rational a and b.

    The returned entries are C(n,k)*a**(n-k)*b**k for k=0,...,n.
    """
    left = _fraction(a, "a")
    right = _fraction(b, "b")
    degree = _nonnegative_int(n, "n")
    return tuple(
        Fraction(comb(degree, k)) * left ** (degree - k) * right**k
        for k in range(degree + 1)
    )


def binomial_value(a: ExactRational, b: ExactRational, n: int) -> Fraction:
    """Evaluate (a+b)**n exactly for rational inputs and n >= 0."""
    left = _fraction(a, "a")
    right = _fraction(b, "b")
    degree = _nonnegative_int(n, "n")
    return (left + right) ** degree

# --- Chapter example ---
geometric_sum = geometric_sum
infinite_geometric_sum = infinite_geometric_sum

from fractions import Fraction


finite = geometric_sum(Fraction(3, 2), Fraction(1, 3), 4)
infinite = infinite_geometric_sum(Fraction(3, 2), Fraction(1, 3))
print(finite)    # 20/9
print(infinite) # 9/4
```

### Example 23 — Check a binomial expansion exactly

```python
from __future__ import annotations

# --- Inlined implementation: sequences_core ---
"""Exact sequence, series, and binomial helpers for Math-Atlas Algebra, Chapter 18.

The helpers use integers and fractions only. They are educational utilities, not a
symbolic sequence-recognition system or a general infinite-series engine.
"""


from fractions import Fraction
from math import comb
from typing import TypeAlias

ExactRational: TypeAlias = int | Fraction


def _fraction(value: ExactRational, name: str) -> Fraction:
    if isinstance(value, bool) or not isinstance(value, (int, Fraction)):
        raise TypeError(f"{name} must be an int or Fraction; floats are not accepted")
    return Fraction(value)


def _positive_int(value: int, name: str) -> int:
    if isinstance(value, bool) or not isinstance(value, int):
        raise TypeError(f"{name} must be an integer")
    if value <= 0:
        raise ValueError(f"{name} must be positive")
    return value


def _nonnegative_int(value: int, name: str) -> int:
    if isinstance(value, bool) or not isinstance(value, int):
        raise TypeError(f"{name} must be an integer")
    if value < 0:
        raise ValueError(f"{name} must be nonnegative")
    return value


def _index(value: int, name: str) -> int:
    """Validate a nonnegative integer index (supporting both n=0 and n=1)."""
    return _nonnegative_int(value, name)


def arithmetic_term(
    first: ExactRational,
    difference: ExactRational,
    n: int,
    *,
    start_index: int = 1,
) -> Fraction:
    """Return the term at index n; ``first`` is the term at ``start_index``."""
    a = _fraction(first, "first")
    d = _fraction(difference, "difference")
    start = _index(start_index, "start_index")
    index = _index(n, "n")
    if index < start:
        raise ValueError("n must be greater than or equal to start_index")
    return a + (index - start) * d


def geometric_term(
    first: ExactRational,
    ratio: ExactRational,
    n: int,
    *,
    start_index: int = 1,
) -> Fraction:
    """Return a geometric term; ``first`` is the term at ``start_index``."""
    a = _fraction(first, "first")
    r = _fraction(ratio, "ratio")
    start = _index(start_index, "start_index")
    index = _index(n, "n")
    if index < start:
        raise ValueError("n must be greater than or equal to start_index")
    return a * r ** (index - start)


def arithmetic_sequence(
    first: ExactRational, difference: ExactRational, terms: int
) -> tuple[Fraction, ...]:
    """Generate a finite arithmetic sequence of the requested positive length."""
    a = _fraction(first, "first")
    d = _fraction(difference, "difference")
    count = _positive_int(terms, "terms")
    return tuple(a + i * d for i in range(count))


def geometric_sequence(
    first: ExactRational, ratio: ExactRational, terms: int
) -> tuple[Fraction, ...]:
    """Generate a finite geometric sequence of the requested positive length."""
    a = _fraction(first, "first")
    r = _fraction(ratio, "ratio")
    count = _positive_int(terms, "terms")
    return tuple(a * r**i for i in range(count))


def arithmetic_sum(
    first: ExactRational, difference: ExactRational, terms: int
) -> Fraction:
    """Return the sum of the first ``terms`` arithmetic-sequence terms exactly."""
    a = _fraction(first, "first")
    d = _fraction(difference, "difference")
    count = _positive_int(terms, "terms")
    last = a + (count - 1) * d
    return Fraction(count, 2) * (a + last)


def geometric_sum(
    first: ExactRational, ratio: ExactRational, terms: int
) -> Fraction:
    """Return the sum of the first ``terms`` geometric-sequence terms exactly."""
    a = _fraction(first, "first")
    r = _fraction(ratio, "ratio")
    count = _positive_int(terms, "terms")
    if r == 1:
        return count * a
    return a * (1 - r**count) / (1 - r)


def infinite_geometric_sum(first: ExactRational, ratio: ExactRational) -> Fraction:
    """Return an infinite geometric sum when it converges.

    If the first term is zero, every term is zero and the sum is zero for any
    finite rational ratio. Otherwise convergence requires abs(ratio) < 1.
    """
    a = _fraction(first, "first")
    r = _fraction(ratio, "ratio")
    if a == 0:
        return Fraction(0)
    if abs(r) >= 1:
        raise ValueError("a nonzero infinite geometric series converges only when |ratio| < 1")
    return a / (1 - r)


def binomial_coefficients(n: int) -> tuple[int, ...]:
    """Return C(n,0), ..., C(n,n) for a nonnegative integer n."""
    degree = _nonnegative_int(n, "n")
    return tuple(comb(degree, k) for k in range(degree + 1))


def pascal_row(n: int) -> tuple[int, ...]:
    """Return row n of Pascal's triangle (row zero is (1,))."""
    return binomial_coefficients(n)


def binomial_terms(
    a: ExactRational, b: ExactRational, n: int
) -> tuple[Fraction, ...]:
    """Return the exact ordered terms of (a+b)**n for rational a and b.

    The returned entries are C(n,k)*a**(n-k)*b**k for k=0,...,n.
    """
    left = _fraction(a, "a")
    right = _fraction(b, "b")
    degree = _nonnegative_int(n, "n")
    return tuple(
        Fraction(comb(degree, k)) * left ** (degree - k) * right**k
        for k in range(degree + 1)
    )


def binomial_value(a: ExactRational, b: ExactRational, n: int) -> Fraction:
    """Evaluate (a+b)**n exactly for rational inputs and n >= 0."""
    left = _fraction(a, "a")
    right = _fraction(b, "b")
    degree = _nonnegative_int(n, "n")
    return (left + right) ** degree

# --- Chapter example ---
binomial_terms = binomial_terms
binomial_value = binomial_value

from fractions import Fraction


terms = binomial_terms(Fraction(1, 2), Fraction(1, 3), 4)
print(terms)
print(sum(terms, Fraction(0)) == binomial_value(Fraction(1, 2), Fraction(1, 3), 4))
```

The equality check verifies this particular input. It is not a proof of the Binomial Theorem; the induction argument in Section 11 supplies the proof.

## 13. Common errors and cautions

- **Confusing a term with a partial sum:** $a_N$ is the $N$ th term; $S_N$ is the sum of the first $N$ terms.
- **Off-by-one indexing:** the formula $a_n=a_1+(n-1)d$ uses indexing from $1$. If indexing begins at $0$, write the formula consistently, such as $a_n=a_0+nd$.
- **Calling every pattern arithmetic or geometric:** constant differences indicate arithmetic structure; constant ratios indicate geometric structure, and a ratio test must not divide by zero.
- **Using the geometric-sum formula at $r=1$:** use $S_N=Na_1$ instead.
- **Summing an infinite geometric series when $|r|\geq1$:** a nonzero series diverges; the finite formula does not give an infinite sum in that case.
- **Assuming bounded terms imply convergence:** the alternating series with ratio $-1$ is bounded term by term but its partial sums do not converge.
- **Dropping a sigma bound or changing only the index letter:** a reindexing must transform the summand and bounds together.
- **Using the Binomial Theorem for arbitrary real exponents:** the finite formula stated here requires a nonnegative integer exponent.
- **Using positive signs for every term in $(a-b)^n$:** the negative signs are generated by powers of $-b$.
- **Treating computation as proof:** checking selected values can reveal errors but does not establish a universal identity.

## 14. Exercises

### A. Sequence recognition and explicit formulas

1. Determine whether $4,9,14,19,\ldots$ is arithmetic or geometric. State the common difference or ratio and give an explicit formula.
2. Determine whether $81,27,9,3,\ldots$ is arithmetic or geometric. Give an explicit formula.
3. An arithmetic sequence has $a_1=-5$ and $d=4$. Find $a_{18}$.
4. An arithmetic sequence has $a_3=11$ and $a_8=31$. Find $a_1$ and $d$.
5. A geometric sequence has $a_1=5$ and $r=-2$. Find the first six terms and $a_9$.
6. A geometric sequence has $a_2=12$ and $a_5=324$. Find the real common ratio and $a_1$.

### B. Finite sums and recurrences

7. Find the sum of the first 20 terms of $3,7,11,15,\ldots$.
8. An arithmetic sequence has first term 18 and common difference $-3$. How many terms occur through the term $-18$? Find their sum.
9. Find the sum of the first 6 terms of $2,6,18,54,\ldots$.
10. Find the sum of the first 8 terms of $100,50,25,\ldots$.
11. A recurrence is defined by $a_1=7$ and $a_{n+1}=a_n-2$. List the first five terms and give an explicit formula.
12. A recurrence is defined by $g_1=3$ and $g_{n+1}=4g_n$. Give an explicit formula and find $g_6$.

### C. Infinite geometric series

13. Determine whether $12+6+3+\cdots$ converges. If it does, find its sum.
14. Determine whether $5-10+20-40+\cdots$ converges. Explain using the ratio.
15. Find the sum of $9-3+1-\frac13+\cdots$.
16. An infinite geometric series has first term zero and ratio $4$. Does it converge? Explain why this does not contradict the usual nonzero-series condition.

### D. Sigma notation

17. Expand and evaluate $\sum_{k=1}^{5}(3k-1)$.
18. Evaluate $\sum_{j=0}^{3}(j+2)^2$.
19. Rewrite $\sum_{k=0}^{N-1}a_{k+1}$ using an index that begins at 1.
20. Use summation rules to evaluate $\sum_{k=1}^{6}(2k+5)$.

### E. Binomial coefficients and expansion

21. Write the sixth row of Pascal's triangle and state $\binom63$.
22. Expand $(x+3)^4$.
23. Find the coefficient of $x^2y^4$ in $(3x-2y)^6$ without writing every term.
24. Use the Binomial Theorem to verify $(1+2)^5=243$. Identify why the exponent condition is satisfied.

## 15. Selected answers

1. Arithmetic, $d=5$, $a_n=4+5(n-1)=5n-1$.
2. Geometric, $r=1/3$, $a_n=81(1/3)^{n-1}$.
3. $a_{18}=-5+17(4)=63$.
4. $d=(31-11)/(8-3)=4$ and $a_1=11-2(4)=3$.
5. $5,-10,20,-40,80,-160$; $a_9=5(-2)^8=1280$.
6. $r^3=324/12=27$, so the real ratio is $r=3$ and $a_1=4$.
7. $a_{20}=3+19(4)=79$ and $S_{20}=10(3+79)=820$.
8. $-18=18+(n-1)(-3)$ gives $n=13$; $S_{13}=13(18-18)/2=0$.
9. $S_6=2(3^6-1)/(3-1)=728$.
10. $S_8=100(1-(1/2)^8)/(1-1/2)=6375/32=199.21875$.
11. $7,5,3,1,-1$; $a_n=7-2(n-1)$.
12. $g_n=3\cdot4^{n-1}$ and $g_6=3072$.
13. Converges because $r=1/2$; sum $12/(1-1/2)=24$.
14. Diverges because $r=-2$ and $|r|>1$; its terms do not approach zero.
15. Converges because $r=-1/3$; sum $9/(1+1/3)=27/4$.
16. It converges to zero because every term is zero, regardless of the ratio assigned in the recurrence.
17. $2+5+8+11+14=40$.
18. $4+9+16+25=54$.
19. $\sum_{j=1}^{N}a_j$.
20. $2\sum_{k=1}^{6}k+5(6)=42+30=72$.
21. $1,6,15,20,15,6,1$; $\binom63=20$.
22. $x^4+12x^3+54x^2+108x+81$.
23. The $y^4$ term corresponds to $k=4$: $\binom64(3x)^2(-2y)^4=15\cdot9\cdot16x^2y^4$, so the coefficient is $2160$.
24. $1+5(2)+10(2^2)+10(2^3)+5(2^4)+2^5=243$. The exponent $5$ is a nonnegative integer, as required.

## 16. Chapter summary

A sequence is an indexed list of terms; a series is a sum of terms, and an infinite series converges only when its partial sums approach a finite limit. Arithmetic sequences have constant differences and satisfy $a_n=a_1+(n-1)d$. Their first-$N$ sum is $N(a_1+a_N)/2$. Geometric sequences multiply by a constant ratio and satisfy $a_n=a_1r^{n-1}$. Their finite sum has a separate case for $r=1$; a nonzero infinite geometric series converges exactly when $|r|<1$, with sum $a_1/(1-r)$. Sigma notation compactly represents finite sums. Binomial coefficients satisfy Pascal's identity, and the Binomial Theorem expands $(a+b)^n$ for nonnegative integer $n$. Exact computation helps check examples but does not replace the proofs.
## 17. References and further reading

- Math-Atlas Foundations, Chapter 05 — Mathematical Proof Techniques.
- Math-Atlas Foundations, Chapter 07 — Mathematical Notation and Symbols.
- Math-Atlas Algebra, Chapter 07 — Exponents and Scientific Notation.
- Math-Atlas Algebra, Chapter 08 — Polynomials and Polynomial Operations.
- Math-Atlas Algebra, Chapter 16 — Exponential Functions and Models.
- OpenStax, *College Algebra 2e*, sections on sequences, arithmetic and geometric series, and the Binomial Theorem.

**Next chapter:** Chapter 19 — Nonlinear Systems and Inequalities.
