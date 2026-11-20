# Foundations 04 — Number Systems and Mathematical Structures

## 1. Introduction

Number systems (دستگاه‌های عددی) provide the mathematical framework for representing quantities, performing operations, and describing mathematical relationships.

The familiar progression from natural numbers to integers, rational numbers, real numbers, and complex numbers is not merely an expansion of notation. Each extension makes new mathematical operations and problems possible.

This chapter introduces the principal number systems and the algebraic structures (ساختارهای جبری) associated with them.

## 2. Natural Numbers

The natural numbers (اعداد طبیعی) are commonly denoted by:

$$
\mathbb{N}=\lbrace 0,1,2,3,\ldots\rbrace
$$


Some mathematical conventions begin the natural numbers at 1. We use the convention that includes zero.

Natural numbers are used for counting and ordering.

### 2.1 Peano Axioms

The natural numbers can be characterized axiomatically using the Peano axioms (اصل‌های پئانو).

A common formulation includes:

1. Zero is a natural number.
2. Every natural number has a successor.
3. Zero is not the successor of any natural number.
4. Different natural numbers have different successors.
5. Mathematical induction holds.

The successor of $n$ is denoted by:

$$
S(n)
$$


For example:

$$
S(0)=1,\quad S(1)=2
$$


### 2.2 Mathematical Induction

The principle of mathematical induction (استقرای ریاضی) establishes statements about all natural numbers.

To prove a proposition $P(n)$:

1. **Base case:** Prove $P(0)$.
2. **Inductive hypothesis:** Assume $P(k)$ holds.
3. **Inductive step:** Prove $P(k+1)$.

Then $P(n)$ holds for every natural number $n$.

Example: Prove that:

$$
0+1+\cdots+n=\frac{n(n+1)}{2}
$$


**Base case:**

For $n=0$:

$$
0=\frac{0(0+1)}{2}=0
$$


**Inductive hypothesis:**

Assume:

$$
0+1+\cdots+k=\frac{k(k+1)}{2}
$$


**Inductive step:**

$$
\begin{aligned} 0+1+\cdots+k+(k+1) &=\frac{k(k+1)}{2}+k+1\\ &=\frac{(k+1)(k+2)}{2} \end{aligned}
$$


This is the required formula for $k+1$.

Therefore, the identity holds for all natural numbers.

## 3. Integers

The integers (اعداد صحیح) are:

$$
\mathbb{Z}=\lbrace \ldots,-2,-1,0,1,2,\ldots\rbrace
$$


Integers extend the natural numbers by including negative numbers.

They allow subtraction without leaving the number system.

For example:

$$
3-7=-4
$$


The natural numbers are contained in the integers:

$$
\mathbb{N}\subseteq\mathbb{Z}
$$


### 3.1 Properties of Integer Operations

For integers $a,b,c$:

**Closure:**

$$
a+b\in\mathbb{Z}
$$


$$
a\cdot b\in\mathbb{Z}
$$


**Commutativity:**

$$
a+b=b+a
$$


$$
ab=ba
$$


**Associativity:**

$$
(a+b)+c=a+(b+c)
$$


$$
(ab)c=a(bc)
$$


**Distributivity:**

$$
a(b+c)=ab+ac
$$


However, integer division does not always produce an integer:

$$
1\div 2=\frac12\notin\mathbb{Z}
$$


## 4. Rational Numbers

The rational numbers (اعداد گویا) are numbers that can be expressed as a ratio of two integers:

$$
\mathbb{Q} = \left\lbrace \frac{a}{b} \mid a,b\in\mathbb{Z},\ b\neq0 \right\rbrace
$$


Examples:

$$
\frac12,\quad -\frac34,\quad 5,\quad 0
$$


Every integer is rational because:

$$
a=\frac{a}{1}
$$


Therefore:

$$
\mathbb{Z}\subseteq\mathbb{Q}
$$


### 4.1 Equivalent Fractions

Two fractions represent the same rational number if:

$$
\frac{a}{b}=\frac{c}{d} \iff ad=bc
$$


where $b,d\neq0$.

For example:

