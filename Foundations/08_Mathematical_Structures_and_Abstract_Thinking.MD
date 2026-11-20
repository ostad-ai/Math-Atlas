# Foundations 08 — Mathematical Structures and Abstract Thinking

## 1. Introduction

Mathematics is not only the study of numbers and calculations. It is also the study of structures, relationships, and patterns.

Consider the following objects:

- Integers under addition.
- Real numbers under multiplication.
- Square matrices under matrix addition.
- Functions under composition.
- Symmetries of a geometric object.

These objects belong to different mathematical domains, but some of their properties are shared.

For example, addition of integers and matrix addition are both associative and have identity elements.

Abstract mathematics (ریاضیات انتزاعی) studies such common properties independently of the particular objects involved.

This chapter introduces mathematical structures, operations, algebraic systems, homomorphisms, isomorphisms, and the role of abstraction in mathematical modeling.

---

## 2. What Is a Mathematical Structure?

A mathematical structure consists of a collection of objects together with specified relationships, operations, or distinguished elements.

A simple structure can be represented as

$$
\mathcal{S}=(A,R),
$$


where:

- $A$ is a set of objects.
- $R$ is a relation defined on those objects.

A structure with an operation may be written as

$$
\mathcal{S}=(A,\star),
$$


where $\star$ is a binary operation on $A$.

More complicated structures may contain several operations and relations:

$$
\mathcal{S}=(A,\star,\circ,R,e,\ldots).
$$


The exact components depend on the mathematical theory being studied.

### Example: Ordered Integers

The integers with their usual order form an ordered structure:

$$
(\mathbb{Z},\leq).
$$


The set is $\mathbb{Z}$, and the relation is the usual ordering.

### Example: Integers Under Addition

The structure

$$
(\mathbb{Z},+)
$$


consists of the integers together with addition.

Its properties include closure, associativity, an identity element, and additive inverses.

---

## 3. Binary Operations

A binary operation (عملگر دوتایی) on a set $A$ is a function

$$
\star:A\times A\to A.
$$


It takes two elements of $A$ and produces another element of $A$.

For every $a,b\in A$,

$$
a\star b\in A.
$$


### 3.1 Examples

**Integer addition**

$$
+: \mathbb{Z}\times\mathbb{Z}\to\mathbb{Z}.
$$


For example,

$$
3+5=8.
$$


**Real multiplication**

$$
\cdot:\mathbb{R}\times\mathbb{R}\to\mathbb{R}.
$$


For example,

$$
2.5\cdot4=10.
$$


**Matrix addition**

For two matrices of the same dimensions,

$$
A+B
$$


is another matrix of those dimensions.

### 3.2 Closure

A set $A$ is closed under an operation $\star$ if

$$
\forall a,b\in A,\quad a\star b\in A.
$$


For example, the integers are closed under addition:

$$
a,b\in\mathbb{Z} \Rightarrow a+b\in\mathbb{Z}.
$$


The positive integers are not closed under subtraction, because

$$
2-5=-3
$$


is not a positive integer.

### 3.3 Properties of Binary Operations

Important properties include:

**Commutativity**

$$
a\star b=b\star a.
$$


**Associativity**

$$
(a\star b)\star c = a\star(b\star c).
$$


**Identity element**

An element $e\in A$ is an identity if

$$
e\star a=a\star e=a
$$


for every $a\in A$.

**Inverse element**

If $e$ is an identity, an element $b$ is an inverse of $a$ when

$$
a\star b=b\star a=e.
$$


**Distributivity**

An operation $\star$ is left-distributive over another operation $\diamond$ if

$$
a\star(b\diamond c)=(a\star b)\diamond(a\star c).
$$

It is right-distributive if

$$
(a\diamond b)\star c=(a\star c)\diamond(b\star c).
$$

In a noncommutative structure, the two laws are logically distinct and must both be stated when both are required.

---

## 4. Algebraic Structures

An algebraic structure (ساختار جبری) is a set equipped with one or more operations satisfying specified axioms.

### 4.1 Semigroup

