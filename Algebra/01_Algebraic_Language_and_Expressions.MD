# Algebra 01 — Algebraic Language and Expressions

## 1. Introduction

Algebra gives us a language for describing quantities and relationships when some values are unknown, changeable, or represented by parameters. Its symbols are not decorations: each variable, operation, and grouping mark has a precise role.

An algebraic expression can represent a cost, distance, area, number pattern, or many other quantities. Algebra then provides rules for rewriting expressions without changing their values and for solving equations that describe relationships.

This chapter establishes the language used throughout the Algebra volume. It focuses on expressions before moving to equation-solving procedures.

### Learning objectives

After this chapter, you should be able to:

- Distinguish variables, constants, parameters, expressions, equations, identities, and inequalities.
- Identify terms, coefficients, factors, and exponents.
- Evaluate expressions by substitution while respecting order of operations.
- Translate common verbal statements into algebraic expressions.
- Identify like terms and simplify sums of like terms.
- Apply the distributive property and explain why it is valid.
- Recognize equivalent expressions and identify common invalid transformations.
- Use Python to evaluate simple expressions without using unsafe dynamic evaluation.

## 2. Variables, constants, and parameters

A **variable** is a symbol representing an element of a specified set. In elementary algebra, variables commonly represent real numbers, but the domain must be stated when it matters.

A **constant** is a fixed value in the context under discussion. A **parameter** is also fixed within one problem, but it may vary between different members of a family of problems.

For example, in

$$
C(x)=5x+12,
$$

if $x$ is the number of items purchased, then $5$ is the unit cost and $12$ is a fixed fee. If a business model is written as

$$
C(x)=mx+b,
$$

then $x$ is the input variable, while $m$ and $b$ are parameters when one particular line is being studied. In another problem, the parameters themselves may be variables.

The role of a symbol is determined by the problem, not by the letter used.

### 2.1 Domain matters

An expression may be meaningful only for certain values. For example,

$$
\frac{1}{x-3}
$$

is undefined at $x=3$. Its real domain is therefore

$$
\mathbb{R}\setminus\{3\}.
$$

Similarly, the real expression $\sqrt{x-2}$ requires $x\geq2$. Restrictions should be recorded before simplifying or solving expressions that contain denominators or even roots.

## 3. Expressions, equations, identities, and inequalities

These four objects must not be confused.

- An **expression** represents a value, such as $3x-7$.
- An **equation** states that two expressions are equal, such as $3x-7=8$.
- An **identity** is an equality true for every value in the stated domain, such as $(x+1)^2=x^2+2x+1$ for all real $x$.
- An **inequality** compares expressions, such as $3x-7>8$.

An expression does not have a truth value by itself. An equation or inequality makes a claim whose truth may depend on the variable values.

### Example 1 — Classifying mathematical statements

1. $4x+9$ is an expression.
2. $4x+9=21$ is an equation.
3. $4(x+2)=4x+8$ is an identity over $\mathbb{R}$.
4. $4x+9\leq21$ is an inequality.

## 4. Terms, coefficients, factors, and exponents

A **term** is a part of an expression separated from other terms by addition or subtraction at the outermost level.

Consider

$$
7x^3-4x+9.
$$

Its terms are $7x^3$, $-4x$, and $9$.

- The **coefficient** of $x^3$ is $7$.
- The coefficient of $x$ is $-4$.
- The constant term is $9$.
- In $7x^3$, the factors are $7$, $x$, $x$, and $x$ when the exponent is a positive integer.
- The exponent of $x$ in $7x^3$ is $3$.

A coefficient may be negative, fractional, or irrational. The coefficient of $x$ in $\frac{2}{3}x$ is $\frac{2}{3}$; the coefficient of $x$ in $-\sqrt{5}x$ is $-\sqrt{5}$.

### 4.1 Implied coefficients and factors

When no coefficient is written, the coefficient is understood to be $1$ or $-1$:

$$
x=1x,\qquad -x=(-1)x.
$$

When multiplication is written by adjacency, as in $3xy$, the expression means $3\cdot x\cdot y$.

The notation $ab$ ordinarily means the product of $a$ and $b$, not a two-digit number. Context distinguishes algebraic multiplication from numeral notation.

### 4.2 Grouping symbols

Parentheses, brackets, and braces can all group expressions. For example,