$$
\frac12=\frac24
$$


### 4.2 Decimal Representations

Every rational number has a decimal representation that either terminates or eventually repeats.

Examples:

$$
\frac14=0.25
$$


$$
\frac13=0.3333\ldots
$$


A non-terminating, non-repeating decimal cannot represent a rational number.

## 5. Irrational and Real Numbers

### 5.1 Irrational Numbers

An irrational number (عدد گنگ) cannot be expressed as a ratio of two integers.

Examples include:

$$
\sqrt2,\quad \pi,\quad e
$$


The decimal expansions of irrational numbers are non-terminating and non-repeating.

### 5.2 Real Numbers

The real numbers (اعداد حقیقی) include all rational and irrational numbers.

$$
\mathbb{R}=\mathbb{Q}\cup(\mathbb{R}\setminus\mathbb{Q})
$$


The number systems are nested:

$$
\mathbb{N}\subseteq \mathbb{Z}\subseteq \mathbb{Q}\subseteq \mathbb{R}
$$


The real numbers form a complete ordered field (میدان مرتب کامل).

### 5.3 Completeness

Completeness (کامل‌بودن) is a fundamental property of the real numbers.

One important formulation is the least upper bound property:

Every nonempty subset of $\mathbb{R}$ that is bounded above has a least upper bound in $\mathbb{R}$.

For example, consider:

$$
S=\lbrace x\in\mathbb{R}\mid x^2<2,\ x\geq0\rbrace
$$


Its least upper bound is:

$$
\sup S=\sqrt2
$$


This property distinguishes the real numbers from the rational numbers.

## 6. Complex Numbers

The complex numbers (اعداد مختلط) extend the real numbers by introducing the imaginary unit:

$$
i^2=-1
$$


A complex number has the form:

$$
z=a+bi
$$


where:

$$
a,b\in\mathbb{R}
$$


The set of complex numbers is denoted by:

$$
\mathbb{C}
$$


### 6.1 Real and Imaginary Parts

For:

$$
z=a+bi
$$


the real part is:

$$
\mathop{\text{Re}}(z)=a
$$


The imaginary part is:

$$
\mathop{\text{Im}}(z)=b
$$


### 6.2 Complex Arithmetic

For:

$$
z_1=a+bi,\quad z_2=c+di
$$


Addition:

$$
z_1+z_2=(a+c)+(b+d)i
$$


Multiplication:

$$
z_1z_2=(ac-bd)+(ad+bc)i
$$


Conjugation:

$$
\overline{z_1}=a-bi
$$


Modulus:

$$
|z_1|=\sqrt{a^2+b^2}
$$


### 6.3 Complex Numbers and Polynomial Equations

The complex numbers allow every nonconstant polynomial with complex coefficients to have a complete set of roots, counted with multiplicity.

This is the fundamental theorem of algebra (قضیهٔ بنیادی جبر).

For example:

$$
x^2+1=0
$$


has no real solutions, but has two complex solutions:

$$
x=i,\quad x=-i
$$


The number systems are now nested as:

$$
\mathbb{N}\subseteq \mathbb{Z}\subseteq \mathbb{Q}\subseteq \mathbb{R}\subseteq \mathbb{C}
$$


## 7. Algebraic Structures

An algebraic structure (ساختار جبری) consists of a set together with one or more operations satisfying specified axioms.

### 7.1 Binary Operations

A binary operation (عمل دوتایی) on a set $S$ is a function:

$$
*:S\times S\to S
$$


It combines any two elements of $S$ to produce another element of $S$.

Examples include addition and multiplication on the integers.

### 7.2 Semigroups

A semigroup (نیم‌گروه) is a nonempty set equipped with an associative binary operation.

For all $a,b,c\in S$:

$$
(a*b)*c=a*(b*c)
$$


### 7.3 Monoids

A monoid (تک‌وار) is a semigroup with an identity element $e$:

$$
a*e=e*a=a
$$


For example:

$$
(\mathbb{N},+,0)
$$


is a monoid under our convention that $\mathbb{N}$ includes zero.

### 7.4 Groups