A semigroup is a nonempty set $S$ with an associative binary operation.

The defining property is

$$
(a\star b)\star c = a\star(b\star c).
$$


No identity element is required.

**Example**

The positive integers under addition form a semigroup:

$$
(\mathbb{Z}_{>0},+).
$$


Addition is associative, and the sum of two positive integers is positive.

### 4.2 Monoid

A monoid is a semigroup with an identity element.

Its axioms are:

1. Closure.
2. Associativity.
3. Existence of an identity element.

**Example**

The nonnegative integers under addition form a monoid:

$$
(\mathbb{N},+),
$$


using the convention $\mathbb{N}=\lbrace 0,1,2,\ldots\rbrace$.

The identity is zero because

$$
a+0=0+a=a.
$$


### 4.3 Group

A group is a set $G$ with a binary operation satisfying:

1. Closure.
2. Associativity.
3. Existence of an identity.
4. Existence of an inverse for every element.

**Example**

The integers under addition form a group:

$$
(\mathbb{Z},+).
$$


The identity is zero, and the inverse of $a$ is $-a$.

### 4.4 Abelian Group

A group is Abelian if its operation is also commutative:

$$
a\star b=b\star a.
$$


The integers under addition form an Abelian group.

A general group need not be Abelian.

### 4.5 Ring

A **ring** in Math-Atlas is a ring with multiplicative identity (a unital ring), following the convention set in Chapter 04. Its axioms are:

- The elements form an Abelian group under addition.
- Multiplication is associative.
- Both left and right distributive laws hold.
- A multiplicative identity $1$ exists.

Multiplication need not be commutative. Some texts allow rings without a multiplicative identity; such structures will be called **non-unital rings** here.

**Example**

The integers form a commutative ring with identity:

$$
(\mathbb{Z},+,\cdot).
$$


### 4.6 Field

A **field** is a **nontrivial** commutative ring with a multiplicative identity ($0\ne1$) in which every nonzero element has a multiplicative inverse. This excludes the zero ring.

For nonzero $a$,

$$
a\cdot a^{-1}=1.
$$


**Examples**

$$
(\mathbb{Q},+,\cdot)
$$


and

$$
(\mathbb{R},+,\cdot)
$$


are fields.

The integers are not a field because, for example, the multiplicative inverse of $2$ is $1/2$, which is not an integer.

### 4.7 Structure Hierarchy

For the standard definitions above, the following hierarchy holds:

$$
\text{Abelian Groups} \subseteq \text{Groups} \subseteq \text{Monoids} \subseteq \text{Semigroups}.
$$


A field is a more specialized structure with two compatible operations. It is not simply another step in this one-operation hierarchy.

---

## 5. Ordered Structures

An order relation describes how elements compare.

A partial order (ترتیب جزئی) is a relation $\preceq$ satisfying:

**Reflexivity**

$$
a\preceq a.
$$


**Antisymmetry**

$$
a\preceq b\land b\preceq a \Rightarrow a=b.
$$


**Transitivity**

$$
a\preceq b\land b\preceq c \Rightarrow a\preceq c.
$$


A set equipped with a partial order is called a partially ordered set, or poset.

### Example: Subset Relation

The power set of $A$, ordered by inclusion, forms a poset:

$$
(\mathcal{P}(A),\subseteq).
$$


For example, if

$$
A=\lbrace 1,2\rbrace,
$$


then

$$
\mathcal{P}(A) = \lbrace \varnothing,\lbrace 1\rbrace,\lbrace 2\rbrace,\lbrace 1,2\rbrace\rbrace.
$$


The relation $\subseteq$ is a partial order on this collection.

Not every pair of subsets is comparable. For example,

$$
\lbrace 1\rbrace\nsubseteq\lbrace 2\rbrace
$$


and

$$
\lbrace 2\rbrace\nsubseteq\lbrace 1\rbrace.
$$


### 5.1 Total Orders

A partial order is a total order if every pair of elements is comparable:

$$
a\preceq b \quad\text{or}\quad b\preceq a.
$$