$$
2\bigl[3x-(x-4)\bigr]
$$

means twice the entire bracketed quantity. Grouping symbols determine which operations belong together and should be preserved until the expression is evaluated or expanded carefully.

## 5. Evaluating an expression

To **evaluate** an expression, substitute the given values for its variables and then calculate using the order of operations.

For example, evaluate

$$
2x^2-3y+1
$$

at $x=-2$ and $y=5$.

Substitute first:

$$
2(-2)^2-3(5)+1.
$$

Then evaluate the exponent, multiplication, and addition/subtraction:

$$
2(4)-15+1=8-15+1=-6.
$$

The answer is $-6$.

### 5.1 Negative bases and parentheses

The expressions $(-3)^2$ and $-3^2$ are different:

$$
(-3)^2=9,\qquad -3^2=-(3^2)=-9.
$$

Parentheses show whether the negative sign is part of the base. This distinction becomes essential when substituting negative values into powers.

### 5.2 Substitution into formulas

Suppose a rectangle has length $L$ and width $W$. Its perimeter is

$$
P=2L+2W.
$$

For $L=8.5$ cm and $W=3$ cm,

$$
P=2(8.5)+2(3)=17+6=23\text{ cm}.
$$

Units are part of the interpretation: the numerical result is a perimeter measured in centimetres.

## 6. Translating verbal statements

Algebraic translation requires attention to word order and grouping. A phrase should be translated by identifying the operation and the quantity to which it applies.

| Verbal statement | Algebraic expression |
|---|---|
| Five more than $x$ | $x+5$ |
| Five less than $x$ | $x-5$ |
| Five less than twice $x$ | $2x-5$ |
| Twice the quantity $x-5$ | $2(x-5)$ |
| The quotient of $x$ and $4$ | $\frac{x}{4}$ |
| The square of the sum of $x$ and $3$ | $(x+3)^2$ |
| The sum of the squares of $x$ and $3$ | $x^2+3^2$ |

The last two expressions are not the same. Grouping is part of the meaning.

### Example 2 — Translating a contextual statement

A gym charges a registration fee of 18 dollars and a monthly fee of 24 dollars. Let $m$ denote the number of months.

The total cost is

$$
C(m)=18+24m,
$$

where $m$ is a nonnegative integer if only complete monthly charges are counted. For $m=5$,

$$
C(5)=18+24(5)=138.
$$

The model gives a total cost of 138 dollars for five months. The domain assumption is part of the model, not an optional detail.

### 6.1 Ambiguous language

Some verbal statements are ambiguous without context. “Half of a number increased by 6” may be interpreted as $\frac{x}{2}+6$ or, depending on the intended grouping, $\frac{x+6}{2}$. A good mathematical model states the intended meaning in words and uses parentheses when needed.

## 7. Like terms and simplifying sums

Two terms are **like terms** when they have exactly the same variable part, including the same variables raised to the same exponents. Their coefficients may differ.

Examples:

- $3x^2$ and $-8x^2$ are like terms.
- $4ab$ and $-\frac12ab$ are like terms.
- $5x$ and $5x^2$ are not like terms.
- $2xy$ and $2x$ are not like terms.

Like terms can be combined by adding their coefficients:

$$
3x^2-8x^2=-5x^2.
$$

This is justified by the distributive property:

$$
3x^2-8x^2=(3-8)x^2=-5x^2.
$$

### Example 3 — Simplifying an expression

Simplify

$$
5a-3b+2a+7b-4.
$$

Group like terms:

$$
(5a+2a)+(-3b+7b)-4.
$$

Add the coefficients:

$$
7a+4b-4.
$$

The expression $7a+4b-4$ is equivalent to the original expression for every real $a$ and $b$.

### Common error

It is invalid to combine unlike terms as if they had the same variable part. For example,

$$
3x+2x^2
$$

cannot be simplified to $5x^3$ or $5x^2$. The terms represent different powers of the variable.

## 8. The distributive property

For real numbers $a$, $b$, and $c$, multiplication distributes over addition:

$$
a(b+c)=ab+ac.
$$

It also distributes over subtraction:

$$
a(b-c)=ab-ac.
$$

The factor outside the parentheses multiplies **every** term inside them.

### Example 4 — Expanding an expression

Expand

$$
-3(2x-5).
$$

Distribute $-3$ to both terms:

