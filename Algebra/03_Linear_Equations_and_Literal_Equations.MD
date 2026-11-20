# Algebra 03 — Linear Equations and Literal Equations

## 1. Introduction

An equation states that two expressions have the same value. Solving an equation means finding every value in the stated domain that makes this statement true. The goal of this chapter is not merely to move symbols from one side to the other: every step must preserve the equation's solution set, or clearly identify when a step produces only candidate solutions.

We focus on linear equations in one real variable and on rearranging formulas (often called literal equations), in which several letters represent variables or parameters. Equations with variable denominators, radical equations, polynomial equations of degree greater than one, and inequalities are developed in later chapters.

### Learning objectives

After this chapter, you should be able to:

- State the domain and solution set of an equation.
- Distinguish an equation with one solution from an identity and a contradiction.
- Explain why adding the same quantity to both sides and multiplying by a nonzero constant preserve the solution set.
- Solve linear equations with variables on both sides, parentheses, and rational coefficients.
- Recognize equations whose coefficient of the variable is zero and handle those cases correctly.
- Rearrange literal equations to isolate a specified variable while stating required nonzero conditions.
- Check a proposed solution in the original equation.
- Use exact rational arithmetic in Python to solve and classify simple linear equations.

## 2. Equations and solution sets

Let $D$ be the domain of a variable $x$, and let $L(x)$ and $R(x)$ be expressions defined for the values under consideration. The equation

$$
L(x)=R(x)
$$

has solution set

$$
S_D=\{x\in D:L(x)=R(x)\}.
$$

A **solution** is a value in $S_D$. The domain is part of the problem: the same written equation can have different solution sets over different domains.

### Example 1 — The domain changes the solution set

Consider

$$
x^2=4.
$$

Over the real numbers, the solution set is $\{-2,2\}$. Over the nonnegative real numbers, the solution set is $\{2\}$. Over the integers, the solution set is still $\{-2,2\}$.

The equation has not changed; the domain has.

### 2.1 Equivalent equations

Two equations in the same domain are **equivalent** when they have exactly the same solution set. We write this informally as “the equations are equivalent”; when useful, we may display

$$
L(x)=R(x)\quad\Longleftrightarrow\quad P(x)=Q(x).
$$

The biconditional is justified only when each equation implies the other over the stated domain. A transformation that proves only one direction is not enough to claim equivalence.

## 3. Three outcomes for a linear equation

A linear equation in one variable can have one solution, no solution, or every value in its domain as a solution. The last two cases are especially important because a procedure that assumes a unique answer can mishandle them.

### 3.1 An equation with one solution

Consider

$$
3x+5=2x+11.
$$

Subtract $2x$ from both sides, then subtract 5:

$$
3x-2x=11-5,
$$

so

$$
x=6.
$$

The solution set over $\mathbb{R}$ is $\{6\}$. Substitution verifies it:

$$
3(6)+5=23=2(6)+11.
$$

### 3.2 An identity

An **identity** is an equation that is true for every value in its stated domain. For example,

$$
2(x+3)=2x+6
$$

expands to

$$
2x+6=2x+6.
$$

Both sides are equal for every real $x$. Its solution set is $\mathbb{R}$, not a single number.

### 3.3 A contradiction

A **contradiction** is an equation that is false for every value in its stated domain. For example,

$$
2(x+3)=2x+7
$$

simplifies to

$$
2x+6=2x+7,
$$

and subtracting $2x$ gives $6=7$, which is false. Its solution set is empty, written $\varnothing$.

### 3.4 A useful classification table

| Simplified result | Classification | Solution set over $\mathbb{R}$ |
|---|---|---|
| $x=4$ | One-solution equation | $\{4\}$ |
| $0=0$ | Identity | $\mathbb{R}$ |
| $0=5$ | Contradiction | $\varnothing$ |

The result must be interpreted after valid transformations. A false step, such as dividing by a quantity that may be zero, can change the outcome.

## 4. Why the standard solving steps work

The real numbers form a field. In particular, they have additive inverses, and every nonzero real number has a multiplicative inverse. These properties justify the elementary operations used to solve linear equations.

