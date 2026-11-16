# Foundations 03 — Relations and Functions

## 1. Introduction

Relations (روابط) and functions (تابع‌ها) are fundamental mathematical structures used to describe connections between objects.

A relation describes which objects are connected to one another. A function is a special kind of relation that assigns exactly one output to each input.

These concepts appear throughout mathematics, including algebra, calculus, discrete mathematics, probability, statistics, and computer science.

## 2. Relations

### 2.1 Definition

Let $A$ and $B$ be two sets.

A **binary relation** (رابطهٔ دوتایی) from $A$ to $B$ is any subset of their Cartesian product:

$$
R \subseteq A\times B
$$

If $(a,b)\in R$, we write:

$$
aRb
$$

This means that $a$ is related to $b$ through relation $R$.

### 2.2 Example

Let:

$$
A=\{1,2,3\}
$$

$$
B=\{2,4,6\}
$$

Define a relation:

$$
R=\{(1,2),(2,4),(3,6)\}
$$

This relation connects each element of $A$ to twice its value in $B$.

### 2.3 Domain and Range of a Relation

The **domain** (دامنه) of a relation is the set of all first components of its ordered pairs.

$$
\operatorname{Dom}(R)
=
\{a\in A\mid \exists b\in B:(a,b)\in R\}
$$

The **range** (برد) is the set of all second components:

$$
\operatorname{Ran}(R)
=
\{b\in B\mid \exists a\in A:(a,b)\in R\}
$$

For the previous example:

$$
\operatorname{Dom}(R)=\{1,2,3\}
$$

$$
\operatorname{Ran}(R)=\{2,4,6\}
$$

## 3. Relations on a Set

A relation on $A$ is a relation from $A$ to itself:

$$
R\subseteq A\times A
$$

Certain properties are particularly important.

### 3.1 Reflexivity

A relation $R$ on $A$ is **reflexive** (بازتابی) if every element is related to itself:

$$
\forall a\in A,\quad aRa
$$

Example: equality.

$$
a=a
$$

### 3.2 Symmetry

A relation is **symmetric** (تقارنی) if:

$$
\forall a,b\in A,\quad
aRb\Rightarrow bRa
$$

Example: on the integers, define:

$$
aRb\iff a-b\text{ is even}
$$

If $a-b$ is even, then $b-a$ is also even.

### 3.3 Antisymmetry

A relation is **antisymmetric** (پادتقارنی) if:

$$
\forall a,b\in A,\quad
(aRb\land bRa)\Rightarrow a=b
$$

Example: the usual less-than-or-equal relation on integers.

$$
a\leq b\land b\leq a\Rightarrow a=b
$$

Antisymmetry does not mean that the relation cannot contain pairs in both directions. It means that such pairs can occur only when the two elements are equal.

### 3.4 Transitivity

A relation is **transitive** (تعدی‌پذیر) if:

$$
\forall a,b,c\in A,\quad
(aRb\land bRc)\Rightarrow aRc
$$

Example: the usual less-than-or-equal relation.

$$
a\leq b\land b\leq c\Rightarrow a\leq c
$$

## 4. Equivalence Relations and Partitions

### 4.1 Equivalence Relation

An **equivalence relation** (رابطهٔ هم‌ارزی) is a relation that is:

1. Reflexive
2. Symmetric
3. Transitive

For example, define a relation on the integers:

$$
a\sim b
\iff
a-b\text{ is divisible by }3
$$

This is an equivalence relation.

### 4.2 Equivalence Classes

The **equivalence class** (ردهٔ هم‌ارزی) of an element $a$ is the set of all elements related to $a$:

$$
[a]=\{x\in A\mid x\sim a\}
$$

For congruence modulo 3, the integers are divided into three equivalence classes:

$$
[0]=\{\ldots,-6,-3,0,3,6,\ldots\}
$$

$$
[1]=\{\ldots,-5,-2,1,4,7,\ldots\}
$$

$$
[2]=\{\ldots,-4,-1,2,5,8,\ldots\}
$$

### 4.3 Partitions

A **partition** (افراز) of a set is a collection of nonempty, pairwise disjoint subsets whose union is the entire set.

Every equivalence relation produces a partition of its underlying set, and every partition defines an equivalence relation.

## 5. Partial Orders

A relation is a **partial order** (ترتیب جزئی) if it is:

1. Reflexive
2. Antisymmetric
3. Transitive

A set together with a partial order is called a **partially ordered set**, or **poset** (مجموعهٔ مرتب جزئی).

