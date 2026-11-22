# Algebra 04 — Linear Inequalities and Absolute Value

## 1. Introduction

An equation asks where two expressions are equal. An inequality asks where one expression is less than, at most, greater than, or at least another. Its solution is therefore usually a set of numbers rather than a single number. This chapter develops linear inequalities in one real variable, compound inequalities, interval notation, and equations and inequalities involving absolute value.

The default domain in this chapter is $\mathbb{R}$. When a problem restricts the variable to integers, nonnegative values, or another domain $D$, intersect the real solution set with that domain. The order properties used below are those of the ordered field $\mathbb{R}$, as established in Foundations, Chapter 04.

### Learning objectives

After studying this chapter, you should be able to:

- Define an inequality's solution set over a stated domain.
- Identify which transformations preserve an inequality and when its direction must reverse.
- Solve one-variable linear inequalities, including those with rational coefficients.
- Write solution sets in interval notation and represent them on a number line.
- Translate compound inequalities using intersection and union.
- Interpret absolute value as distance and use its basic properties.
- Solve absolute-value equations and inequalities without losing or adding solutions.
- Use exact rational arithmetic in Python to test membership in intervals.

## 2. Inequalities and solution sets

Let $D\subseteq\mathbb{R}$ be the domain of $x$, and let $L(x)$ and $R(x)$ be real-valued expressions defined on $D$. The inequality $L(x) \mathrel{<} R(x)$ has solution set

$$
S_D = \{x \in D \mid L(x) \mathrel{<} R(x)\}.
$$

The set-builder notation means that $S_D$ contains exactly those values of $x$ in the domain $D$ for which the inequality is true. The vertical bar means “such that.”

The symbols have the following meanings:

| Symbol | Meaning | Endpoint included? |
|---|---|---|
| $ \mathrel{<} $ | strictly less than | No |
| $\leq$ | less than or equal to | Yes |
| $ \mathrel{>} $ | strictly greater than | No |
| $\geq$ | greater than or equal to | Yes |

For example, over $\mathbb{R}$, the solution set of $x \mathrel{<} 3$ contains every real number to the left of 3, but not 3 itself. The solution set of $x\leq3$ also contains 3.

An inequality is not an equation: its solution set may be an interval, a union of intervals, a single point, the empty set, or the entire domain. The form of the answer depends on the inequality and on the domain.

## 3. Transformations that preserve or reverse an inequality

The key solving rules follow from the order properties of the real numbers. Let $a,b,c\in\mathbb{R}$.

### 3.1 Adding or subtracting the same quantity

Adding the same real number to both sides preserves the direction and the truth of an inequality:

$$
a \mathrel{<} b \quad\Longleftrightarrow\quad a+c \mathrel{<} b+c.
$$

The reverse implication follows by adding $-c$ to both sides. The same rule holds for $\leq$, $\mathrel{>}$, and $\geq$. Subtracting a quantity is simply adding its additive inverse.

### 3.2 Multiplying or dividing by a positive number

If $c \mathrel{>} 0$, multiplication preserves the direction:

$$
a \mathrel{<} b \quad\Longleftrightarrow\quad ac \mathrel{<} bc \qquad(c \mathrel{>} 0).
$$

Division by a positive number also preserves the direction:

$$
a \mathrel{<} b \quad\Longleftrightarrow\quad \frac{a}{c} \mathrel{<} \frac{b}{c} \qquad(c \mathrel{>} 0).
$$

This is because division by $c$ is multiplication by its positive reciprocal $1/c$. The same rules hold for $\leq$, $\mathrel{>}$, and $\geq$.

### 3.3 Multiplying or dividing by a negative number

If $c \mathrel{<} 0$, multiplication reverses the direction:

$$
a \mathrel{<} b \quad\Longleftrightarrow\quad ac \mathrel{>} bc \qquad(c \mathrel{<} 0).
$$

Division by a negative number also reverses the direction:

$$
a \mathrel{<} b \quad\Longleftrightarrow\quad \frac{a}{c} \mathrel{>} \frac{b}{c} \qquad(c \mathrel{<} 0).
$$

**Why does the direction reverse?** Since $c \mathrel{<} 0$, the number $-c$ is positive. Thus $a \mathrel{<} b$ implies $(-c)a \mathrel{<} (-c)b$. Multiplying both sides of this last inequality by $-1$ reverses the order, giving $ca \mathrel{>} cb$. The reverse implication follows by multiplying by the negative reciprocal $1/c$.