$$
-3(2x)-3(-5)=-6x+15.
$$

The result is $-6x+15$.

### Example 5 — Factoring by reversing distribution

Factor

$$
12x+18.
$$

The greatest common factor of $12$ and $18$ is $6$. Extract it:

$$
12x+18=6(2x+3).
$$

Expanding the factored expression returns the original expression, confirming the equality.

## 9. Equivalent expressions

Two expressions are **equivalent on a domain** if they have the same value for every input in that domain.

For example,

$$
2(x+4)\quad\text{and}\quad 2x+8
$$

are equivalent for all real $x$ because of the distributive property.

Domain language matters. The expressions

$$
\frac{x^2-1}{x-1}\quad\text{and}\quad x+1
$$

are equal whenever $x\ne1$, since

$$
\frac{(x-1)(x+1)}{x-1}=x+1\qquad (x\ne1).
$$

However, their original domains are not identical: the rational expression is undefined at $x=1$, while $x+1$ is defined there. Therefore, they are equivalent on the restricted domain $\mathbb{R}\setminus\{1\}$, but they are not the same partially defined expression on all of $\mathbb{R}$.

This distinction will become important in later chapters on rational expressions and equations.

## 10. Why algebraic transformations are valid

The simplifications in this chapter rely on properties of addition and multiplication in the real numbers. For example, combining like terms uses associativity and commutativity to regroup addends, while expanding or factoring uses the distributive property. These are not arbitrary symbol-manipulation rules: they preserve the value of an expression for every admissible input.

The next chapter develops the real-number properties more systematically, including additive and multiplicative inverses, sign rules, order properties, rational arithmetic, and the restrictions attached to division. Foundations, Chapter 04, establishes the underlying number system; Algebra Chapter 02 focuses on using its properties in calculations.

## 11. Python implementation

Python can evaluate a formula after values are assigned to its variables. In educational code, write the expression explicitly as a function. Do not use `eval` on arbitrary text supplied by a user.

```python
from math import isclose


def evaluate_expression(x: float, y: float) -> float:
    """Evaluate 2*x**2 - 3*y + 1 for real inputs x and y."""
    return 2 * x**2 - 3 * y + 1


def simplify_like_terms(a: float, b: float, c: float, d: float) -> tuple[float, float]:
    """Return coefficients for (a*x + b*y) + (c*x + d*y)."""
    return a + c, b + d


# Example 1: numerical evaluation
value = evaluate_expression(-2, 5)
assert value == -6

# Example 2: combine the x-terms and y-terms
x_coefficient, y_coefficient = simplify_like_terms(5, -3, 2, 7)
assert (x_coefficient, y_coefficient) == (7, 4)

# Example 3: check the distributive identity numerically for chosen values.
# This is an experiment for selected values, not a proof for all real values.
for a in (-3, 0, 2.5):
    for b in (-4, 1, 7):
        for c in (-2, 0, 3.5):
            left = a * (b + c)
            right = a * b + a * c
            assert isclose(left, right, rel_tol=1e-12, abs_tol=1e-12)

print("All Chapter 01 examples passed.")
```

### 11.1 Interpreting the experiment

The numerical checks can catch implementation mistakes and illustrate a property. They do not prove the distributive property for every real number. Its general validity comes from the algebraic structure of the real numbers, not from testing finitely many inputs.

## 12. Worked examples

### Example 6 — Evaluate with negative inputs

Evaluate $3x-2y^2$ for $x=-4$ and $y=-3$.

Substitute with parentheses:

$$
3(-4)-2(-3)^2.
$$

Evaluate the exponent first:

$$
-12-2(9)=-12-18=-30.
$$

### Example 7 — Translate and simplify

“Four more than three times a number, decreased by twice the number.”

Let the number be $x$. The phrase becomes

$$
(3x+4)-2x.
$$

Combine like terms:

$$
x+4.
$$

The result is $x+4$.

### Example 8 — Compare two possible groupings

A number $x$ is increased by 8, and the result is multiplied by 3. The expression is

$$
3(x+8)=3x+24.
$$

This differs from increasing three times the number by 8:

$$
3x+8.
$$

The verbal grouping determines which expression is correct.

### Example 9 — Identify a domain restriction

Consider

$$
E(x)=\frac{x+2}{x-5}+1.
$$

