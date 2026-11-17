# Foundations 02 — Set Theory

## 1. Introduction

Set theory (نظریهٔ مجموعه‌ها) is a fundamental branch of mathematics concerned with collections of objects. These collections are called **sets** (مجموعه‌ها), and their objects are called **elements** (اعضا).

Sets provide a common language for describing mathematical structures, defining functions, studying relations, and developing many areas of mathematics.

## 2. Basic Definitions

A **set** is a well-defined collection of distinct objects.

If an object $x$ belongs to a set $A$, we write:

$$
x \in A
$$

If it does not belong to $A$, we write:

$$
x \notin A
$$

A set can be described by listing its elements:

$$
A = \lbrace 1,2,3,4\rbrace
$$

Or by specifying a property that its elements satisfy:

$$
A = \lbrace x \in \mathbb{N} \mid x < 5\rbrace
$$

The symbol $\mid$ means "such that."

### 2.1 Common Number Sets

The following standard sets appear throughout mathematics:

| Symbol | Meaning |
|---|---|
| $\mathbb{N}$ | Natural numbers |
| $\mathbb{Z}$ | Integers |
| $\mathbb{Q}$ | Rational numbers |
| $\mathbb{R}$ | Real numbers |
| $\mathbb{C}$ | Complex numbers |

The convention for whether $0$ belongs to $\mathbb{N}$ varies between mathematical texts. We will state the convention whenever it matters.

### 2.2 Empty Set

The **empty set** (مجموعهٔ تهی) contains no elements:

$$
\varnothing = \lbrace \rbrace
$$

For every set $A$:

$$
\varnothing \subseteq A
$$

### 2.3 Equality of Sets

Two sets are equal if and only if they contain exactly the same elements:

$$
A = B
\iff
(\forall x)(x \in A \iff x \in B)
$$

The order of elements and the number of times an element is written do not affect a set:

$$
\lbrace 1,2,3\rbrace = \lbrace 3,2,1\rbrace = \lbrace 1,1,2,3\rbrace
$$

## 3. Subsets and Set Relationships

### 3.1 Subset

A set $A$ is a **subset** (زیرمجموعه) of $B$ if every element of $A$ also belongs to $B$:

$$
A \subseteq B
\iff
(\forall x)(x \in A \Rightarrow x \in B)
$$

For example:

$$
\lbrace 1,2\rbrace \subseteq \lbrace 1,2,3\rbrace
$$

### 3.2 Proper Subset

A is a **proper subset** (زیرمجموعهٔ سره) of B if:

$$
A \subseteq B \quad \text{and} \quad A \neq B
$$

It is sometimes written as $A \subsetneq B$.

### 3.3 Superset

If $A \subseteq B$, then $B$ is a **superset** (فرا‌مجموعه) of $A$:

$$
B \supseteq A
$$

### 3.4 Disjoint Sets

Two sets are **disjoint** (مجموعه‌های جدا از هم) if they have no common elements:

$$
A \cap B = \varnothing
$$

## 4. Set Operations

Set operations (عملگرهای مجموعه‌ای) produce new sets from existing ones.

Let:

$$
A = \lbrace 1,2,3,4\rbrace
$$

$$
B = \lbrace 3,4,5,6\rbrace
$$

### 4.1 Union

The **union** (اجتماع) contains all elements that belong to at least one of the sets:

$$
A \cup B = \lbrace x \mid x \in A \lor x \in B\rbrace
$$

Example:

$$
A \cup B = \lbrace 1,2,3,4,5,6\rbrace
$$

### 4.2 Intersection

The **intersection** (اشتراک) contains elements common to both sets:

$$
A \cap B = \lbrace x \mid x \in A \land x \in B\rbrace
$$

Example:

$$
A \cap B = \lbrace 3,4\rbrace
$$

### 4.3 Difference

The **set difference** (تفاضل مجموعه‌ای) contains elements belonging to the first set but not the second:

$$
A - B = \lbrace x \mid x \in A \land x \notin B\rbrace
$$

Example:

$$
A-B = \lbrace 1,2\rbrace
$$

In general:

$$
A-B \neq B-A
$$

### 4.4 Complement

Given a universal set $U$, the **complement** (متمم) of $A$ contains all elements of $U$ that do not belong to $A$:

$$
A^c = U-A
$$

The universal set must be specified because the complement depends on the chosen universe.

## 5. Important Set Identities

Set identities (همانی‌های مجموعه‌ای) describe relationships that hold for all sets.

### 5.1 Commutative Laws

$$
A \cup B = B \cup A
$$

$$
A \cap B = B \cap A
$$

### 5.2 Associative Laws

$$
(A \cup B)\cup C = A\cup(B\cup C)
$$

$$
(A \cap B)\cap C = A\cap(B\cap C)
$$

### 5.3 Distributive Laws

$$
A\cap(B\cup C)
=
(A\cap B)\cup(A\cap C)
$$

$$
A\cup(B\cap C)
=
(A\cup B)\cap(A\cup C)
$$

### 5.4 Identity Laws

$$
A\cup\varnothing=A
$$

$$
A\cap U=A
$$

### 5.5 Complement Laws

$$
A\cup A^c=U
$$

$$
A\cap A^c=\varnothing
$$

### 5.6 De Morgan's Laws

$$
(A\cup B)^c=A^c\cap B^c
$$

$$
(A\cap B)^c=A^c\cup B^c
$$

These laws connect set theory with propositional logic.

## 6. Power Sets and Cartesian Products

### 6.1 Power Set

The **power set** (مجموعهٔ توانی) of $A$, denoted by $\mathcal{P}(A)$, is the set of all subsets of $A$.

For example:

$$
A=\lbrace 1,2\rbrace
$$

$$
\mathcal{P}(A)=
\lbrace \varnothing,\lbrace 1\rbrace,\lbrace 2\rbrace,\lbrace 1,2\rbrace\rbrace
$$

If a finite set has $n$ elements, its power set contains:

$$
|\mathcal{P}(A)|=2^n
$$

### 6.2 Cartesian Product

The **Cartesian product** (ضرب دکارتی) of two sets is the set of all ordered pairs whose first element belongs to $A$ and second element belongs to $B$:

$$
A\times B =
\lbrace (a,b)\mid a\in A,\ b\in B\rbrace
$$

For example:

$$
A=\lbrace 1,2\rbrace,\quad B=\lbrace x,y\rbrace
$$

$$
A\times B =
\lbrace (1,x),(1,y),(2,x),(2,y)\rbrace
$$

For finite sets:

$$
|A\times B|=|A|\cdot|B|
$$

In general, $A\times B$ is not equal to $B\times A$.

## 7. Cardinality and Finite Sets

The **cardinality** (اندازهٔ مجموعه) of a finite set is the number of its distinct elements.

It is denoted by:

$$
|A|
$$

For example:

$$
A=\lbrace 2,4,6,8\rbrace
\quad\Rightarrow\quad
|A|=4
$$

For two finite sets, the inclusion-exclusion principle (اصل شمول و عدم شمول) states:

$$
|A\cup B|
=
|A|+|B|-|A\cap B|
$$

This formula prevents common elements from being counted twice.

## 8. Theorems and Proofs

### Theorem 1: Subset Characterization of Equality

For any two sets $A$ and $B$:

$$
A=B
\iff
(A\subseteq B \land B\subseteq A)
$$

**Proof:**

Assume $A=B$. Every element of $A$ must then belong to $B$, and every element of $B$ must belong to $A$. Therefore:

$$
A\subseteq B,\quad B\subseteq A
$$

Conversely, assume both inclusions hold. Every element of $A$ belongs to $B$, and every element of $B$ belongs to $A$. Thus, the sets contain exactly the same elements:

$$
A=B
$$

### Theorem 2: Cardinality of a Union

For finite sets $A$ and $B$:

$$
|A\cup B|=|A|+|B|-|A\cap B|
$$

**Explanation:**

Adding $|A|$ and $|B|$ counts every element in the intersection twice. Subtracting $|A\cap B|$ removes the extra count.

## 9. Python Implementation

Python provides a built-in `set` type for representing finite sets.

### 9.1 Creating Sets

```python
A = {1, 2, 3, 4}
B = {3, 4, 5, 6}

empty_set = set()

print(A)
print(B)
print(empty_set)
```

Note: `{}` creates an empty dictionary, not an empty set.