For example, dividing both sides of

$$
-4x\leq12
$$

by $-4$ reverses the inequality and gives

$$
x\geq-3,
$$

not $x\leq-3$. The same direction-reversal rule holds for $\leq$ and $\geq$.

### 3.4 Multiplication by zero and by an expression of unknown sign

Multiplication by zero is not an equivalence-preserving operation. For a strict inequality it may turn a true statement into a false one; for a non-strict inequality it may erase all information. It must not be used as a solving step.

Do not multiply or divide an inequality by an expression whose sign is unknown without first analyzing that sign. For instance, the direction of an inequality cannot be chosen safely when multiplying both sides by $x$ unless the sign of $x$ is known. Split into the cases $x \mathrel{>} 0$, $x=0$, and $x \mathrel{<} 0$, or use another method that avoids the sign-unknown operation.

### 3.5 A quick rule table

| Operation on both sides | Condition | Direction |
|---|---|---|
| Add or subtract $c$ | Any real $c$ | Unchanged |
| Multiply or divide by $c$ | $c \mathrel{>} 0$ | Unchanged |
| Multiply or divide by $c$ | $c \mathrel{<} 0$ | Reversed |
| Multiply or divide by $c$ | $c=0$ | Not an equivalent transformation |
| Multiply or divide by $g(x)$ | Sign not established | Analyze cases first |

## 4. Solving a linear inequality in one variable

A linear inequality can be rearranged to a form such as

$$
ax+b \mathrel{<} c,
$$

where $a,b,c$ are fixed real numbers and $x\in\mathbb{R}$. The value of $a$ determines the method:

- If $a \mathrel{>} 0$, then $x \mathrel{<} (c-b)/a$.
- If $a \mathrel{<} 0$, then $x \mathrel{>} (c-b)/a$, because division by $a$ reverses the inequality.
- If $a=0$, the inequality becomes the numerical statement $b \mathrel{<} c$. It is true for every real $x$ when $b \mathrel{<} c$, and false for every real $x$ when $b\geq c$.

For a non-strict inequality $ax+b\leq c$, the same cases apply, with the final comparison $b\leq c$ in the $a=0$ case. This zero-coefficient check is analogous to the classification used for equations in Chapter 03.

### Example 1 — A positive coefficient

Solve $3x-7 \mathrel{<} 11$.

Add 7 to both sides:

$$
3x \mathrel{<} 18.
$$

Divide by 3, which is positive:

$$
x \mathrel{<} 6.
$$

The solution set is $(-\infty,6)$.

### Example 2 — A negative coefficient

Solve $-4x+5\leq17$.

Subtract 5:

$$
-4x\leq12.
$$

Divide by $-4$ and reverse the direction:

$$
x\geq-3.
$$

The solution set is $[-3,\infty)$.

### Example 3 — Parentheses on both sides

Solve $3(x-2)\geq x+4$.

Expand and collect terms:

$$
3x-6\geq x+4,
$$

$$
2x\geq10.
$$

Divide by the positive number 2:

$$
x\geq5.
$$

The solution set is $[5,\infty)$.

### Example 4 — Rational coefficients

Solve $\frac{x-1}{2} \mathrel{<} \frac{2x+3}{3}$.

The denominators 2 and 3 are positive constants. Multiplying both sides by 6 preserves the direction:

$$
3(x-1) \mathrel{<} 2(2x+3).
$$

Expand and simplify:

$$
3x-3 \mathrel{<} 4x+6,
$$

so $-9 \mathrel{<} x$. The solution set is $(-9,\infty)$.

### Example 5 — A zero coefficient

Solve $0x+4\leq7$ over $\mathbb{R}$.

The statement reduces to $4\leq7$, which is true. Every real number is a solution, so the solution set is $\mathbb{R}$.

By contrast, $0x+4 \mathrel{<} 2$ reduces to the false statement $4 \mathrel{<} 2$ and has no solution. Do not attempt to divide by the zero coefficient.

## 5. Interval notation and number-line representations

An interval is a subset of $\mathbb{R}$ containing every real number between any two of its elements. Parentheses exclude an endpoint; square brackets include it.