### 4.1 Adding or subtracting the same quantity

For any real expressions $A(x)$, $B(x)$, and $C(x)$ that are defined on the domain,

$$
A(x)=B(x)\quad\Longleftrightarrow\quad A(x)+C(x)=B(x)+C(x).
$$

The forward direction follows by adding equal quantities. The reverse direction follows by adding $-C(x)$ to both sides. Therefore, adding or subtracting the same defined quantity preserves the solution set.

### 4.2 Multiplying by a nonzero constant

For a fixed real number $k\ne0$,

$$
A(x)=B(x)\quad\Longleftrightarrow\quad kA(x)=kB(x).
$$

The forward direction follows from multiplication. For the reverse direction, multiply both sides by $1/k$, which exists because $k\ne0$.

If $k=0$, this argument fails: multiplying any equation by zero produces $0=0$, which is true for every $x$ and can destroy the original solution set. Therefore, **multiplication by zero is not an equivalence-preserving solving step**.

### 4.3 Dividing by a nonzero constant

For a fixed $k\ne0$,

$$
A(x)=B(x)\quad\Longleftrightarrow\quad \frac{A(x)}{k}=\frac{B(x)}{k}.
$$

This is multiplication by the nonzero reciprocal $1/k$.

Dividing by an expression that depends on the variable is more delicate. Before dividing by $g(x)$, split the original domain into the cases $g(x)=0$ and $g(x)\ne0$, unless it has already been proved that no solution of the original equation can occur when $g(x)=0$. Substitute the zero case into the original equation; it may contain solutions that would be lost by division. Division is reversible on the nonzero case. This issue becomes central in later chapters on rational and polynomial equations.

For a simple illustration of the danger of multiplying by a variable expression, start with $x=2$ and multiply both sides by $x$:

$$
x^2=2x.
$$

The new equation is also satisfied by $x=0$, even though $0$ does not satisfy the original equation $x=2$. Thus multiplication by a variable expression that may be zero can introduce extra candidates.

## 5. A reliable procedure for solving linear equations

For an equation that can be written as

$$
ax+b=c,
$$

where $a,b,c$ are fixed real numbers and $x\in\mathbb{R}$, first consider whether $a$ is zero.

- If $a\ne0$, there is exactly one solution, $x=(c-b)/a$.
- If $a=0$ and $b=c$, every real number is a solution.
- If $a=0$ and $b\ne c$, there is no solution.

When the equation has variables on both sides, the practical steps are:

1. Expand parentheses when doing so makes the equation easier to organize.
2. Combine like terms on each side.
3. Add or subtract terms to collect all variable terms on one side and constants on the other.
4. Combine again; inspect the coefficient of the variable.
5. If the coefficient is nonzero, divide by it. If it is zero, classify the resulting statement as an identity or contradiction.
6. Substitute any proposed solution into the original equation.

These are not arbitrary symbol-moving rules. Each step is justified by the equality properties above.

### Example 2 — Variables on both sides

Solve

$$
5(2x-1)-3=4(x+2)+8.
$$

Expand both sides:

$$
10x-5-3=4x+8+8.
$$

Combine constants:

$$
10x-8=4x+16.
$$

Subtract $4x$ from both sides and add 8 to both sides:

$$
6x=24.
$$

Divide by 6:

$$
x=4.
$$

Check in the original equation:

$$
5(2\cdot4-1)-3=5(7)-3=32,
$$

and

$$
4(4+2)+8=24+8=32.
$$

Both sides agree, so the solution is $x=4$.

### Example 3 — Rational coefficients

Solve

$$
\frac34x-\frac56=\frac13x+\frac12.
$$

The denominators are numerical constants. Multiplying both sides by their least common multiple, 12, is safe because 12 is nonzero:

$$
9x-10=4x+6.
$$

Collect terms:

$$
5x=16,
$$

so

$$
x=\frac{16}{5}.
$$

Check using the original equation:

$$
\frac34\cdot\frac{16}{5}-\frac56
=\frac{12}{5}-\frac56
=\frac{72}{30}-\frac{25}{30}
=\frac{47}{30},
$$