The usual order on the real numbers is a total order.

---

## 6. Equivalence Relations and Partitions

An equivalence relation (رابطه هم‌ارزی) groups elements according to a shared property.

A relation is an equivalence relation if it is:

- Reflexive.
- Symmetric.
- Transitive.

### Example: Congruence Modulo $n$

For integers $a,b$,

$$
a\equiv b\pmod n
$$


means that $n$ divides $a-b$.

For example,

$$
17\equiv2\pmod5
$$


because

$$
17-2=15
$$


is divisible by 5.

The equivalence classes modulo 5 are represented by

$$
[0],[1],[2],[3],[4].
$$


Each class contains all integers with the same remainder modulo 5.

An equivalence relation divides a set into disjoint equivalence classes. These classes form a partition of the original set.

---

## 7. Homomorphisms

A homomorphism (همریختی) is a function between mathematical structures that preserves their specified operations. For a structure with several operations, preservation must be checked for each operation in its signature. For example, a ring homomorphism preserves addition and multiplication; a **unital** ring homomorphism also maps the multiplicative identity to the multiplicative identity.

Suppose two sets $A$ and $B$ have binary operations $\star$ and $\diamond$.

A function

$$
f:A\to B
$$


is a homomorphism if

$$
f(a\star b)=f(a)\diamond f(b)
$$


for all $a,b\in A$.

### Example: Modular Reduction

Define

$$
f:\mathbb{Z}\to\mathbb{Z}_5
$$


by

$$
f(a)=a\bmod5.
$$


Then

$$
f(a+b) = (a+b)\bmod5
$$


and

$$
f(a)\oplus f(b) = (a\bmod5+b\bmod5)\bmod5.
$$


Therefore,

$$
f(a+b)=f(a)\oplus f(b).
$$


The mapping preserves addition modulo 5.

### 7.1 Why Homomorphisms Matter

Homomorphisms allow mathematical objects to be studied through simpler or more convenient representations.

They are important in:

- Abstract algebra.
- Number theory.
- Linear algebra.
- Computer science.
- Cryptography.
- Algebraic modeling.

---

## 8. Isomorphisms

An isomorphism (یکریختی) is a bijective homomorphism whose inverse also preserves the relevant structure.

Two structures connected by an isomorphism are structurally equivalent. Their elements may have different names or representations, but their relevant mathematical relationships are the same. For ordinary algebraic structures with finitary operations, a bijective homomorphism has a structure-preserving inverse; stating the inverse condition explicitly makes the intended meaning clear.

### Example: Two Representations of the Integers

The sets

$$
\mathbb{Z}
$$


and

$$
\lbrace \ldots,-4,-2,0,2,4,\ldots\rbrace
$$


are isomorphic under addition through

$$
f(n)=2n.
$$


The function is bijective onto the set of even integers, and

$$
f(a+b)=2(a+b)=2a+2b=f(a)+f(b).
$$


Thus, the additive group of integers is isomorphic to the additive group of even integers.

---

## 9. Mathematical Abstraction

Abstraction (انتزاع) means identifying essential properties while ignoring irrelevant details.

Consider three systems:

1. Adding integers.
2. Adding vectors.
3. Adding matrices of the same dimensions.

Their elements are different, but each operation is associative and has an identity element.

Rather than proving the same basic properties separately in every setting, abstract algebra studies them through shared axioms.

This provides several advantages:

- General theorems apply to many different systems.
- Mathematical reasoning becomes more reusable.
- Relationships between different domains become visible.
- New structures can be studied without requiring familiar numerical representations.

### 9.1 From Concrete to Abstract

A useful progression is:

**Concrete example**

$$
2+3=5.
$$


**General arithmetic property**

$$
a+b=b+a.
$$


**Abstract axiom**

$$
a\star b=b\star a.
$$


The final statement applies to every structure whose operation satisfies commutativity.

---

## 10. Python Implementation: Testing Algebraic Structures

Python can help investigate finite mathematical structures.

