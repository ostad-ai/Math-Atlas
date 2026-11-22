# Algebra 02 — Real-Number Properties and Algebraic Simplification

## 1. Introduction

Algebraic simplification is not a collection of visual tricks. Each valid step follows from a property of the real numbers, a definition of an operation, or a stated restriction on the values involved. This chapter develops the numerical rules that will be used repeatedly when simplifying expressions and, in the next chapter, solving equations.

Foundations, Chapter 04, establishes that the real numbers form a complete ordered field. We will use the field and order properties established there rather than re-proving the full structure. The purpose here is operational: understand exactly which rule justifies a calculation, when a rule is valid, and how to preserve restrictions on the domain.

This chapter focuses on real-number arithmetic, signs, rational numbers, order of operations, absolute value as distance, and simplification of numerical and algebraic expressions. It does **not** yet develop general equation-solving procedures; those belong to Chapter 03.

### Learning objectives

By the end of this chapter, a learner should be able to:

- Identify and use the field properties of addition and multiplication of real numbers.
- Explain the sign rules for negative numbers from the properties of zero, additive inverses, and multiplication.
- Apply the order properties of the real numbers, including the reversal of an inequality when multiplying by a negative number.
- Add, subtract, multiply, and divide rational numbers exactly.
- Apply the order of operations while distinguishing a negative sign from a negative base.
- Simplify expressions with nested grouping symbols and rational coefficients.
- Use absolute value to describe magnitude and distance on the real line.
- Preserve domain restrictions when simplifying expressions containing denominators.
- Use Python's `Fraction` type for exact rational arithmetic and distinguish exact values from floating-point approximations.

## 2. The real numbers as an ordered field

The real-number system and its construction are discussed in Foundations, Chapter 04. For elementary algebra, the most useful summary is that the real numbers, denoted by $\mathbb{R}$, support addition, subtraction, multiplication, and division by nonzero numbers, and they have an order compatible with these operations.

The following properties are the rules behind ordinary algebraic rearrangement. Here $a$, $b$, and $c$ denote arbitrary real numbers unless a condition is stated.

### 2.1 Properties of addition

| Property | Rule | Meaning |
|---|---|---|
| Closure | $a+b\in\mathbb{R}$ | The sum of two real numbers is real. |
| Commutative property | $a+b=b+a$ | The order of addends does not matter. |
| Associative property | $(a+b)+c=a+(b+c)$ | The grouping of addends does not matter. |
| Additive identity | $a+0=a$ | Zero leaves a number unchanged under addition. |
| Additive inverse | $a+(-a)=0$ | Every real number has an additive opposite. |

Subtraction is defined through addition and the additive inverse:

$$
a-b:=a+(-b).
$$

This definition explains why subtracting a number is equivalent to adding its opposite. For example,

$$
8-(-3)=8+3=11.
$$

### 2.2 Properties of multiplication

| Property | Rule | Meaning |
|---|---|---|
| Closure | $ab\in\mathbb{R}$ | The product of two real numbers is real. |
| Commutative property | $ab=ba$ | The order of factors does not matter. |
| Associative property | $(ab)c=a(bc)$ | The grouping of factors does not matter. |
| Multiplicative identity | $a\cdot1=a$ | One leaves a number unchanged under multiplication. |
| Multiplicative inverse | $a\cdot a^{-1}=1$, for $a\ne0$ | Every nonzero real number has a reciprocal. |

Division by a nonzero number is multiplication by its reciprocal:

$$
\frac{a}{b}:=a\cdot b^{-1},\qquad b\ne0.
$$

Division by zero is undefined. The restriction is part of the operation, not an optional convention.

### 2.3 The distributive property

Multiplication distributes over addition:

$$
a(b+c)=ab+ac.
$$

It also distributes over subtraction:

$$
a(b-c)=ab-ac.
$$

The distributive property links addition and multiplication. It justifies both expansion and factoring. For example,

$$
4(x+3)=4x+12
$$

and, in the reverse direction,

$$
4x+12=4(x+3).
$$

The reverse direction is often called factoring out a common factor. Chapter 01 introduced the distributive property in the context of expressions; here we use it together with rational coefficients and sign rules.

### 2.4 Zero and multiplication

For every real number $a$,

$$
a\cdot0=0\quad\text{and}\quad 0\cdot a=0.
$$