| Inequality | Interval notation |
|---|---|
| $a \mathrel{<} x \mathrel{<} b$ | $(a,b)$ |
| $a\leq x\leq b$ | $[a,b]$ |
| $a\leq x \mathrel{<} b$ | $[a,b)$ |
| $a \mathrel{<} x\leq b$ | $(a,b]$ |
| $x \mathrel{>} a$ | $(a,\infty)$ |
| $x\geq a$ | $[a,\infty)$ |
| $x \mathrel{<} b$ | $(-\infty,b)$ |
| $x\leq b$ | $(-\infty,b]$ |

Infinity is never an included endpoint, so an interval always uses a parenthesis next to $\infty$ or $-\infty$. For finite endpoints, the bracket type records whether the endpoint satisfies the inequality.

The interval $(a,a)$ is empty. The interval $[a,a]$ contains exactly one point, namely $a$. In general, a solution set over an integer domain is obtained by intersecting the real interval solution with $\mathbb{Z}$; interval notation alone does not encode discreteness.

### Number-line convention

A hollow circle marks an excluded endpoint; a filled circle marks an included endpoint. The shaded or arrowed portion represents all solutions.

```text
x < 2:       <================o---------------->
                              2

x >= -1:     <----------------●================>
                             -1

-2 < x <= 3: <---------o================●------>
                      -2                3
```

### Example 6 — Read an interval as an inequality

The interval $(-2,5]$ means that the variable is greater than $-2$ and at most 5:

$$
-2 \mathrel{<} x\leq5.
$$

The endpoint $-2$ is excluded and 5 is included.

## 6. Compound inequalities: AND and OR

A compound inequality combines two comparisons. The words **and** and **or** have different set meanings:

- **And** means both conditions must hold; the solution set is the intersection of the two solution sets.
- **Or** means at least one condition must hold; the solution set is the union of the two solution sets.

### 6.1 Chained inequalities (AND)

A statement such as

$$
a\leq bx+c \mathrel{<} d
$$

means both $a\leq bx+c$ and $bx+c \mathrel{<} d$ must be true. The same operation may be applied to all three parts, but multiplication or division by a negative number reverses both comparison signs.

### Example 7 — Solve a chained inequality

Solve $-2\leq3x+1 \mathrel{<} 10$.

Subtract 1 from all three parts:

$$
-3\leq3x \mathrel{<} 9.
$$

Divide all three parts by the positive number 3:

$$
-1\leq x \mathrel{<} 3.
$$

The solution set is $[-1,3)$.

### Example 8 — Chained inequality with a negative coefficient

Solve $-2 \mathrel{<} 3-2x\leq9$.

Subtract 3 from all three parts:

$$
-5 \mathrel{<} -2x\leq6.
$$

Divide by $-2$. Both inequality signs reverse:

$$
\frac52 \mathrel{>} x\geq-3.
$$

Written in increasing order, the solution is $-3\leq x \mathrel{<} \frac52$, or $[-3,\frac52)$.

### 6.2 Disjunctions (OR)

A statement such as $x \mathrel{<} a$ or $x \mathrel{>} b$ describes two separated parts of the real line. Its solution set is the union $(-\infty,a)\cup(b,\infty)$.

### Example 9 — Two rays

Solve $x\leq-2$ or $x \mathrel{>} 3$.

The two parts are already solved. The solution set is

$$
(-\infty,-2]\cup(3,\infty).
$$

Do not replace “or” by “and”: a number does not need to satisfy both separated conditions.

## 7. Absolute value as distance

For a real number $x$, its absolute value is

$$
\lvert x\rvert=\begin{cases}
x,&x\geq0,\\
-x,&x \mathrel{<} 0.
\end{cases}
$$

Thus $\lvert x\rvert$ is the distance from $x$ to 0 on the real number line. It is always nonnegative. More generally, $\lvert x-a\rvert$ is the distance between $x$ and $a$.

Basic properties for real $x$ and $y$ include:

$$
\lvert x\rvert\geq0,\qquad \lvert x\rvert=0\Longleftrightarrow x=0,
$$

$$
\lvert -x\rvert=\lvert x\rvert,\qquad \lvert xy\rvert=\lvert x\rvert\lvert y\rvert,
$$

and, when $y\ne0$,

$$
\left\lvert \frac{x}{y}\right\rvert=\frac{\lvert x\rvert}{\lvert y\rvert}.
$$

### 7.1 The triangle inequality

For all real $x$ and $y$,

$$
\lvert x+y\rvert\leq\lvert x\rvert+\lvert y\rvert.
$$

**Proof.** By the definition of absolute value,

$$
-\lvert x\rvert\leq x\leq\lvert x\rvert,\qquad -\lvert y\rvert\leq y\leq\lvert y\rvert.
$$