and

$$
\frac13\cdot\frac{16}{5}+\frac12
=\frac{16}{15}+\frac12
=\frac{32}{30}+\frac{15}{30}
=\frac{47}{30}.
$$

The two sides agree, so the verified solution is $x=\frac{16}{5}$.

### Example 4 — An identity

Solve

$$
4(2x-3)=8x-12.
$$

Expanding the left side gives

$$
8x-12=8x-12.
$$

Subtracting $8x$ and adding 12 gives $0=0$. Every real number satisfies the original equation. The solution set is $\mathbb{R}$.

### Example 5 — A contradiction

Solve

$$
3(2x+1)=6x+8.
$$

Expanding gives

$$
6x+3=6x+8.
$$

Subtracting $6x$ gives $3=8$, which is false. The solution set is $\varnothing$.

## 6. Equations with parameters: the zero-coefficient case

A parameter is fixed while an equation is solved, but its value may vary between problems. The equation

$$
(a-2)x=6
$$

has a unique real solution when $a\ne2$:

$$
x=\frac{6}{a-2}.
$$

When $a=2$, the equation becomes $0\cdot x=6$, or $0=6$, so it has no solution. We must not divide by $a-2$ before considering the case $a=2$.

Now consider

$$
(a-2)x=0.
$$

- If $a\ne2$, divide by the nonzero coefficient and obtain $x=0$.
- If $a=2$, the equation becomes $0=0$, so every real $x$ is a solution.

### Example 6 — Classify a parameterized equation

For which real values of $m$ does

$$
(m+1)x=m+1
$$

have one solution, and what happens for the remaining value?

If $m\ne-1$, divide by the nonzero number $m+1$ to obtain $x=1$. If $m=-1$, the equation becomes $0=0$, so every real number is a solution.

## 7. Literal equations and rearranging formulas

A **literal equation** is an equation involving two or more letters. Usually, one letter is selected as the subject, meaning that we rearrange the equation to express that letter in terms of the others. The other letters may be variables or fixed parameters, depending on the context.

The same equality-preserving principles apply, but coefficients may now be expressions involving parameters. Every division therefore needs a nonzero condition.

### Example 7 — Perimeter of a rectangle

The perimeter formula is

$$
P=2l+2w.
$$

Solve for $w$:

$$
P-2l=2w,
$$

so

$$
w=\frac{P-2l}{2}=\frac P2-l.
$$

Division by 2 is always valid because 2 is nonzero.

### Example 8 — Area of a triangle

The area formula is

$$
A=\frac12 bh.
$$

Solve for $h$. Multiply both sides by 2:

$$
2A=bh.
$$

If $b\ne0$, divide by $b$:

$$
h=\frac{2A}{b}.
$$

The condition $b\ne0$ is essential. If $b=0$, the original equation becomes $A=0$:

- If $A=0$, every real $h$ satisfies the equation.
- If $A\ne0$, no value of $h$ satisfies it.

In a geometric context, a triangle with base length zero is degenerate; the algebraic case analysis still explains why division by $b$ cannot be automatic.

### Example 9 — Distance, rate, and time

The constant-rate formula is

$$
d=rt.
$$

Solving for time gives

$$
t=\frac dr
$$

provided $r\ne0$. If $r=0$, the equation reduces to $d=0$:

- If $d=0$, every real $t$ satisfies the algebraic equation.
- If $d\ne0$, there is no solution.

In a physical application, additional conditions such as nonnegative time and a meaningful rate may restrict the domain further.

### Example 10 — Temperature conversion

The conversion formula is

$$
F=\frac95C+32.
$$

Subtract 32 and multiply by $5/9$:

$$
C=\frac59(F-32).
$$

The rearrangement is valid for every real $F$ because the coefficient $9/5$ is nonzero.

### 7.1 A general parameter rule

For a literal equation of the form

$$
A(p)x+B(p)=C(p),
$$

where $p$ represents one or more parameters, the solution depends on whether $A(p)$ is zero:

- If $A(p)\ne0$, then $x=\dfrac{C(p)-B(p)}{A(p)}$.
- If $A(p)=0$ and $B(p)=C(p)$, every admissible $x$ is a solution.
- If $A(p)=0$ and $B(p)\ne C(p)$, there is no solution.

This case split is the safe alternative to dividing by an expression whose value has not been checked.

## 8. Checking solutions and recognizing unsafe steps

A proposed solution must be tested in the **original equation**, not merely in the final transformed equation. This matters whenever a transformation may fail to be reversible.

For the elementary linear equations in Sections 2–7, adding the same expression and multiplying or dividing by a known nonzero constant preserve equivalence. The following operations need extra care:

- Dividing by a variable expression: it may be zero. Split into cases or prove it is nonzero for all possible solutions.
- Multiplying by a variable expression: if that expression can be zero, the new equation may acquire additional solutions.
- Squaring both sides: the squared equation may be true even when the original sides have opposite signs. Check candidates in the original equation.
- Clearing variable denominators: record the original denominator restrictions before multiplying. Rational equations are treated systematically in Chapter 10.

### Example 11 — Why a nonzero condition matters

Suppose we are asked to solve

$$
(k-3)x=12.
$$

It is tempting to write $x=12/(k-3)$ immediately. This expression is valid only if $k\ne3$. When $k=3$, the original equation is $0=12$, a contradiction. The complete answer is therefore:

$$
x=\frac{12}{k-3}\quad\text{if }k\ne3,
$$

and no solution if $k=3$.

## 9. Common errors and how to avoid them

| Incorrect approach | Why it fails | Correct principle |
|---|---|---|
| Divide both sides by a coefficient without checking whether it is zero. | The zero case may be an identity or contradiction. | Inspect the coefficient before dividing. |
| Multiply both sides by zero and claim equivalence. | Every equation becomes $0=0$. | Multiplication preserves equivalence only by a nonzero factor. |
| Treat $0x=0$ as $x=0$. | The equation is true for every real $x$. | Its solution set is $\mathbb{R}$. |
| Treat $0x=5$ as $x=5$. | The left side is always zero. | The equation has no solution. |
| Divide by a variable and discard the case where it is zero. | A possible solution may be lost. | Split cases before division. |
| Accept a value that solves only a transformed equation. | A non-equivalent step may have introduced candidates. | Substitute into the original equation. |
| Rearrange a formula and omit a required condition such as $b\ne0$. | The displayed formula is undefined when the coefficient is zero. | State the condition and analyze the zero case. |

## 10. Python: exact classification and solution of linear equations

The following function solves

$$
ax+b=c
$$

over the real domain, where $a$, $b$, and $c$ are exact rational inputs. It distinguishes a unique solution, an identity, and a contradiction. The code uses `Fraction`, so calculations remain exact.

The function accepts integers, `Fraction` objects, and rational strings such as `"3/5"`. It intentionally rejects floating-point inputs; convert a decimal text such as `"0.1"` to a rational string when exact decimal intent is desired.

```python
from fractions import Fraction


def as_fraction(value):
    """Convert an integer, Fraction, or rational string exactly."""
    if isinstance(value, bool) or isinstance(value, float):
        raise TypeError("Use int, Fraction, or a rational string; do not pass float.")
    if isinstance(value, (int, Fraction, str)):
        return Fraction(value)
    raise TypeError("Unsupported coefficient type.")


def solve_linear(a, b, c):
    """Classify and solve a*x + b = c over the real numbers.

    Returns:
        ("unique", x)       when exactly one real solution exists;
        ("all_reals", None) when every real number is a solution;
        ("no_solution", None) when no real solution exists.
    """
    a = as_fraction(a)
    b = as_fraction(b)
    c = as_fraction(c)

    if a == 0:
        if b == c:
            return "all_reals", None
        return "no_solution", None

    x = (c - b) / a
    # Verify the result in the original equation using exact arithmetic.
    assert a * x + b == c
    return "unique", x


examples = [
    (2, 3, 11),       # 2x + 3 = 11 -> x = 4
    (0, 5, 5),        # 0x + 5 = 5 -> every real x
    (0, 5, 8),        # 0x + 5 = 8 -> no solution
    (Fraction(5, 12), Fraction(-5, 6), Fraction(1, 2)),  # reduced form of the worked equation -> x = 16/5
]

for coefficients in examples:
    print(coefficients, "->", solve_linear(*coefficients))
```