One short derivation uses distributivity:

$$
a\cdot0=a(0+0)=a\cdot0+a\cdot0.
$$

Subtracting $a\cdot0$ from both sides gives $a\cdot0=0$. Since multiplication is commutative in $\mathbb{R}$, the corresponding result for $0\cdot a$ follows as well.

A second consequence is the **zero-product property**: if $ab=0$, then $a=0$ or $b=0$. Indeed, if $a\ne0$, multiply both sides by $a^{-1}$ to obtain $b=0$. The zero-product property will be especially useful when factoring equations in Chapter 09; here it is introduced as a property of real-number multiplication.

## 3. Negative numbers and sign rules

A negative number is the additive inverse of a positive number. The notation $-a$ means the additive inverse of $a$; it does not mean that $a$ itself must be positive.

### 3.1 The negative of a negative

The additive inverse of $-a$ is $a$, because

$$
(-a)+a=0.
$$

Therefore,

$$
-(-a)=a.
$$

For example, $-(-9)=9$.

### 3.2 Why a negative times a positive is negative

First note that $-1$ is the additive inverse of $1$. By distributivity,

$$
a+(-1)a=(1+(-1))a=0a=0.
$$

Thus $(-1)a$ is the additive inverse of $a$, so

$$
(-1)a=-a.
$$

More generally,

$$
(-a)b=-(ab),\qquad a(-b)=-(ab).
$$

### 3.3 Why a negative times a negative is positive

Using the previous rule twice,

$$
(-a)(-b)=-\big(a(-b)\big)=-\big(-(ab)\big)=ab.
$$

This derives the familiar sign rules rather than asking the learner to memorize them without explanation.

| First factor | Second factor | Sign of product |
|---|---|---|
| positive | positive | positive |
| positive | negative | negative |
| negative | positive | negative |
| negative | negative | positive |

For a quotient with nonzero denominator, the same sign pattern applies because division is multiplication by a reciprocal.

### Example 1 — Calculate with signed numbers

Evaluate

$$
(-6)(-4)+(-18)\div 3.
$$

Evaluate multiplication and division before addition:

$$
24+(-6)=18.
$$

The result is $18$.

### 3.4 Opposite of a sum or difference

The additive inverse of a sum is the sum of the additive inverses:

$$
-(a+b)=(-a)+(-b)=-a-b.
$$

Likewise,

$$
-(a-b)=-a+b.
$$

This is why a minus sign immediately outside parentheses changes the sign of every term inside:

$$
-(3x-5)=-3x+5.
$$

A common error is to change only the first term. The sign applies to the entire grouped expression.

## 4. Order properties of the real numbers

The order relation $ < $ compares real numbers. The rules below are consequences of the ordered-field structure established in Foundations, Chapter 04. The same properties apply to the corresponding non-strict and reverse inequalities.

### 4.1 Adding the same number preserves order

If $a < b$, then for every real number $c$,

$$
a+c < b+c.
$$

Adding the same signed amount translates both points on the number line equally and does not change which one is greater. More precisely, the transformation is reversible:

$$
a < b\quad\Longleftrightarrow\quad a+c < b+c.
$$

For example, since $-2 < 5$, adding $7$ to both sides gives

$$
-2+7 < 5+7,
$$

and therefore

$$
5 < 12.
$$

### 4.2 Multiplying by a positive number preserves order

If $a < b$ and $c > 0$, then

$$
ac < bc.
$$

For a fixed positive multiplier, the transformation is reversible:

$$
a < b \quad\Longleftrightarrow\quad ac < bc \qquad(c > 0).
$$

A positive scaling preserves the direction of the order. For example, since $2 < 6$, multiplying both sides by $3$ gives

$$
2\cdot3 < 6\cdot3,
$$

so $6 < 18$.

### 4.3 Multiplying by a negative number reverses order

If $a < b$ and $c < 0$, then

$$
ac > bc.
$$

For a fixed negative multiplier, the transformation is reversible with the inequality direction reversed:

$$
a < b \quad\Longleftrightarrow\quad ac > bc \qquad(c < 0).
$$

The direction reverses. To see why, write $c=-d$ where $d > 0$. From $a < b$, multiplication by $d$ gives $ad < bd$. Taking additive inverses reverses the order, so $-ad > -bd$. These are exactly $ac > bc$.