Adding the inequalities gives

$$
-(\lvert x\rvert+\lvert y\rvert)\leq x+y\leq\lvert x\rvert+\lvert y\rvert.
$$

A real number between $-M$ and $M$, where $M\geq0$, has absolute value at most $M$. Taking $M=\lvert x\rvert+\lvert y\rvert$ proves the result.

A useful consequence is the reverse triangle inequality:

$$
\bigl\lvert \lvert x\rvert-\lvert y\rvert\bigr\rvert\leq\lvert x-y\rvert.
$$

It follows by applying the triangle inequality to $x=(x-y)+y$ and then interchanging $x$ and $y$.

## 8. Absolute-value equations

For a real expression $u$ and a real constant $c$, the equation $\lvert u\rvert=c$ has three cases:

- If $c \mathrel{<} 0$, there is no solution because absolute value cannot be negative.
- If $c=0$, the equation is equivalent to $u=0$.
- If $c \mathrel{>} 0$, the equation is equivalent to $u=c$ **or** $u=-c$.

The two branches in the positive case are joined by **or**, because a number can be at distance $c$ from zero on either side.

### Example 10 — Two solutions

Solve $\lvert 2x-3\rvert=7$.

Since 7 is positive, solve the two equations:

$$
2x-3=7\quad\text{or}\quad2x-3=-7.
$$

The first gives $x=5$; the second gives $x=-2$. Both satisfy the original absolute-value equation. The solution set is $\{-2,5\}$.

### Example 11 — A negative right-hand side

The equation $\lvert x+1\rvert=-2$ has no real solution, because $\lvert x+1\rvert\geq0$ for every real $x$.

### Example 12 — Zero on the right

Solve $\lvert 3x-6\rvert=0$. An absolute value is zero only when its inside is zero:

$$
3x-6=0,
$$

so the unique solution is $x=2$.

## 9. Absolute-value inequalities

Let $u$ be a real expression and let $c \mathrel{>} 0$. The distance interpretation gives four basic equivalences:

| Absolute-value inequality | Equivalent statement |
|---|---|
| $\lvert u\rvert \mathrel{<} c$ | $-c \mathrel{<} u \mathrel{<} c$ |
| $\lvert u\rvert\leq c$ | $-c\leq u\leq c$ |
| $\lvert u\rvert \mathrel{>} c$ | $u \mathrel{<} -c$ or $u \mathrel{>} c$ |
| $\lvert u\rvert\geq c$ | $u\leq-c$ or $u\geq c$ |

The distinction is essential: “less than” describes the inside of a distance band and uses **and**; “greater than” describes the outside and uses **or**.

### 9.1 Edge cases when the threshold is not positive

The table above assumes $c \mathrel{>} 0$. The remaining cases must be handled explicitly:

| Condition | $\lvert u\rvert \mathrel{<} c$ | $\lvert u\rvert\leq c$ | $\lvert u\rvert \mathrel{>} c$ | $\lvert u\rvert\geq c$ |
|---|---|---|---|---|
| $c \mathrel{<} 0$ | No solutions | No solutions | All real inputs | All real inputs |
| $c=0$ | No solutions | $u=0$ | $u\ne0$ | All real inputs |

These statements follow from $\lvert u\rvert\geq0$.

### Example 13 — An absolute value bounded above

Solve $\lvert 3x-2\rvert\leq7$.

Because 7 is positive,

$$
-7\leq3x-2\leq7.
$$

Add 2 to all three parts and divide by 3:

$$
-5\leq3x\leq9,
$$

$$
-\frac53\leq x\leq3.
$$

The solution set is $[-\frac53,3]$.

### Example 14 — An absolute value bounded below

Solve $\lvert 2x+1\rvert \mathrel{>} 5$.

Because 5 is positive, split into two branches:

$$
2x+1 \mathrel{<} -5\quad\text{or}\quad2x+1 \mathrel{>} 5.
$$

The first gives $x \mathrel{<} -3$; the second gives $x \mathrel{>} 2$. The solution set is

$$
(-\infty,-3)\cup(2,\infty).
$$

### Example 15 — A negative threshold

Solve $\lvert x-4\rvert \mathrel{<} -1$. This is impossible because an absolute value is nonnegative. The solution set is $\varnothing$.

## 10. Absolute value as a tolerance or distance condition

A condition such as