### 10.1 What the program does and does not prove

The program correctly classifies and solves the supplied rational-coefficient equations. It does not prove the general theorem for all real coefficients. The mathematical proof comes from the field properties of $\mathbb{R}$ and the zero-coefficient case split; the code is an exact computational illustration.

## 11. Worked examples

### Example 12 — Solve with parentheses on both sides

Solve

$$
2(3x-4)-5=3(x+2)+4x.
$$

Expand and combine:

$$
6x-8-5=3x+6+4x,
$$

so

$$
6x-13=7x+6.
$$

Subtract $6x$ and subtract 6:

$$
-19=x,
$$

hence $x=-19$. Check in the original equation:

$$
2(3(-19)-4)-5=2(-61)-5=-127,
$$

and

$$
3(-19+2)+4(-19)=-51-76=-127.
$$

Both sides agree, so $x=-19$ is the solution.

### Example 13 — A linear equation from a context

A bicycle rental service charges a fixed fee of 8 units plus 3 units per hour. A customer pays 29 units. Let $h$ be the number of hours. The model is

$$
8+3h=29.
$$

Subtract 8 and divide by 3:

$$
3h=21,\qquad h=7.
$$

The customer rented the bicycle for 7 hours. This is consistent with the contextual domain $h\geq0$.

### Example 14 — Rearranging a formula with a parameter condition

The kinetic-energy formula is

$$
K=\frac12 mv^2.
$$

In the physical interpretation, mass is positive. Algebraically, solve for $v^2$ by first assuming $m\ne0$:

$$
2K=mv^2.
$$

If $m\ne0$, then

$$
v^2=\frac{2K}{m}.
$$

Because $v$ is real, data from the original equation must also satisfy $2K/m\geq0$; otherwise no real $v$ can satisfy it. This chapter only rearranges the formula to isolate $v^2$. Solving for $v$ requires taking square roots and considering both signs, a step developed later with radical equations.

## 12. Exercises

Unless an exercise states a different domain, variables are real.

### A. Concepts and classification

1. Explain what a solution set is and why its domain must be stated.
2. Classify $5(x-2)=5x-10$ as an equation with one solution, an identity, or a contradiction. State its solution set.
3. Classify $4(x+1)=4x+9$. State its solution set.
4. Give an example of an equation that has exactly one real solution and verify it.
5. Explain why multiplying both sides of an equation by zero does not preserve equivalence.

### B. Solve and verify

6. Solve $7x-9=26$ and check the result in the original equation.
7. Solve $4(2x-1)=3x+16$.
8. Solve $0.2x+1.5=3.1$ exactly.
9. Solve $\frac78x-\frac14=\frac12x+\frac34$.
10. Solve $\frac23(x-3)=\frac12(x+2)$.
11. Solve $-2(4-x)=3x-7$.
12. Determine whether $2(3x+1)-5=6x-3$ has one solution, no solution, or all real numbers as solutions.

### C. Literal equations and parameters

13. From $P=2l+2w$, solve for $w$.
14. From $A=\frac12 bh$, solve for $b$ and state the required condition.
15. From $F=\frac95C+32$, solve for $C$.
16. From $s=ut$, solve for $t$. State the condition for the displayed rearrangement and analyze the case $u=0$.
17. Classify $(k-3)x=12$ for all real values of the parameter $k$.
18. Classify $(m+1)x=m+1$ for all real values of $m$.

### D. Reasoning and error analysis

19. A student solves $ax=6$ by writing $x=6/a$. Explain why the student's answer needs a condition, and classify the equation when $a=0$.
20. A student claims that $2(x+4)=2x+9$ has solution $x=9$. Show why this is incorrect.
21. Explain the difference between an identity and an equation that happens to have a solution such as $x=0$.
22. Create a linear equation with rational coefficients whose unique solution is $x=\frac52$. Show the construction and verify it.
23. Rearrange $V=IR$ to make $R$ the subject, and state the required condition on $I$.
24. A rectangle has perimeter 50 units and length 16 units. Use a literal equation to find its width and state whether the answer is consistent with a positive width.