Examples include:

- The subset relation $\subseteq$ on the power set of a given set.
- Divisibility on the positive integers.
- The usual $\leq$ relation on integers.

A partial order does not require every pair of elements to be comparable.

For example, neither $\{1\}\subseteq\{2\}$ nor $\{2\}\subseteq\{1\}$ holds.

## 6. Functions

### 6.1 Definition

A **function** (تابع) from set $A$ to set $B$ is a relation that assigns exactly one element of $B$ to every element of $A$.

We write:

$$
f:A\to B
$$

For every $a\in A$, there must exist exactly one $b\in B$ such that:

$$
f(a)=b
$$

The set $A$ is the domain, and $B$ is the codomain (هم‌دامنه).

The range is the set of outputs actually produced:

$$
\operatorname{Ran}(f)
=
\{f(a)\mid a\in A\}
$$

Therefore:

$$
\operatorname{Ran}(f)\subseteq B
$$

### 6.2 Example

Consider:

$$
f:\mathbb{R}\to\mathbb{R}
$$

$$
f(x)=x^2
$$

Its domain is:

$$
\operatorname{Dom}(f)=\mathbb{R}
$$

Its codomain is:

$$
B=\mathbb{R}
$$

Its range is:

$$
\operatorname{Ran}(f)=[0,\infty)
$$

The codomain and range are not necessarily equal.

### 6.3 When Is a Relation a Function?

Consider:

$$
R=\{(1,2),(2,3),(3,4)\}
$$

This is a function because every input has exactly one output.

However:

$$
S=\{(1,2),(1,3),(2,4)\}
$$

is not a function because input $1$ has two different outputs.

An input cannot have multiple outputs in a function, although different inputs may have the same output.

## 7. Types of Functions

### 7.1 Injective Functions

A function is **injective** (یک‌به‌یک) if different inputs always produce different outputs.

Formally:

$$
f(a_1)=f(a_2)\Rightarrow a_1=a_2
$$

An equivalent statement is:

$$
a_1\neq a_2\Rightarrow f(a_1)\neq f(a_2)
$$

Example:

$$
f:\mathbb{R}\to\mathbb{R},
\quad f(x)=2x+1
$$

This function is injective.

### 7.2 Surjective Functions

A function is **surjective** (پوشا) if every element of the codomain is the output of at least one input.

$$
\forall y\in B,\quad
\exists x\in A:f(x)=y
$$

Example:

$$
f:\mathbb{R}\to\mathbb{R},
\quad f(x)=x^3
$$

This function is surjective.

### 7.3 Bijective Functions

A function is **bijective** (دوسویی) if it is both injective and surjective.

A bijection establishes a one-to-one correspondence between its domain and codomain.

Example:

$$
f:\mathbb{R}\to\mathbb{R},
\quad f(x)=2x+1
$$

This function is bijective.

## 8. Composition and Inverse Functions

### 8.1 Function Composition

The **composition** (ترکیب) of functions applies one function after another.

Given:

$$
f:A\to B
$$

$$
g:B\to C
$$

their composition is:

$$
g\circ f:A\to C
$$

defined by:

$$
(g\circ f)(x)=g(f(x))
$$

Example:

$$
f(x)=x+2
$$

$$
g(x)=3x
$$

Then:

$$
(g\circ f)(x)=3(x+2)=3x+6
$$

In general:

$$
g\circ f\neq f\circ g
$$

Function composition is associative:

$$
h\circ(g\circ f)=(h\circ g)\circ f
$$

### 8.2 Identity Function

The **identity function** (تابع همانی) on $A$ is:

$$
I_A:A\to A
$$

$$
I_A(x)=x
$$

It satisfies:

$$
f\circ I_A=f
$$

and:

$$
I_B\circ f=f
$$

for $f:A\to B$.

### 8.3 Inverse Function

A function has an inverse (تابع وارون) if it is bijective.

For a bijection:

$$
f:A\to B
$$

the inverse is:

$$
f^{-1}:B\to A
$$

It satisfies:

$$
f^{-1}(f(x))=x
$$

and:

$$
f(f^{-1}(y))=y
$$

Example:

$$
f(x)=2x+3
$$

Let:

$$
y=2x+3
$$

Solving for $x$:

$$
x=\frac{y-3}{2}
$$

Therefore:

$$
f^{-1}(x)=\frac{x-3}{2}
$$

## 9. Images and Preimages

For a function $f:A\to B$:

### 9.1 Image of a Set

For $S\subseteq A$, its image is:

$$
f(S)=\{f(x)\mid x\in S\}
$$

### 9.2 Preimage of a Set

For $T\subseteq B$, its preimage is:

$$
f^{-1}(T)=\{x\in A\mid f(x)\in T\}
$$

The preimage is defined for every function, even if the function is not invertible. In this context, $f^{-1}(T)$ means the preimage of a set, not necessarily an inverse function.

## 10. Important Theorems

### Theorem 1: Inverse Function Criterion

A function $f:A\to B$ has an inverse function $f^{-1}:B\to A$ if and only if $f$ is bijective.

**Proof:**

Suppose $f$ has an inverse.

If $f(a_1)=f(a_2)$, applying $f^{-1}$ to both sides gives:

$$
a_1=a_2
$$

Therefore, $f$ is injective.

For every $b\in B$, the inverse provides an element $a=f^{-1}(b)$ such that:

$$
f(a)=b
$$

Therefore, $f$ is surjective.

Conversely, suppose $f$ is bijective.

Surjectivity guarantees that every $b\in B$ has at least one preimage. Injectivity guarantees that this preimage is unique.

We can therefore define:

$$
f^{-1}(b)=a
\quad\text{where }f(a)=b
$$

Thus, the inverse function exists.

### Theorem 2: Composition of Injective Functions

If $f:A\to B$ and $g:B\to C$ are injective, then:

$$
g\circ f:A\to C
$$

is injective.

**Proof:**

Suppose:

$$
(g\circ f)(a_1)=(g\circ f)(a_2)
$$

Then:

$$
g(f(a_1))=g(f(a_2))
$$

Since $g$ is injective:

$$
f(a_1)=f(a_2)
$$

Since $f$ is injective:

$$
a_1=a_2
$$

Therefore, $g\circ f$ is injective.

### Theorem 3: Composition of Surjective Functions

If $f:A\to B$ and $g:B\to C$ are surjective, then $g\circ f$ is surjective.

**Proof:**

Take any $c\in C$.

Since $g$ is surjective, there exists $b\in B$ such that:

$$
g(b)=c
$$

Since $f$ is surjective, there exists $a\in A$ such that:

$$
f(a)=b
$$

Consequently:

$$
(g\circ f)(a)=g(f(a))=g(b)=c
$$

Thus, every element of $C$ has a preimage, so $g\circ f$ is surjective.

## 11. Python Implementation

Python dictionaries, sets, and functions provide practical ways to represent finite relations and mappings.

### 11.1 Representing a Relation

```python
A = {1, 2, 3}

R = {
    (1, 2),
    (2, 3),
    (3, 1)
}

print("Relation:", R)
```

### 11.2 Checking Relation Properties

```python
def is_reflexive(A, R):
    return all((x, x) in R for x in A)


def is_symmetric(A, R):
    return all(
        (y, x) in R
        for x, y in R
    )


def is_antisymmetric(A, R):
    return all(
        x == y or (y, x) not in R
        for x, y in R
    )


def is_transitive(A, R):
    for x, y in R:
        for z, w in R:
            if y == z and (x, w) not in R:
                return False

    return True


A = {1, 2, 3}

R = {
    (1, 1),
    (2, 2),
    (3, 3),
    (1, 2),
    (2, 3),
    (1, 3)
}

print("Reflexive:", is_reflexive(A, R))
print("Symmetric:", is_symmetric(A, R))
print("Antisymmetric:", is_antisymmetric(A, R))
print("Transitive:", is_transitive(A, R))
```

These functions assume that every pair in `R` belongs to $A\times A$.

### 11.3 Representing a Finite Function

```python
def is_function(domain, relation):
    """
    Check whether a finite relation defines
    exactly one output for every domain element.
    """
    mapping = {}

    for x, y in relation:
        if x not in domain:
            return False

        if x in mapping and mapping[x] != y:
            return False

        mapping[x] = y

    return set(mapping.keys()) == set(domain)


A = {1, 2, 3}

R = {
    (1, 10),
    (2, 20),
    (3, 30)
}

print(is_function(A, R))
```

### 11.4 Checking Injectivity and Surjectivity