A group (گروه) is a set $G$ with a binary operation satisfying:

1. Closure.
2. Associativity.
3. Existence of an identity element.
4. Existence of an inverse for every element.

For each $a\in G$, there exists $a^{-1}\in G$ such that:

$$
a*a^{-1}=a^{-1}*a=e
$$


Example:

$$
(\mathbb{Z},+,0)
$$


is a group because every integer $a$ has additive inverse $-a$.

### 7.5 Abelian Groups

An Abelian group (گروه آبلی) is a group whose operation is also commutative:

$$
a*b=b*a
$$


The integers under addition form an Abelian group.

### 7.6 Rings

A ring (حلقه) is an algebraic structure with two operations, usually called addition and multiplication.

Under the common convention used here:

- Addition forms an Abelian group.
- Multiplication is associative.
- Multiplication distributes over addition.

The integers form a commutative ring with identity.

### 7.7 Fields

A field (میدان) is a commutative ring with identity in which every nonzero element has a multiplicative inverse.

Examples:

$$
\mathbb{Q},\quad\mathbb{R},\quad\mathbb{C}
$$


The integers are not a field because, for example, 2 has no multiplicative inverse in $\mathbb{Z}$.

## 8. Ordered Fields

An ordered field (میدان مرتب) is a field equipped with an order relation compatible with addition and multiplication.

For real numbers:

If:

$$
a<b
$$


then:

$$
a+c<b+c
$$


for every real $c$.

If:

$$
0<a,\quad 0<b
$$


then:

$$
0<ab
$$


The real numbers form an ordered field.

The complex numbers cannot be given an order compatible with all the usual field operations.

This is one important distinction between $\mathbb{R}$ and $\mathbb{C}$.

## 9. Important Theorems

### Theorem 1: Uniqueness of the Additive Identity

In a group, the identity element is unique.

**Proof:**

Suppose $e$ and $e'$ are both identity elements.

Since $e$ is an identity:

$$
e*e'=e'
$$


Since $e'$ is an identity:

$$
e*e'=e
$$


Therefore:

$$
e=e'
$$


### Theorem 2: Uniqueness of Inverses

Every element of a group has exactly one inverse.

**Proof:**

Suppose $b$ and $c$ are both inverses of $a$.

Then:

$$
a*b=e,\quad c*a=e
$$


Using associativity:

$$
c=c*e
$$


$$
=c*(a*b)
$$


$$
=(c*a)*b
$$


$$
=e*b=b
$$


Thus:

$$
b=c
$$


### Theorem 3: Cancellation Law in Groups

If $G$ is a group and:

$$
a*b=a*c
$$


then:

$$
b=c
$$


**Proof:**

Multiply both sides on the left by $a^{-1}$:

$$
a^{-1}*(a*b)=a^{-1}*(a*c)
$$


Using associativity and the identity property:

$$
b=c
$$


## 10. Python Implementation

### 10.1 Checking Number Membership

```python
import numbers

def classify_number(x):
    """
    Classify common Python numeric values.
    """
    if isinstance(x, bool):
        return "Boolean"

    if isinstance(x, complex):
        if x.imag != 0:
            return "Complex"
        x = x.real

    if isinstance(x, int):
        return "Integer"

    if isinstance(x, float):
        return "Real floating-point value"

    return "Other numeric or non-numeric value"


values = [5, -3, 0.5, 2 + 3j, 4 + 0j, True]

for value in values:
    print(value, "->", classify_number(value))
```

Python's `float` type represents floating-point approximations, not exact mathematical real numbers.

### 10.2 Complex Arithmetic

```python
z1 = 3 + 2j
z2 = 1 - 4j

print("Addition:", z1 + z2)
print("Subtraction:", z1 - z2)
print("Multiplication:", z1 * z2)
print("Division:", z1 / z2)
print("Conjugate:", z1.conjugate())
print("Modulus:", abs(z1))
```

### 10.3 Testing Group Axioms on a Finite Set