The following implementation checks whether a finite, explicitly listed set with a supplied operation forms a group. It assumes hashable elements and a deterministic operation. The check is exhaustive for that finite input; it cannot prove a claim about an infinite structure.

```python
def check_group(elements, operation):
    elements = tuple(elements)
    element_set = set(elements)

    if not elements:
        return False
    if len(element_set) != len(elements):
        return False

    # Closure
    for a in elements:
        for b in elements:
            if operation(a, b) not in element_set:
                return False

    # Associativity
    for a in elements:
        for b in elements:
            for c in elements:
                left = operation(operation(a, b), c)
                right = operation(a, operation(b, c))

                if left != right:
                    return False

    # Identity
    identity = None

    for e in elements:
        if all(
            operation(e, a) == a
            and operation(a, e) == a
            for a in elements
        ):
            identity = e
            break

    if identity is None:
        return False

    # Inverses
    for a in elements:
        has_inverse = any(
            operation(a, b) == identity
            and operation(b, a) == identity
            for b in elements
        )

        if not has_inverse:
            return False

    return True
```

### 10.1 Example: Integers Modulo 5 Under Addition

The set is

$$
\mathbb{Z}_5=\lbrace 0,1,2,3,4\rbrace.
$$


Addition is performed modulo 5.

```python
def add_mod_5(a, b):
    return (a + b) % 5


elements = {0, 1, 2, 3, 4}

print(check_group(elements, add_mod_5))
# True
```

This finite group is Abelian because modular addition is commutative.

### 10.2 Checking Commutativity

```python
def is_commutative(elements, operation):
    for a in elements:
        for b in elements:
            if operation(a, b) != operation(b, a):
                return False

    return True


print(is_commutative(elements, add_mod_5))
# True
```

These functions are finite verification tools. They do not replace mathematical proofs for infinite structures.

---

## 11. Worked Examples

### Example 1: Is $(\mathbb{Z},+)$ a Group?

We verify the group axioms.

**Closure**

For all integers $a,b$,

$$
a+b\in\mathbb{Z}.
$$


**Associativity**

$$
(a+b)+c=a+(b+c).
$$


**Identity**

The identity is zero:

$$
a+0=0+a=a.
$$


**Inverses**

For every integer $a$, its inverse is $-a$:

$$
a+(-a)=0.
$$


Therefore,

$$
(\mathbb{Z},+)
$$


is a group.

Since addition is commutative, it is also an Abelian group.

### Example 2: Are the Positive Integers Under Addition a Group?

Consider

$$
(\mathbb{Z}_{>0},+).
$$


Closure and associativity hold.

However, there is no additive identity in the positive integers because zero is not included.

Therefore, this structure is not a monoid and cannot be a group.

### Example 3: Is $(\mathbb{R}\setminus\lbrace 0\rbrace,\cdot)$ a Group?

Consider the nonzero real numbers under multiplication.

- Multiplication is closed.
- Multiplication is associative.
- The identity is $1$.
- Every nonzero real number $a$ has inverse $1/a$.

Therefore,

$$
(\mathbb{R}\setminus\lbrace 0\rbrace,\cdot)
$$


is an Abelian group.

---

## 12. Computational Experiments

### Experiment 1: Modular Addition Groups

Test modular addition for several positive integers.

```python
for modulus in range(2, 11):
    elements = set(range(modulus))

    def operation(a, b, m=modulus):
        return (a + b) % m

    result = check_group(elements, operation)

    print(
        f"Modulo {modulus}: "
        f"{'Group' if result else 'Not a group'}"
    )
```

Investigate:

1. Why does every positive modulus produce a group under modular addition?
2. What is the identity element?
3. What is the additive inverse of each element?
4. Why is this group Abelian?

### Experiment 2: Modular Multiplication

Consider multiplication modulo $n$.

```python
def multiplication_mod(elements, modulus):
    def operation(a, b):
        return (a * b) % modulus

    return check_group(elements, operation)


for modulus in range(2, 11):
    elements = set(range(1, modulus))

    print(
        modulus,
        multiplication_mod(elements, modulus)
    )
```

This experiment tests a particular collection of nonzero residues.