$$
\lvert x-a\rvert\leq\varepsilon,\qquad\varepsilon\geq0,
$$

means that $x$ is within distance $\varepsilon$ of the target value $a$. It is equivalent to

$$
a-\varepsilon\leq x\leq a+\varepsilon.
$$

For example, $\lvert x-7\rvert\leq0.5$ means $6.5\leq x\leq7.5$. This form is useful when a measurement has a stated tolerance. It does not by itself specify measurement uncertainty, instrument calibration, or a probability distribution; those require additional information.

## 11. Python: exact membership in an interval

The following standard-library example checks whether a rational number belongs to an interval. It uses `Fraction` to avoid floating-point rounding at endpoints. A missing lower endpoint represents $-\infty$; a missing upper endpoint represents $+\infty$. Infinite endpoints are necessarily open.

```python
from fractions import Fraction


def as_fraction(value):
    """Convert an integer, Fraction, or rational string exactly."""
    if isinstance(value, bool) or isinstance(value, float):
        raise TypeError("Use int, Fraction, or a rational string; not float/bool.")
    if not isinstance(value, (int, Fraction, str)):
        raise TypeError("Unsupported rational input type.")
    return Fraction(value)


def interval_contains(value, lower=None, upper=None,
                      left_closed=False, right_closed=False):
    """Return whether value belongs to the specified real interval.

    None as lower means -infinity; None as upper means +infinity.
    Infinite endpoints cannot be closed. Endpoints are exact rationals.
    """
    if not isinstance(left_closed, bool) or not isinstance(right_closed, bool):
        raise TypeError("Endpoint flags must be bool values.")
    if lower is None and left_closed:
        raise ValueError("The -infinity endpoint cannot be closed.")
    if upper is None and right_closed:
        raise ValueError("The +infinity endpoint cannot be closed.")

    x = as_fraction(value)
    lo = None if lower is None else as_fraction(lower)
    hi = None if upper is None else as_fraction(upper)

    if lo is not None and hi is not None and lo > hi:
        raise ValueError("The lower endpoint must not exceed the upper endpoint.")

    above_lower = True if lo is None else (x >= lo if left_closed else x > lo)
    below_upper = True if hi is None else (x <= hi if right_closed else x < hi)
    return above_lower and below_upper


# Examples: (-1, 3] includes 3 but excludes -1.
assert interval_contains("3", -1, 3, False, True)
assert not interval_contains("-1", -1, 3, False, True)
assert interval_contains("1/2", 0, 1, True, False)
assert not interval_contains("1", 0, 1, True, False)
assert interval_contains(-100, None, 5, False, True)

print("Exact interval-membership examples passed.")
```

This program checks membership in an interval that has already been found. It does not derive the solution of an inequality. The algebraic reasoning remains the responsibility of the solver, and a finite set of code tests is not a proof of the general interval rules.

## 12. Common errors and how to avoid them

| Incorrect approach | Why it fails | Correct principle |
|---|---|---|
| Divide by a negative number without reversing the sign. | Multiplication by a negative reverses real order. | Reverse the inequality when multiplying or dividing by a negative value. |
| Multiply by a variable expression without checking its sign. | The factor may be positive, zero, or negative. | Establish its sign or split into cases. |
| Use a square bracket for an excluded endpoint. | The interval then includes a value that does not satisfy the strict inequality. | Match brackets to $ \mathrel{<} $, $\leq$, $ \mathrel{>} $, or $\geq$. |
| Put a parenthesis next to infinity as if infinity were a number. | Infinity is not a real endpoint and is never included. | Always use parentheses at infinite endpoints. |
| Translate $\lvert u\rvert \mathrel{<} c$ into two separate outside rays. | “Less than” means the distance is inside the band. | Use $-c \mathrel{<} u \mathrel{<} c$ when $c \mathrel{>} 0$. |
| Translate $\lvert u\rvert \mathrel{>} c$ into a chained inequality. | “Greater than” means outside the band. | Use $u \mathrel{<} -c$ or $u \mathrel{>} c$ when $c \mathrel{>} 0$. |
| Solve $\lvert u\rvert=c$ by dividing into two branches when $c \mathrel{<} 0$. | Absolute value cannot be negative. | Check the sign of $c$ first. |
| Treat an integer-domain problem as a continuous interval answer. | The domain may contain only isolated values. | Intersect the real solution set with the stated domain. |

## 13. Exercises

Unless a domain is stated otherwise, solve over $\mathbb{R}$. Give interval notation where appropriate.