```python
def check_group(elements, operation):
    """
    Check the group axioms for a finite set.

    operation(a, b) must return the result
    of the binary operation.
    """
    elements = list(elements)

    # Closure
    for a in elements:
        for b in elements:
            if operation(a, b) not in elements:
                return False, "Closure failed"

    # Associativity
    for a in elements:
        for b in elements:
            for c in elements:
                left = operation(operation(a, b), c)
                right = operation(a, operation(b, c))

                if left != right:
                    return False, "Associativity failed"

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
        return False, "No identity element"

    # Inverses
    for a in elements:
        has_inverse = any(
            operation(a, b) == identity
            and operation(b, a) == identity
            for b in elements
        )

        if not has_inverse:
            return False, "An inverse is missing"

    return True, f"Group verified; identity = {identity}"


# Integers modulo 4 under addition.
elements = {0, 1, 2, 3}

def add_mod_4(a, b):
    return (a + b) % 4

print(check_group(elements, add_mod_4))
```

This program checks the group axioms for finite sets. It does not establish algebraic properties for infinite structures.

## 11. Worked Examples

### Example 1: Identifying a Number System

Determine the smallest standard number system containing:

$$
-7,\quad \frac{3}{5},\quad \sqrt{2},\quad 4+3i
$$


**Solution:**

- $-7$ belongs to $\mathbb{Z}$.
- $\frac35$ belongs to $\mathbb{Q}$.
- $\sqrt2$ belongs to $\mathbb{R}\setminus\mathbb{Q}$.
- $4+3i$ belongs to $\mathbb{C}\setminus\mathbb{R}$.

### Example 2: Checking a Group

Consider the set:

$$
G=\lbrace 0,1,2\rbrace
$$


with addition modulo 3.

The operation table is:

| $+$ mod 3 | 0 | 1 | 2 |
|---|---:|---:|---:|
| 0 | 0 | 1 | 2 |
| 1 | 1 | 2 | 0 |
| 2 | 2 | 0 | 1 |

The operation is closed and associative. The identity is 0, and the inverses are:

$$
0^{-1}=0,\quad 1^{-1}=2,\quad 2^{-1}=1
$$


Therefore, $G$ is a group. Since addition modulo 3 is commutative, it is an Abelian group.

### Example 3: Why Integers Are Not a Field

Consider:

$$
2x=1
$$


Solving over the rational numbers gives:

$$
x=\frac12
$$


But:

$$
\frac12\notin\mathbb{Z}
$$


Thus, the integers do not contain multiplicative inverses for all nonzero elements and are not a field.

## 12. Computational Experiments

1. Implement arithmetic operations for rational numbers using Python's `fractions.Fraction`.
2. Compare exact rational arithmetic with floating-point arithmetic.
3. Generate complex numbers and visualize their positions in the complex plane.
4. Implement modular addition and multiplication for several moduli.
5. Test which finite modular systems form groups under addition.
6. Investigate which nonzero elements have multiplicative inverses modulo a given integer.
7. Test the group axioms for small finite operation tables.

## 13. Exercises

1. Explain why every integer is rational.
2. Give three examples of irrational numbers.
3. Prove that the sum of two rational numbers is rational.
4. Prove that the product of two rational numbers is rational.
5. Calculate:

   $(3+2i)(1-4i)$

6. Find the conjugate and modulus of:

   $z=5-12i$

7. Explain why $\mathbb{Z}$ is a ring but not a field.
8. Determine whether the nonzero rational numbers form a group under multiplication.
9. Prove the uniqueness of the identity element in a group.
10. Implement addition modulo 5 and verify the group axioms computationally.
11. Find the multiplicative inverse of 3 modulo 7.
12. Explain the difference between a group, a ring, and a field.

## 14. References

1. Enderton, H. B. *Elements of Set Theory*. Academic Press.
2. Fraleigh, J. B. *A First Course in Abstract Algebra*. Pearson.
3. Dummit, D. S., and Foote, R. M. *Abstract Algebra*. Wiley.
4. Rosen, K. H. *Discrete Mathematics and Its Applications*. McGraw-Hill.
5. Rudin, W. *Principles of Mathematical Analysis*. McGraw-Hill.