```python
def is_injective(domain, codomain, mapping):
    """
    Check injectivity of a finite function.
    """
    if set(mapping.keys()) != set(domain):
        return False

    if any(y not in codomain for y in mapping.values()):
        return False

    outputs = list(mapping.values())

    return len(outputs) == len(set(outputs))


def is_surjective(domain, codomain, mapping):
    """
    Check surjectivity of a finite function.
    """
    if set(mapping.keys()) != set(domain):
        return False

    if any(y not in codomain for y in mapping.values()):
        return False

    return set(mapping.values()) == set(codomain)


A = {1, 2, 3}
B = {2, 4, 6}

f = {
    1: 2,
    2: 4,
    3: 6
}

print("Injective:", is_injective(A, B, f))
print("Surjective:", is_surjective(A, B, f))
```

These checks apply to finite mappings represented explicitly by dictionaries.

### 11.5 Function Composition

```python
def compose(f, g, domain):
    """
    Return g composed with f.

    f maps A to B.
    g maps B to C.
    """
    result = {}

    for x in domain:
        result[x] = g[f[x]]

    return result


A = {1, 2, 3}

f = {
    1: 2,
    2: 3,
    3: 4
}

g = {
    2: 20,
    3: 30,
    4: 40
}

composition = compose(f, g, A)

print(composition)
```

## 12. Worked Examples

### Example 1: Testing an Equivalence Relation

On the integers, define:

$$
aRb\iff a-b\text{ is divisible by }5
$$

Show that $R$ is an equivalence relation.

**Solution:**

Reflexivity:

$$
a-a=0
$$

Since 0 is divisible by 5, $aRa$.

Symmetry:

If:

$$
a-b=5k
$$

then:

$$
b-a=-5k
$$

Therefore, $bRa$.

Transitivity:

Suppose:

$$
a-b=5k
$$

and:

$$
b-c=5m
$$

Adding:

$$
a-c=5(k+m)
$$

Therefore, $aRc$.

The relation is reflexive, symmetric, and transitive. Hence, it is an equivalence relation.

### Example 2: Injectivity and Surjectivity

Consider:

$$
f:\mathbb{R}\to\mathbb{R}
$$

$$
f(x)=x^2
$$

Is this function injective? Is it surjective?

**Solution:**

It is not injective because:

$$
f(2)=f(-2)=4
$$

It is not surjective onto $\mathbb{R}$ because negative real numbers are not in its range.

Therefore, it is neither injective nor surjective.

### Example 3: Finding an Inverse

Given:

$$
f(x)=5x-7
$$

Find its inverse.

**Solution:**

Start with:

$$
y=5x-7
$$

Solve for $x$:

$$
x=\frac{y+7}{5}
$$

Thus:

$$
f^{-1}(x)=\frac{x+7}{5}
$$

## 13. Computational Experiments

1. Generate finite relations and test their reflexivity, symmetry, antisymmetry, and transitivity.
2. Generate equivalence relations and identify their equivalence classes.
3. Enumerate all functions between two small finite sets.
4. Count how many of these functions are injective, surjective, and bijective.
5. Compare a function with its inverse when it is bijective.
6. Verify associativity of function composition for several finite mappings.

For finite sets with $m$ elements in the domain and $n$ elements in the codomain, the total number of functions is:

$$
n^m
$$

If $m=n$, the number of bijections is:

$$
n!
$$

## 14. Exercises

1. Let $A=\{1,2,3\}$. Give an example of a reflexive relation on $A$.
2. Give an example of a symmetric relation that is not transitive.
3. Determine whether the relation $\leq$ on integers is reflexive, symmetric, antisymmetric, and transitive.
4. Prove that equality is an equivalence relation.
5. Find the equivalence classes of congruence modulo 4 on the integers.
6. Determine whether $f:\mathbb{R}\to\mathbb{R}$, defined by $f(x)=3x+2$, is injective and surjective.
7. Determine whether $f:\mathbb{R}\to[0,\infty)$, defined by $f(x)=x^2$, is surjective.
8. Calculate $g\circ f$ and $f\circ g$, where $f(x)=x+1$ and $g(x)=x^2$.
9. Find the inverse of $f(x)=4x-9$.
10. Write a Python program that enumerates all functions between two finite sets.
11. Write a Python program that checks whether a finite relation is an equivalence relation.
12. Explain the difference between the codomain and the range of a function.

## 15. References

1. Enderton, H. B. *Elements of Set Theory*. Academic Press.
2. Rosen, K. H. *Discrete Mathematics and Its Applications*. McGraw-Hill.
3. Epp, S. S. *Discrete Mathematics with Applications*. Cengage Learning.
4. Halmos, P. R. *Naive Set Theory*. Springer.