For example, since $2 < 6$, multiplying both sides by $-3$ gives

$$
2(-3) > 6(-3),
$$

and therefore

$$
-6 > -18.
$$

This rule is essential when solving inequalities in Chapter 04. It is not valid to multiply an inequality by a negative number while leaving its direction unchanged.
### 4.4 Reciprocal order for positive numbers

If $0 < a < b$, then

$$
\frac{1}{a} > \frac{1}{b}.
$$

The reciprocal function reverses order on the positive real numbers. To see this, multiply $a < b$ by the positive number $1/(ab)$; the result is $1/b < 1/a$. This statement requires both numbers to be positive; it should not be applied without checking signs.

### Common error

From $2 < 7$, a learner writes $-2 < -7$. This is false. Multiplying by $-1$ reverses the inequality:

$$
-2 > -7.
$$

## 5. Fractions and rational arithmetic

A rational number is a real number expressible as $\frac{a}{b}$, where $a,b\in\mathbb{Z}$ and $b\ne0$. Foundations, Chapter 04, develops the rational numbers as a number system. This section focuses on accurate arithmetic with fractions, which appear constantly as algebraic coefficients.

### 5.1 Equivalent fractions

If $c\ne0$, then

$$
\frac{a}{b}=\frac{ac}{bc},\qquad b\ne0.
$$

The numerator and denominator are multiplied by the same nonzero number, so the value does not change. For integer fractions, simplification usually divides the numerator and denominator by a common nonzero integer factor.

For example,

$$
\frac{42}{56}=\frac{42\div14}{56\div14}=\frac34.
$$

The fraction $\frac34$ is in lowest terms because 3 and 4 have no common positive factor other than 1.

### 5.2 Addition and subtraction

Fractions must have a common denominator before their numerators are combined:

$$
\frac{a}{b}+\frac{c}{d}=\frac{ad+bc}{bd},\qquad b\ne0,\ d\ne0.
$$

The common denominator $bd$ is always valid under the stated nonzero conditions, although using the least common denominator may keep the arithmetic smaller.

**Example 2 — Add fractions**

$$
\frac56-\frac38
=\frac{20}{24}-\frac9{24}
=\frac{11}{24}.
$$

The numerators are subtracted only after the denominators agree.

### 5.3 Multiplication

Multiply numerators and denominators:

$$
\frac{a}{b}\cdot\frac{c}{d}=\frac{ac}{bd},\qquad b\ne0,\ d\ne0.
$$

For example,

$$
\frac{14}{15}\cdot\frac{25}{21}
=\frac{2\cdot5}{3\cdot3}
=\frac{10}{9}.
$$

Cross-cancellation may simplify the arithmetic before multiplication, but it is valid only for common **factors**, not terms in a sum.

### 5.4 Division

Dividing by a nonzero fraction means multiplying by its reciprocal:

$$
\frac{a}{b}\div\frac{c}{d}
=\frac{a}{b}\cdot\frac{d}{c}
=\frac{ad}{bc},
$$

where $b\ne0$, $d\ne0$, and $c\ne0$. The final condition says that the fraction being used as the divisor is not zero.

**Example 3 — Divide fractions**

$$
\frac79\div\frac{14}{15}
=\frac79\cdot\frac{15}{14}
=\frac56.
$$

### 5.5 Signs in fractions

A negative sign may be placed in front of a fraction or in exactly one of its numerator or denominator positions:

$$
-\frac ab=\frac{-a}{b}=\frac{a}{-b},\qquad b\ne0.
$$

If both numerator and denominator are negative, the fraction is positive:

$$
\frac{-a}{-b}=\frac ab,\qquad b\ne0.
$$

Writing one negative sign in front of a fraction is usually clearest.

### 5.6 Algebraic fractions: restrictions come first

The same nonzero-denominator rule applies when a denominator contains a variable. Consider

$$
\frac{6x}{9x}.
$$

The original expression is defined only when $x\ne0$. For those values,

$$
\frac{6x}{9x}=\frac23.
$$

The simplified expression $\frac23$ is defined for every real number, but it does **not** erase the restriction of the original expression. The two expressions agree on the original domain $\mathbb{R}\setminus\{0\}$; they are not identical as partially defined expressions over all of $\mathbb{R}$.

This principle becomes central in Chapter 10 on rational expressions and equations.

## 6. Order of operations and grouping