### A. Linear inequalities

1. Solve $x+5 \mathrel{<} 9$.
2. Solve $-3x\leq12$.
3. Solve $2-5x \mathrel{>} 17$.
4. Solve $3(x-2)\geq x+4$.
5. Solve $\frac{x-1}{2} \mathrel{<} \frac{2x+3}{3}$.
6. Solve $0x+4\leq7$ and explain why the coefficient-zero case is different from division by a nonzero coefficient.

### B. Compound inequalities and intervals

7. Solve $-2\leq3x+1 \mathrel{<} 10$.
8. Solve $4 \mathrel{<} x+5\leq9$.
9. Write $x\leq-2$ or $x \mathrel{>} 3$ in interval notation.
10. Solve $-2 \mathrel{<} 3-2x\leq9$.

### C. Absolute-value equations and inequalities

11. Solve $\lvert x\rvert=6$.
12. Solve $\lvert x-4\rvert=3$.
13. Solve $\lvert 2x+1\rvert=5$.
14. Solve $\lvert x+2\rvert\leq4$.
15. Solve $\lvert 3x-6\rvert \mathrel{<} 9$.
16. Solve $\lvert x-1\rvert\geq2$.
17. Solve $\lvert 2x+3\rvert \mathrel{>} 1$.
18. Solve $\lvert x+2\rvert \mathrel{<} -1$ and justify your answer without algebraic manipulation.

### D. Applications and challenge problems

19. A temperature conversion is given by $F=\frac95C+32$. Find the Celsius interval corresponding to $50\leq F \mathrel{<} 68$.
20. A measured value $x$ must be within 0.5 units of 7. Express the condition as an absolute-value inequality and as an interval.
21. **Challenge:** Solve $\lvert 2x-4\rvert\geq6$ and explain why the answer has two separated intervals.

## 14. Selected answers

1. $(-\infty,4)$.
2. $[-4,\infty)$.
3. $(-\infty,-3)$.
4. $[5,\infty)$.
5. $(-9,\infty)$.
6. Every real number; the inequality reduces to the true statement $4\leq7$.
7. $[-1,3)$.
8. $(-1,4]$.
9. $(-\infty,-2]\cup(3,\infty)$.
10. $[-3,\frac52)$.
11. $\{-6,6\}$.
12. $\{1,7\}$.
13. $\{-3,2\}$.
14. $[-6,2]$.
15. $(-1,5)$.
16. $(-\infty,-1]\cup[3,\infty)$.
17. $(-\infty,-2)\cup(-1,\infty)$.
18. $\varnothing$, because absolute value is nonnegative.
19. $[10,20)$ degrees Celsius.
20. $\lvert x-7\rvert\leq0.5$, equivalently $[6.5,7.5]$.
21. $(-\infty,-1]\cup[5,\infty)$; the absolute value is at least 6 when the inside is at most $-6$ or at least 6.

## 15. Chapter summary

- Adding or subtracting the same quantity preserves an inequality.
- Multiplication or division by a positive number preserves direction; by a negative number it reverses direction.
- A zero factor or an expression of unknown sign cannot be used as an ordinary inequality-preserving multiplier.
- Interval brackets record endpoint inclusion; infinity is always written with a parenthesis.
- “And” corresponds to intersection; “or” corresponds to union.
- Absolute value measures distance from zero, and $\lvert x-a\rvert$ measures distance from $a$.
- For $c \mathrel{>} 0$, $\lvert u\rvert \mathrel{<} c$ describes the inside band, while $\lvert u\rvert \mathrel{>} c$ describes the two outside rays.
- Check zero and negative thresholds before applying the standard absolute-value templates.

## 16. References and connections

- Math-Atlas Foundations, Chapter 04 — Number Systems and Mathematical Structures: ordered-field properties of the real numbers.
- Math-Atlas Foundations, Chapter 05 — Mathematical Proof Techniques: direct reasoning used in the proof of the triangle inequality.
- Math-Atlas Foundations, Chapter 07 — Mathematical Notation and Symbols: set, interval, and inequality notation.
- Math-Atlas Algebra, Chapter 02 — Real-Number Properties and Algebraic Simplification: order properties and exact rational arithmetic.
- Math-Atlas Algebra, Chapter 03 — Linear Equations and Literal Equations: solution sets and safe transformations.

**Next chapter:** Chapter 05 — Coordinate Graphs and Linear Models.