The denominator cannot be zero, so $x\ne5$. The domain is $\mathbb{R}\setminus\{5\}$. This restriction must be retained even if later algebraic simplification changes the appearance of the expression.

## 13. Common errors and how to avoid them

| Incorrect approach | Why it is incorrect | Better approach |
|---|---|---|
| $-(x-4)=-x-4$ | The negative sign must distribute to both terms. | $-(x-4)=-x+4$ |
| $2(x+3)=2x+3$ | The factor 2 must multiply every term. | $2(x+3)=2x+6$ |
| $x+x^2=2x^2$ | The terms are not like terms. | Leave the sum as $x^2+x$. |
| $(-5)^2=-25$ | The square of a negative number is positive. | $(-5)^2=25$ |
| Cancel $x$ in $\frac{x+2}{x}$ as if it were a factor of the whole numerator. | Cancellation applies to common factors, not individual terms in a sum. | For $x\ne0$, write $\frac{x+2}{x}=1+\frac2x$. |

## 14. Exercises

### A. Concepts

1. Classify each item as an expression, equation, identity, or inequality: (a) $5x-2$; (b) $5x-2=13$; (c) $2(x+1)=2x+2$; (d) $5x-2<13$.
2. In $-6p^3+4p-11$, identify all terms, the coefficient of $p^3$, the coefficient of $p$, and the constant term.
3. Explain why $4x$ and $4x^2$ are not like terms.
4. State the real domain of $\frac{3}{x+7}$ and of $\sqrt{2x-6}$.

### B. Skills

5. Evaluate $4a^2-3b+2$ for $a=-2$ and $b=5$.
6. Simplify $8x-3y-5x+9y+4$.
7. Expand $-4(3x-2)$.
8. Factor $15x+25$ using the greatest common factor.
9. Translate: “Seven less than twice the sum of $x$ and 4.”
10. Are $\frac{x^2-9}{x-3}$ and $x+3$ equivalent on their common domain? State that domain.

### C. Reasoning and applications

11. A delivery service charges a fixed fee of 6 dollars plus 1.75 dollars per kilometre. Write a formula for the cost $C(d)$ of a delivery of $d$ kilometres and state a reasonable domain for $d$.
12. A student claims that $3(x+2)=3x+2$. Give a counterexample by selecting a value of $x$, then show the correct expansion.
13. Explain why checking the distributive property for one hundred numerical examples does not constitute a proof for all real numbers.
14. Construct two different verbal statements that correspond to $2x+5$ and $2(x+5)$, and explain the difference.

### Selected answers

1. (a) expression; (b) equation; (c) identity; (d) inequality.
2. Terms: $-6p^3$, $4p$, $-11$; coefficients: $-6$ and $4$; constant: $-11$.
3. Their variable parts have different exponents.
4. First: $\mathbb{R}\setminus\{-7\}$. Second: $[3,\infty)$.
5. $3$.
6. $3x+6y+4$.
7. $-12x+8$.
8. $5(3x+5)$.
9. $2(x+4)-7$.
10. Yes, on $\mathbb{R}\setminus\{3\}$.
11. $C(d)=6+1.75d$, with $d\geq0$ (and a more specific domain may be required by the service's billing policy).
12. For example, at $x=0$, the left side is 6 and the claimed right side is 2. Correctly, $3(x+2)=3x+6$.

## 15. Chapter summary

- Variables represent values from a specified domain; constants and parameters are fixed within a particular context.
- Expressions denote values; equations, identities, and inequalities make claims.
- Terms with identical variable parts are like terms and can be combined by adding their coefficients.
- The distributive property explains expansion and factoring.
- Equivalent expressions must be compared on a stated domain.
- Algebraic transformations must respect conditions such as nonzero denominators and nonnegative radicands.
- Python experiments can illustrate properties but do not replace general proofs.

## 16. References

1. Marecek, L., Anthony-Smith, M., and Mathis, A. H. *Elementary Algebra 2e*. OpenStax, Rice University.
2. Marecek, L., Anthony-Smith, M., and Mathis, A. H. *Intermediate Algebra 2e*. OpenStax, Rice University.
3. Math-Atlas, **Foundations**, especially Chapters 03, 04, 05, and 07, and `MATHEMATICAL_CONVENTIONS.MD`.

**Next chapter:** Chapter 02 — Real-Number Properties and Algebraic Simplification.