The order-of-operations convention gives a consistent way to interpret an expression. It does not replace grouping symbols: parentheses, brackets, and fraction bars define which parts belong together.

A reliable procedure is:

1. Evaluate grouped expressions from the innermost grouping outward.
2. Evaluate exponents.
3. Apply unary signs according to the expression's written structure.
4. Perform multiplication and division from left to right.
5. Perform addition and subtraction from left to right.

Multiplication and division have equal precedence; addition and subtraction also have equal precedence. The left-to-right rule applies within each pair.

### 6.1 A negative sign is not automatically part of the base

Compare

$$
-3^2=-(3^2)=-9
$$

with

$$
(-3)^2=(-3)(-3)=9.
$$

Parentheses determine whether the negative sign belongs to the base.

### 6.2 Multiplication and division are evaluated left to right

For example,

$$
24\div 6\cdot2=4\cdot2=8,
$$

not $24\div(6\cdot2)$. If the latter is intended, parentheses must be written explicitly:

$$
24\div(6\cdot2)=2.
$$

### 6.3 Fraction bars act as grouping symbols

The expression

$$
\frac{2+6}{4-2}
$$

means that the entire numerator $2+6$ is divided by the entire denominator $4-2$:

$$
\frac{8}{2}=4.
$$

By contrast, $2+6\div4-2$ is a different expression. When typing formulas in plain text, use parentheses to make numerator and denominator boundaries explicit.

**Example 4 — Evaluate a nested expression**

Evaluate

$$
18-2\left(3^2-5\right)\div2.
$$

First evaluate the exponent and the parentheses:

$$
18-2(9-5)\div2=18-2(4)\div2.
$$

Then multiplication and division from left to right:

$$
18-8\div2=18-4=14.
$$

## 7. Simplifying numerical and algebraic expressions

An expression is simplified relative to a purpose and a set of conventions. In elementary algebra, a useful standard form often has numerical coefficients, combined like terms, and no unnecessary grouping. There may be more than one correct simplified form.

### 7.1 Combine like terms

Terms are like terms when their variable parts are identical. Their coefficients may be added or subtracted:

$$
\frac23x-\frac56x
=\left(\frac23-\frac56\right)x
=\left(\frac46-\frac56\right)x
=-\frac16x.
$$

The variable part is unchanged; only the coefficients are combined.

Terms such as $x^2$ and $x$ are not like terms, so $3x^2+2x$ cannot be combined into a single term using addition.

### 7.2 Use distribution carefully

Simplify

$$
2(3x-4)-3(x+1).
$$

Distribute each factor across every term in its parentheses:

$$
6x-8-3x-3.
$$

Combine like terms:

$$
3x-11.
$$

The negative factor $-3$ changes the signs of both terms in $x+1$.

### 7.3 Nested grouping and subtraction

Simplify

$$
5-[2-(3-7)].
$$

Work from the innermost grouping:

$$
3-7=-4,
$$

so

$$
5-[2-(-4)]=5-[2+4]=5-6=-1.
$$

Alternatively, the minus sign before a bracket can be distributed by taking the additive inverse of every term inside. Both methods must give the same result.

### 7.4 Simplify with rational coefficients

Simplify

$$
\frac34x-\frac23+\frac56x+\frac16.
$$

Group like terms:

$$
\left(\frac34+\frac56\right)x+\left(-\frac23+\frac16\right).
$$

Use common denominators:

$$
\left(\frac9{12}+\frac{10}{12}\right)x
+\left(-\frac46+\frac16\right)
=\frac{19}{12}x-\frac12.
$$

### 7.5 Factoring out a numerical common factor

The distributive property also lets us write an expression as a product. For example,

$$
12x-18=6(2x-3).
$$

The factor 6 is a common factor of both terms. Factoring may make later calculations easier, but it does not by itself solve an equation.

## 8. Absolute value as magnitude and distance

For a real number $a$, its absolute value is defined by

$$
|a|=\begin{cases}
a,&a\geq0,\\
-a,&a < 0.
\end{cases}
$$

Absolute value is always nonnegative. It measures the distance from the number to zero on the real line:

$$
|a|\geq0,\qquad |a|=0\iff a=0.
$$

For example, $|7|=7$ and $|-7|=7$. The values 7 and -7 are different real numbers, but they are the same distance from zero.