### 9.2 Set Operations

```python
A = {1, 2, 3, 4}
B = {3, 4, 5, 6}

# Union
print(A | B)

# Intersection
print(A & B)

# Difference
print(A - B)

# Symmetric difference:
# Elements that belong to exactly one of the sets.
print(A ^ B)
```

### 9.3 Subset and Superset

```python
A = {1, 2}
B = {1, 2, 3}

print(A.issubset(B))   # True
print(B.issuperset(A)) # True

print(A < B)           # True: proper subset
```

### 9.4 Generating a Power Set

```python
from itertools import combinations

def power_set(items):
    """
    Return all subsets of a finite collection.

    The result is represented as a list of tuples.
    """
    items = list(items)
    result = []

    for r in range(len(items) + 1):
        for subset in combinations(items, r):
            result.append(subset)

    return result


A = {1, 2, 3}

for subset in power_set(A):
    print(subset)

print("Number of subsets:", len(power_set(A)))
```

### 9.5 Verifying De Morgan's Laws

```python
U = {1, 2, 3, 4, 5, 6, 7}

A = {1, 2, 3, 4}
B = {3, 4, 5}

complement_A = U - A
complement_B = U - B

left_1 = U - (A | B)
right_1 = complement_A & complement_B

left_2 = U - (A & B)
right_2 = complement_A | complement_B

assert left_1 == right_1
assert left_2 == right_2

print("Both De Morgan's laws are verified.")
```

## 10. Worked Examples

### Example 1: Basic Set Operations

Given:

$$
A=\lbrace 1,2,3,4,5\rbrace
$$

$$
B=\lbrace 4,5,6,7\rbrace
$$

Find the union, intersection, and both differences.

**Solution:**

$$
A\cup B=\lbrace 1,2,3,4,5,6,7\rbrace
$$

$$
A\cap B=\lbrace 4,5\rbrace
$$

$$
A-B=\lbrace 1,2,3\rbrace
$$

$$
B-A=\lbrace 6,7\rbrace
$$

### Example 2: Power Set Cardinality

A finite set contains 5 elements. How many subsets does it have?

**Solution:**

$$
|\mathcal{P}(A)|=2^5=32
$$

### Example 3: Inclusion-Exclusion

Suppose:

$$
|A|=20,\quad |B|=15,\quad |A\cap B|=7
$$

Find the cardinality of their union.

**Solution:**

$$
|A\cup B|=20+15-7=28
$$

## 11. Computational Experiments

Experiment with the following tasks:

1. Generate random finite sets and compare their union, intersection, and difference.
2. Verify the commutative and associative laws for randomly generated sets.
3. Generate power sets for increasingly large finite sets and observe how their sizes grow.
4. Verify the inclusion-exclusion principle computationally.
5. Compare the number of ordered pairs in $A\times B$ with $|A|\cdot|B|$.

For every experiment, distinguish between computational verification and mathematical proof. Testing many examples does not establish a statement for all possible sets.

## 12. Exercises

1. Let $A=\lbrace 1,2,3,4\rbrace$ and $B=\lbrace 3,4,5,6\rbrace$. Calculate all four basic set operations.
2. Prove that $A\cap B\subseteq A$.
3. Prove the distributive law:

   $$
   A\cap(B\cup C)=(A\cap B)\cup(A\cap C)
   $$

4. Find the power set of $\lbrace a,b,c\rbrace$.
5. If $|A|=8$, calculate $|\mathcal{P}(A)|$.
6. If $|A|=30$, $|B|=25$, and $|A\cap B|=10$, calculate $|A\cup B|$.
7. Explain why $A\times B$ is not necessarily equal to $B\times A$.
8. Write a Python function that verifies whether two finite sets are equal.
9. Write a Python function that checks De Morgan's laws for three finite sets and a specified universal set.
10. Explain why computational experiments cannot replace a general mathematical proof.

## 13. References

1. Halmos, P. R. *Naive Set Theory*. Springer.
2. Enderton, H. B. *Elements of Set Theory*. Academic Press.
3. Rosen, K. H. *Discrete Mathematics and Its Applications*. McGraw-Hill.
4. Epp, S. S. *Discrete Mathematics with Applications*. Cengage Learning.