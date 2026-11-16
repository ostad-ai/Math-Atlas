# Foundations 01 — Propositional Logic

## 1. Introduction

Mathematical logic provides a formal framework for expressing mathematical statements, evaluating their truth, and constructing valid arguments.

It is fundamental to mathematical proof, set theory, computer science, algorithms, and formal verification.

This chapter introduces propositional logic (منطق گزاره‌ای), including propositions, logical operators, truth tables, logical equivalence, and basic inference rules.

## 2. Propositions and Truth Values

### 2.1 Definition

A proposition (گزاره) is a declarative statement that has exactly one of two truth values:

- True: \(T\)
- False: \(F\)

Examples:

\[
P: 2+3=5
\]

This proposition is true.

\[
Q: 7<4
\]

This proposition is false.

Questions, commands, and expressions containing unspecified variables are not propositions by themselves.

For example, \(x>5\) is not a proposition until the value of \(x\) or its domain and quantification are specified.

### 2.2 Atomic and Compound Propositions

An atomic proposition (گزارهٔ اتمی) is a proposition that cannot be decomposed into simpler propositions using logical operators.

A compound proposition (گزارهٔ مرکب) is constructed from simpler propositions using logical operators.

For example:

\[
P: 8>3
\]

\[
Q: 8<10
\]

The compound proposition

\[
P\land Q
\]

states that both \(P\) and \(Q\) are true.

## 3. Logical Operators

### 3.1 Negation

Negation (نقیض) reverses the truth value of a proposition.

Symbol:

\[
\neg P
\]

| \(P\) | \(\neg P\) |
|---|---|
| T | F |
| F | T |

Example:

\[
P: 5>2
\]

Its negation is:

\[
\neg P: 5\leq2
\]

### 3.2 Conjunction

Conjunction (عطف) represents the logical AND operation.

Symbol:

\[
P\land Q
\]

It is true only when both propositions are true.

| \(P\) | \(Q\) | \(P\land Q\) |
|---|---|---|
| T | T | T |
| T | F | F |
| F | T | F |
| F | F | F |

### 3.3 Disjunction

Disjunction (فصل) represents the logical OR operation.

Symbol:

\[
P\lor Q
\]

In classical logic, it is true when at least one proposition is true.

| \(P\) | \(Q\) | \(P\lor Q\) |
|---|---|---|
| T | T | T |
| T | F | T |
| F | T | T |
| F | F | F |

This is inclusive OR: both propositions may be true simultaneously.

### 3.4 Implication

Implication (شرطی منطقی) represents the statement "if P, then Q."

Symbol:

\[
P\Rightarrow Q
\]

The proposition \(P\) is called the antecedent (مقدم), and \(Q\) is called the consequent (تالی).

| \(P\) | \(Q\) | \(P\Rightarrow Q\) |
|---|---|---|
| T | T | T |
| T | F | F |
| F | T | T |
| F | F | T |

An implication is false only when its antecedent is true and its consequent is false.

### 3.5 Biconditional

Biconditional (دوشرطی) represents logical equivalence between two propositions.

Symbol:

\[
P\Leftrightarrow Q
\]

It is true when both propositions have the same truth value.

| \(P\) | \(Q\) | \(P\Leftrightarrow Q\) |
|---|---|---|
| T | T | T |
| T | F | F |
| F | T | F |
| F | F | T |

An important equivalence is:

\[
P\Leftrightarrow Q
\equiv
(P\Rightarrow Q)\land(Q\Rightarrow P)
\]

## 4. Truth Tables

A truth table (جدول ارزش صدق) lists the truth value of a compound proposition for every possible combination of its atomic propositions.

For \(n\) independent atomic propositions, the number of possible combinations is:

\[
2^n
\]

For example, three propositions have:

\[
2^3=8
\]

possible truth-value combinations.

Truth tables are useful for:

- Evaluating compound propositions.
- Checking logical equivalence.
- Identifying tautologies and contradictions.
- Testing logical inference rules.

## 5. Logical Equivalence

Two propositions are logically equivalent (هم‌ارزی منطقی) if they have identical truth values under every possible assignment of their atomic propositions.

Symbol:

\[
P\equiv Q
\]

### 5.1 De Morgan's Laws

De Morgan's laws (قوانین دمورگان) state:

\[
\neg(P\land Q)
\equiv
(\neg P\lor\neg Q)
\]

\[
\neg(P\lor Q)
\equiv
(\neg P\land\neg Q)
\]

### 5.2 Double Negation

\[
\neg(\neg P)\equiv P
\]

### 5.3 Implication Equivalence

\[
P\Rightarrow Q
\equiv
\neg P\lor Q
\]

### 5.4 Commutative Laws