More generally, the distance between two real numbers $a$ and $b$ is

$$
|a-b|.
$$

For instance, the distance between -2 and 5 is

$$
|-2-5|=|-7|=7.
$$

Useful properties include

$$
|ab|=|a||b|,\qquad
\left|\frac ab\right|=\frac{|a|}{|b|}\quad(b\ne0),
$$

and the triangle inequality

$$
|a+b|\leq|a|+|b|.
$$

The triangle inequality says that the direct distance represented by $|a+b|$ cannot exceed the sum of the two magnitudes. A short proof follows from the definition of absolute value. We know

$$
-|a|\leq a\leq |a|\quad\text{and}\quad -|b|\leq b\leq |b|.
$$

Adding the left inequalities and the right inequalities gives

$$
-(|a|+|b|)\leq a+b\leq |a|+|b|.
$$

A real number lying between $-M$ and $M$, with $M\geq0$, has absolute value at most $M$. Therefore $|a+b|\leq|a|+|b|$. The inequality will also be useful later in more advanced mathematics.

This chapter uses absolute value to describe magnitude and distance only. Solving absolute-value equations and inequalities is covered in Chapter 04.

## 9. Exact values and decimal approximations

A rational number such as $\frac17$ has an exact value. Its decimal expansion is repeating:

$$
\frac17=0.\overline{142857}.
$$

A finite decimal such as $0.125$ is also exact and rational:

$$
0.125=\frac18.
$$

A decimal produced by a calculator may instead be an approximation to an irrational value. For example,

$$
\sqrt2\approx1.41421356.
$$

The approximation symbol matters: $1.41421356$ is not exactly equal to $\sqrt2$.

When a problem asks for an exact answer, preserve fractions and radicals rather than converting them prematurely to decimals. When an approximation is needed, state an appropriate precision or tolerance.

## 10. Common errors and how to avoid them

| Incorrect approach | Why it fails | Correct principle |
|---|---|---|
| $-(a-b)=-a-b$ | The negative applies to both terms in the group. | $-(a-b)=-a+b$ |
| $(-a)^2=-a^2$ | The negative sign is part of the base on the left. | $(-a)^2=a^2$ and $-a^2=-(a^2)$ |
| $\frac ab+\frac cd=\frac{a+c}{b+d}$ | Numerators and denominators cannot be added separately. | Use a common denominator. |
| Cancel a term across addition, as in $\frac{x+3}{x}=3$ | Cancellation applies to common factors, not individual terms in a sum. | For $x\ne0$, write $\frac{x+3}{x}=1+\frac3x$. |
| Multiply an inequality by a negative number without reversing its direction. | Negative scaling reverses order. | Reverse $ < $ to $ > $ (or vice versa). |
| Replace $\frac{6x}{9x}$ by $\frac23$ and allow $x=0$. | The original expression is undefined at zero. | Retain the original restriction $x\ne0$. |
| Read $24\div6\cdot2$ as $24\div(6\cdot2)$. | Multiplication and division have equal precedence. | Evaluate left to right unless parentheses state otherwise. |

## 11. Python: exact rational arithmetic

Python's built-in `float` type stores binary floating-point approximations. For fractions that must remain exact, the standard-library class `fractions.Fraction` is more appropriate. Construct fractions from integers or strings; constructing `Fraction` from a floating-point number can preserve the float's binary approximation rather than the intended decimal fraction.

### 11.1 Exact fraction operations

```python
from fractions import Fraction

first = Fraction(5, 6)
second = Fraction(3, 8)

sum_value = first + second
product_value = first * second
quotient_value = first / second

assert sum_value == Fraction(29, 24)
assert product_value == Fraction(5, 16)
assert quotient_value == Fraction(20, 9)

print(sum_value, product_value, quotient_value)
```

The results are exact rational numbers. `Fraction` automatically reduces them to lowest terms.

### 11.2 Simplify a linear expression with rational coefficients

The expression

$$
\frac34x-\frac23+\frac56x+\frac16
$$

has simplified form $\frac{19}{12}x-\frac12$. We can verify the coefficient arithmetic exactly:

```python
from fractions import Fraction

x_coefficient = Fraction(3, 4) + Fraction(5, 6)
constant = -Fraction(2, 3) + Fraction(1, 6)

assert x_coefficient == Fraction(19, 12)
assert constant == Fraction(-1, 2)

print(f"{x_coefficient}*x + ({constant})")
```