Investigate why the nonzero residues modulo a composite number do not always form a group under multiplication.

For example, modulo 6,

$$
2\cdot3\equiv0\pmod6.
$$


The set of nonzero residues is therefore not closed under multiplication. For a general modulus $n$, the correct multiplicative group is the set of **units** $U(n)=\{a\in\{0,1,\ldots,n-1\}:\gcd(a,n)=1\}$ under multiplication modulo $n$. This set is a group for every $n\geq2$; nonzero residues and units coincide when the modulus is prime.

---

## 13. Common Mistakes

1. **Confusing a set with a structure:** A set alone does not specify an operation or relation.
2. **Assuming closure automatically:** Closure must be verified for the chosen set and operation.
3. **Confusing identity and inverse:** The identity is a single element; inverses depend on the elements.
4. **Assuming every group is Abelian:** Commutativity is an additional property.
5. **Assuming every ring is a field:** Nonzero elements of a ring need not have multiplicative inverses.
6. **Confusing homomorphism and isomorphism:** An isomorphism must also be bijective and preserve the structure in both directions.
7. **Treating computational checks as general proofs:** Finite testing cannot establish an unrestricted theorem about an infinite set.

---

## 14. Exercises

### Exercise 1 — Binary Operations

For each set and operation, determine whether closure holds.

1. Integers under addition.
2. Positive integers under subtraction.
3. Real numbers under multiplication.
4. Nonzero real numbers under division.
5. Even integers under addition.

### Exercise 2 — Algebraic Structures

Classify each structure as a semigroup, monoid, group, or Abelian group whenever applicable.

1. $(\mathbb{Z},+)$
2. $(\mathbb{N},+)$, with zero included.
3. $(\mathbb{Z}_{>0},+)$
4. $(\mathbb{R}\setminus\lbrace 0\rbrace,\cdot)$
5. $(\mathbb{Q}\setminus\lbrace 0\rbrace,\cdot)$

### Exercise 3 — Equivalence Relations

Define a relation on the integers by

$$
a\sim b \iff a-b\text{ is divisible by }4.
$$


Prove that it is an equivalence relation and describe its equivalence classes.

### Exercise 4 — Partial Orders

Let

$$
A=\lbrace 1,2,3,6\rbrace
$$


and define

$$
a\preceq b \iff a\text{ divides }b.
$$


Show that this relation is a partial order.

Determine which pairs are comparable.

### Exercise 5 — Homomorphisms

Consider

$$
f:\mathbb{Z}\to\mathbb{Z}, \qquad f(n)=3n.
$$


Prove that

$$
f(a+b)=f(a)+f(b).
$$


Is $f$ bijective as a function from the integers to the integers?

### Exercise 6 — Python Implementation

Implement functions that test:

1. Closure.
2. Associativity.
3. Commutativity.
4. Existence of an identity.
5. Existence of inverses.

Use your functions to investigate finite algebraic structures.

### Exercise 7 — Abstract Thinking

Explain why integer addition, vector addition, and matrix addition can all be studied using the same abstract algebraic axioms.

---

## 15. References

1. Joseph A. Gallian, *Contemporary Abstract Algebra*. Cengage Learning.
2. John B. Fraleigh, *A First Course in Abstract Algebra*. Pearson.
3. Michael Artin, *Algebra*. Pearson.
4. Kenneth H. Rosen, *Discrete Mathematics and Its Applications*. McGraw-Hill.
5. David S. Dummit and Richard M. Foote, *Abstract Algebra*. Wiley.

---

## 16. Summary

This chapter introduced mathematical structures as sets equipped with operations and relations.

The central ideas are:

- Binary operations and their properties.
- Algebraic structures such as semigroups, monoids, groups, rings, and fields.
- Partial orders and equivalence relations.
- Homomorphisms and isomorphisms.
- Mathematical abstraction as a way to identify common structures.
- Computational experiments for finite algebraic systems.

These concepts provide a foundation for abstract algebra, number theory, linear algebra, discrete mathematics, and many areas of theoretical computer science.