\[
P\land Q\equiv Q\land P
\]

\[
P\lor Q\equiv Q\lor P
\]

### 5.5 Associative Laws

\[
(P\land Q)\land R
\equiv
P\land(Q\land R)
\]

\[
(P\lor Q)\lor R
\equiv
P\lor(Q\lor R)
\]

## 6. Tautologies, Contradictions, and Contingencies

A tautology (همواره‌درست) is a compound proposition that is true under every possible truth assignment.

Example:

\[
P\lor\neg P
\]

A contradiction (تناقض منطقی) is false under every possible truth assignment.

Example:

\[
P\land\neg P
\]

A contingency (گزارهٔ وابسته به حالت) is neither a tautology nor a contradiction.

Example:

\[
P\land Q
\]

Its truth value depends on the values of \(P\) and \(Q\).

## 7. Logical Inference

Logical inference (استنتاج منطقی) is the process of deriving conclusions from premises using valid reasoning rules.

### 7.1 Modus Ponens

\[
P\Rightarrow Q
\]

\[
P
\]

Therefore:

\[
Q
\]

Example:

- If an integer is divisible by 4, it is even.
- The integer 12 is divisible by 4.
- Therefore, 12 is even.

### 7.2 Modus Tollens

\[
P\Rightarrow Q
\]

\[
\neg Q
\]

Therefore:

\[
\neg P
\]

### 7.3 Hypothetical Syllogism

\[
P\Rightarrow Q
\]

\[
Q\Rightarrow R
\]

Therefore:

\[
P\Rightarrow R
\]

### 7.4 Disjunctive Syllogism

\[
P\lor Q
\]

\[
\neg P
\]

Therefore:

\[
Q
\]

## 8. Predicates and Quantifiers

A predicate (محمول) is a statement containing one or more variables whose truth depends on the values assigned to those variables.

For example:

\[
P(x): x>5
\]

For \(x=8\), the predicate is true. For \(x=3\), it is false.

A domain (دامنه) specifies the set of possible values for the variables.

### 8.1 Universal Quantifier

The universal quantifier (سور همگانی) is represented by:

\[
\forall x\in A,\ P(x)
\]

It means that \(P(x)\) is true for every element of \(A\).

Example:

\[
\forall x\in\mathbb{R},\quad x^2\geq0
\]

This statement is true.

### 8.2 Existential Quantifier

The existential quantifier (سور وجودی) is represented by:

\[
\exists x\in A:\ P(x)
\]

It means that at least one element of \(A\) satisfies \(P(x)\).

Example:

\[
\exists x\in\mathbb{Z}:\quad x^2=9
\]

This statement is true because \(x=3\) and \(x=-3\) satisfy it.

### 8.3 Negation of Quantifiers

The following equivalences are fundamental:

\[
\neg(\forall x\in A,\ P(x))
\equiv
\exists x\in A:\neg P(x)
\]

\[
\neg(\exists x\in A,\ P(x))
\equiv
\forall x\in A:\neg P(x)
\]

## 9. Mathematical Proof Techniques

### 9.1 Direct Proof

A direct proof (اثبات مستقیم) establishes an implication by assuming its antecedent and logically deriving its consequent.

Example: The square of every even integer is even.

Let \(n\) be an even integer. By definition:

\[
n=2k,\qquad k\in\mathbb{Z}
\]

Then:

\[
n^2=(2k)^2=4k^2=2(2k^2)
\]

Since \(2k^2\) is an integer, \(n^2\) is even.

### 9.2 Proof by Contrapositive

The contrapositive (عکس نقیض) of:

\[
P\Rightarrow Q
\]

is:

\[
\neg Q\Rightarrow\neg P
\]

An implication is logically equivalent to its contrapositive. Therefore, proving the contrapositive is sufficient.

### 9.3 Proof by Contradiction

Proof by contradiction (برهان خلف) begins by assuming that the statement to be proved is false.

If this assumption leads to a logical contradiction, the original statement must be true.

### 9.4 Mathematical Induction

Mathematical induction (استقرای ریاضی) is a proof technique used to establish statements over the natural numbers.

It consists of two essential steps:

1. Base case (پایهٔ استقرا): Prove the statement for the initial value.
2. Inductive step (گام استقرا): Assume the statement holds for \(n=k\), then prove it holds for \(n=k+1\).

For example, consider:

\[
1+2+\cdots+n=\frac{n(n+1)}{2}
\]

The base case \(n=1\) gives:

\[
1=\frac{1(1+1)}{2}=1
\]

Assume the formula holds for \(n=k\):

\[
1+2+\cdots+k=\frac{k(k+1)}{2}
\]

Then:

\[
\begin{aligned}
1+2+\cdots+k+(k+1)
&=\frac{k(k+1)}{2}+(k+1)\\
&=\frac{(k+1)(k+2)}{2}
\end{aligned}
\]

Thus, the formula holds for \(k+1\), completing the proof.

## 10. Python Implementation

### 10.1 Logical Operators

Python provides built-in Boolean operators.

```python
def logical_not(p):
    return not p


def logical_and(p, q):
    return p and q


def logical_or(p, q):
    return p or q


def implication(p, q):
    return (not p) or q


def biconditional(p, q):
    return p == q
```

### 10.2 Generating Truth Tables

```python
from itertools import product


def implication(p, q):
    return (not p) or q


print("P Q | AND OR IMP IFF")

for p, q in product([False, True], repeat=2):

    print(
        int(p),
        int(q),
        "|",
        int(p and q),
        int(p or q),
        int(implication(p, q)),
        int(p == q)
    )
```

### 10.3 Verifying De Morgan's Laws

```python
from itertools import product


for p, q in product([False, True], repeat=2):

    first_left = not (p and q)
    first_right = (not p) or (not q)

    second_left = not (p or q)
    second_right = (not p) and (not q)

    assert first_left == first_right
    assert second_left == second_right


print("Both De Morgan's laws verified.")
```

### 10.4 Classifying a Proposition

```python
from itertools import product


def classify(expression, variables):

    results = []

    for values in product([False, True], repeat=len(variables)):

        assignment = dict(zip(variables, values))
        results.append(expression(**assignment))

    if all(results):
        return "Tautology"

    if not any(results):
        return "Contradiction"

    return "Contingency"


result = classify(
    lambda P, Q: P or not P,
    ["P"]
)

print(result)
```

## 11. Worked Examples

### Example 1: Implication

Evaluate:

\[
P\Rightarrow Q
\]

when \(P=F\) and \(Q=F\).

Using the truth table:

\[
F\Rightarrow F=T
\]

The implication is true.

### Example 2: Negating a Universal Statement

Find the negation of:

\[
\forall x\in\mathbb{R},\quad x^2\geq0
\]

Applying the quantifier negation rule:

\[
\exists x\in\mathbb{R}:\quad x^2<0
\]

This negation is false over the real numbers.

### Example 3: Testing Logical Equivalence

Determine whether:

\[
P\Rightarrow Q
\]

and

\[
\neg P\lor Q
\]

are logically equivalent.

Their truth tables are identical:

| P | Q | \(P\Rightarrow Q\) | \(\neg P\lor Q\) |
|---|---|---|---|
| T | T | T | T |
| T | F | F | F |
| F | T | T | T |
| F | F | T | T |

Therefore:

\[
P\Rightarrow Q\equiv\neg P\lor Q
\]

## 12. Computational Experiments

Suggested experiments:

1. Generate truth tables for expressions containing three and four variables.
2. Write a program that automatically checks whether two Boolean expressions are equivalent.
3. Generate all possible truth assignments for a compound proposition.
4. Implement a basic inference-rule checker.
5. Compare direct truth-table evaluation with symbolic simplification.

These experiments will connect the mathematical definitions to practical computational reasoning.

## 13. Exercises

### Conceptual Questions

1. What distinguishes an atomic proposition from a compound proposition?
2. Why is implication considered true when its antecedent is false?
3. Explain the difference between a tautology and a contingency.
4. What is the difference between a predicate and a proposition?

### Mathematical Exercises

5. Construct the truth table for:

\[
(P\land Q)\Rightarrow R
\]

6. Prove the following equivalence using a truth table:

\[
\neg(P\Rightarrow Q)\equiv P\land\neg Q
\]

7. Find the negation of:

\[
\forall x\in\mathbb{Z},\quad x^2\geq x
\]

8. Prove that the sum of two even integers is even.

9. Prove by induction:

\[
1+2+\cdots+n=\frac{n(n+1)}{2}
\]

### Programming Exercises

10. Write a Python function that generates the truth table of an arbitrary Boolean expression.

11. Write a program that checks whether an expression is a tautology, contradiction, or contingency.

12. Implement a function that verifies logical equivalence between two Boolean functions.

## 14. References

1. Enderton, H. B. — *A Mathematical Introduction to Logic*.
2. Rosen, K. H. — *Discrete Mathematics and Its Applications*.
3. Epp, S. S. — *Discrete Mathematics with Applications*.
4. Huth, M. and Ryan, M. — *Logic in Computer Science: Modelling and Reasoning about Systems*.

---

**Chapter status:** Initial educational draft.

**Next chapter:** Predicate Logic and Quantifiers (منطق محمول‌ها و سورها).