This code verifies the rational arithmetic used in the derivation. The algebraic grouping of like terms is justified by the distributive property and the associative and commutative properties, not by the program.

### 11.3 Compare exact fractions with floating-point values

```python
from fractions import Fraction

exact_tenth = Fraction(1, 10)
from_decimal_text = Fraction("0.1")
from_float = Fraction(0.1)

assert exact_tenth == from_decimal_text
assert exact_tenth != from_float

print("Exact rational:", exact_tenth)
print("From decimal text:", from_decimal_text)
print("From binary float:", from_float)
```

The final value is a fraction with a large denominator because it represents the exact binary floating-point value stored for `0.1`, not the intended exact decimal fraction one tenth.

### 11.4 A safe numerical check of the distributive property

```python
from fractions import Fraction

values = [Fraction(-3, 2), Fraction(0), Fraction(5, 4)]

for a in values:
    for b in values:
        for c in values:
            left = a * (b + c)
            right = a * b + a * c
            assert left == right

print("All selected exact-rational checks passed.")
```

This finite test checks selected rational inputs exactly. It is an experiment, not a proof for every real number. The general distributive property is a property of the real-number field.

### 11.5 A note about integer division in Python

Python's `//` operator performs floor division, not truncation toward zero. For example, `-7 // 3` is `-3`, because -3 is the greatest integer less than or equal to $-7/3$. By contrast, ordinary algebraic division gives the rational number $-7/3$. Use `/` for ordinary division and `Fraction` when exact rational results are required.

## 12. Worked examples

### Example 5 — Simplify an expression with signs

Simplify

$$
-2(4x-3)+5(x-2).
$$

Distribute each factor:

$$
-8x+6+5x-10.
$$

Combine like terms:

$$
-3x-4.
$$

### Example 6 — Evaluate a mixed numerical expression

Evaluate

$$
\frac34-\left(\frac12-\frac56\right)\cdot3.
$$

First evaluate the parentheses:

$$
\frac12-\frac56=\frac36-\frac56=-\frac13.
$$

Then multiply and subtract:

$$
\frac34-\left(-\frac13\right)3
=\frac34-(-1)
=\frac74.
$$

### Example 7 — Keep a domain restriction after simplification

Simplify the expression

$$
\frac{x^2-4}{x-2}.
$$

Factor the numerator:

$$
\frac{(x-2)(x+2)}{x-2}.
$$

Cancellation is permitted only when $x-2\ne0$, so $x\ne2$. On that domain, the expression equals

$$
x+2,\qquad x\ne2.
$$

The simplified formula does not make the original expression defined at $x=2$.

### Example 8 — Compare order after multiplication

Given $-4 < 1$, multiply both sides by $-2$. Because the multiplier is negative, reverse the inequality:

$$
8 > -2.
$$

A quick numerical check confirms the direction. The rule itself follows from the ordered-field properties, not merely from this example.

### Example 9 — Interpret absolute value as distance

Find all real numbers whose distance from 3 is 5. This is a distance statement:

$$
|x-3|=5.
$$

The two points are 5 units to the left and right of 3:

$$
x=-2\quad\text{or}\quad x=8.
$$

This example previews the absolute-value equations developed in Chapter 04; a systematic solution method is deferred there.

## 13. Exercises

### A. Concepts and properties

1. State the property used in each step: (a) $a+(-a)=0$; (b) $a(b+c)=ab+ac$; (c) $a+0=a$; (d) $a\cdot a^{-1}=1$ for $a\ne0$.
2. Explain why division by zero is undefined in the real-number system.
3. Derive $(-a)(-b)=ab$ using additive inverses and distributivity.
4. If $a < b$, state what happens to the inequality when both sides are (a) increased by 4, (b) multiplied by 3, and (c) multiplied by -3.
5. Explain why $\frac{x+4}{x}=4$ is not a valid simplification in general.

### B. Numerical skills

6. Evaluate $-5^2+(-5)^2$.
7. Evaluate $20-3(2^3-5)\div3$.
8. Calculate $\frac7{12}+\frac5{18}$ and give the result in lowest terms.
9. Calculate $\frac{15}{28}\cdot\frac{14}{25}$.
10. Calculate $\frac89\div\frac4{15}$.
11. Simplify $-\frac34+\frac56-\frac13$.
12. Find the distance between -6 and 4 on the real line.