## 13. Selected answers and solution outlines

1. The set of all values in the stated domain that make the equation true; changing the domain can change this set.
2. Identity; solution set $\mathbb{R}$.
3. Contradiction, since it reduces to $4=9$; solution set $\varnothing$.
4. Example: $2x+1=9$, whose solution is $x=4$; substitution gives 9 on both sides.
5. Every equation becomes $0=0$, so equations with different solution sets become indistinguishable.
6. $x=5$.
7. $8x-4=3x+16$, so $x=4$.
8. $x=8$.
9. $\frac38x=1$, so $x=\frac83$.
10. $4(x-3)=3(x+2)$, so $x=18$.
11. $-8+2x=3x-7$, so $x=-1$.
12. Identity; all real numbers.
13. $w=\frac P2-l$.
14. $b=\frac{2A}{h}$ provided $h\ne0$. If $h=0$ and $A=0$, every real $b$ satisfies the original equation; if $h=0$ and $A\ne0$, no $b$ satisfies it.
15. $C=\frac59(F-32)$.
16. $t=\frac su$ provided $u\ne0$. If $u=0$, then $s=0$ allows every $t$ algebraically, while $s\ne0$ allows none.
17. If $k\ne3$, $x=\frac{12}{k-3}$; if $k=3$, there is no solution.
18. If $m\ne-1$, $x=1$; if $m=-1$, every real $x$ is a solution.
19. The division requires $a\ne0$. If $a=0$, the equation is $0=6$, a contradiction.
20. It reduces to $8=9$, so it has no solution.
21. An identity is true for every value in the domain; an ordinary equation may be true only for a proper subset of the domain.
22. Many answers are possible. For example, $2x+1=6$ gives $x=\frac52$.
23. $R=\frac VI$ provided $I\ne0$. If $I=0$, then $V=0$ allows every algebraic value of $R$, while $V\ne0$ allows none.
24. $50=2(16)+2w$, so $w=9$ units, which is positive and consistent.

## 14. Chapter summary

- An equation is solved by finding its solution set in a specified domain.
- Equivalent equations have exactly the same solution set.
- Adding the same defined quantity to both sides preserves equivalence.
- Multiplying or dividing by a fixed nonzero number preserves equivalence.
- A one-variable linear equation may have one solution, no solution, or every real number as a solution.
- Always inspect a variable coefficient before dividing by it.
- Literal equations are rearranged using the same rules, with explicit nonzero conditions on coefficients.
- Check proposed solutions in the original equation whenever a transformation may not be reversible.
- Exact rational arithmetic is useful for checking computations, but code does not replace a general proof.

## 15. References

- Math-Atlas, [**Foundations 03 — Relations and Functions**](../Foundations/03_Relations_and_Functions.MD): domains, relations, and function language.
- Math-Atlas, [**Foundations 04 — Number Systems and Mathematical Structures**](../Foundations/04_Number_Systems_and_Mathematical_Structures.MD): real-number systems and field properties.
- Math-Atlas, [**Foundations 05 — Mathematical Proof Techniques**](../Foundations/05_Mathematical_Proof_Techniques.MD): direct reasoning and proof structure.
- Math-Atlas, [**Foundations 07 — Mathematical Notation and Symbols**](../Foundations/07_Mathematical_Notation_and_Symbols.MD): notation and symbol conventions.
- Math-Atlas, [**Algebra 01 — Algebraic Language and Expressions**](01_Algebraic_Language_and_Expressions.MD): variables, expressions, equations, identities, and distributive notation.
- Math-Atlas, [**Algebra 02 — Real-Number Properties and Algebraic Simplification**](02_Real_Number_Properties_and_Algebraic_Simplification.MD): ordered-field properties, signs, fractions, and exact arithmetic.

**Next chapter:** Chapter 04 — Linear Inequalities and Absolute Value.