### C. Algebraic simplification

13. Simplify $4(2x-3)-3(x+5)$.
14. Simplify $\frac23x-\frac34x+\frac56$.
15. Simplify $7-[3-(2-9)]$.
16. Factor out the greatest positive integer common factor from $18x-30$.
17. Simplify $\frac{10x}{15x}$ and state the domain restriction inherited from the original expression.
18. Explain the difference between $-y^2$ and $(-y)^2$.

### D. Reasoning and applications

19. A temperature is 6 degrees below zero and then rises by 11 degrees. Represent the calculation with signed numbers and find the final temperature.
20. A student claims that multiplying both sides of $a < b$ by $c$ always preserves the inequality direction. Give a counterexample and state the correct conditions.
21. A rectangular garden has length $x+4$ metres and width $x$ metres. Write and expand an expression for its area. State a reasonable restriction on $x$.
22. Explain why exact rational arithmetic is preferable to floating-point arithmetic when verifying that two rational expressions have the same exact value.

### Selected answers

1. (a) Additive inverse; (b) distributive property; (c) additive identity; (d) multiplicative inverse.
2. There is no real number $q$ such that $0q=1$; multiplication by zero always gives zero.
3. From $(-a)b=-(ab)$, set $b$ to $-b$: $(-a)(-b)=-\big(a(-b)\big)=-\big(-(ab)\big)=ab$.
4. (a) Direction unchanged; (b) direction unchanged; (c) direction reverses.
5. The numerator is a sum, so the factor $x$ is not a common factor of the entire numerator. For $x\ne0$, the correct form is $1+\frac4x$.
6. $-25+25=0$.
7. $20-3(8-5)\div3=20-3$; the result is $17$.
8. $\frac{21}{36}+\frac{10}{36}=\frac{31}{36}$.
9. $\frac{3}{10}$.
10. $\frac{10}{3}$.
11. $-\frac14$.
12. $|-6-4|=10$.
13. $8x-12-3x-15=5x-27$.
14. $-\frac1{12}x+\frac56$.
15. $7-[3-(-7)]=7-10=-3$.
16. $6(3x-5)$.
17. $\frac23$, with $x\ne0$ inherited from the original denominator.
18. $-y^2$ means $-(y^2)$; $(-y)^2$ squares the entire negative of $y$ and equals $y^2$.
19. $-6+11=5$ degrees above zero.
20. For example, $2 < 5$ but multiplying by $-2$ gives $-4 > -10$. Positive multipliers preserve direction; negative multipliers reverse it; zero does not preserve a strict inequality.
21. $A=x(x+4)=x^2+4x$, with $x > 0$ for a rectangle with positive width.
22. Exact rational arithmetic avoids rounding error and can decide equality of rational values exactly.

## 14. Chapter summary

- The real numbers form an ordered field; their algebraic and order properties justify the rules used in simplification.
- Subtraction is addition of an additive inverse, and division is multiplication by a reciprocal of a nonzero number.
- The sign rules follow from additive inverses and distributivity.
- Adding the same number preserves order; multiplying by a positive number preserves order; multiplying by a negative number reverses order.
- Fraction addition requires a common denominator. Fraction multiplication and division have distinct rules, and division requires a nonzero divisor.
- Order of operations must be combined with explicit grouping; a leading negative sign is not automatically part of a power's base.
- Algebraic simplification combines like terms and uses distribution while preserving domain restrictions.
- Absolute value measures magnitude and distance on the real line.
- Exact rational values should be preserved when exactness matters; floating-point results are approximations.
- Python can test examples and perform exact rational arithmetic, but finite tests do not prove general identities.

## 15. References

1. Marecek, L., Anthony-Smith, M., and Mathis, A. H. *Elementary Algebra 2e*. OpenStax, Rice University.
2. Marecek, L., Anthony-Smith, M., and Mathis, A. H. *Intermediate Algebra 2e*. OpenStax, Rice University.
3. Math-Atlas, **Foundations**, Chapter 04 — Number Systems and Mathematical Structures.
4. Math-Atlas, **Foundations**, `MATHEMATICAL_CONVENTIONS.MD`.
5. Math-Atlas, **Algebra**, Chapter 01 — Algebraic Language and Expressions.
