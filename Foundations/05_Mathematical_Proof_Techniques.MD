# Foundations 05 — Mathematical Proof Techniques

## 1. Introduction

Mathematical proof (برهان ریاضی) is a logical argument that establishes the truth of a mathematical statement from accepted axioms, definitions, and previously proven results.

A mathematical proof must establish a conclusion for every case covered by the statement. Checking several examples may provide evidence, but it does not generally establish a universal claim.

This chapter introduces the principal proof techniques used throughout mathematics.

## 2. Mathematical Statements and Quantifiers

Before constructing a proof, we must understand precisely what is being asserted.

### 2.1 Universal Statements

A universal statement (گزارهٔ همگانی) claims that a property holds for every element of a specified domain.

$$
\forall x\in A,\ P(x)
$$

Example:

$$
\forall n\in\mathbb{Z},\quad n+n=2n
$$

To prove a universal statement, we consider an arbitrary element of the domain and establish the required property.

### 2.2 Existential Statements

An existential statement (گزارهٔ وجودی) claims that at least one element satisfies a property.

$$
\exists x\in A,\ P(x)
$$

Example:

$$
\exists n\in\mathbb{Z},\quad n^2=9
$$

A single valid example is sufficient to establish an existential statement.

### 2.3 Negation of Quantified Statements

The negation of a universal statement is existential:

$$
\neg(\forall x\in A,\ P(x))
\iff
\exists x\in A,\ \neg P(x)
$$

The negation of an existential statement is universal:

$$
\neg(\exists x\in A,\ P(x))
\iff
\forall x\in A,\ \neg P(x)
$$

These equivalences are essential when constructing counterexamples.

## 3. Direct Proof

A **direct proof** (اثبات مستقیم) establishes a conclusion by starting from the assumptions and applying definitions, algebraic transformations, and previously established results.

To prove:

$$
P\Rightarrow Q
$$

we assume $P$ and derive $Q$.

### Example 1: The Sum of Two Even Integers Is Even

**Theorem:** The sum of two even integers is even.

**Proof:**

Let $a,b\in\mathbb{Z}$ be even.

By definition, there exist integers $k,m$ such that:

$$
a=2k,\qquad b=2m
$$

Then:

$$
a+b=2k+2m
$$

$$
=2(k+m)
$$

Since $k+m\in\mathbb{Z}$, the sum is divisible by 2.

Therefore, $a+b$ is even.

### Example 2: The Product of Two Odd Integers Is Odd

**Theorem:** The product of two odd integers is odd.

**Proof:**

Let:

$$
a=2k+1,\qquad b=2m+1
$$

where $k,m\in\mathbb{Z}$.

Then:

$$
\begin{aligned}
ab
&=(2k+1)(2m+1)\\
&=4km+2k+2m+1\\
&=2(2km+k+m)+1
\end{aligned}
$$

The expression $2km+k+m$ is an integer.

Therefore, $ab$ is odd.

## 4. Proof by Contrapositive

The **contrapositive** (عکس نقیض) of an implication is logically equivalent to the original implication.

For:

$$
P\Rightarrow Q
$$

the contrapositive is:

$$
\neg Q\Rightarrow\neg P
$$

Sometimes proving the contrapositive is easier than proving the original statement.

### Example

**Theorem:** If $n^2$ is even, then $n$ is even.

**Proof by contrapositive:**

The contrapositive is:

If $n$ is odd, then $n^2$ is odd.

Suppose:

$$
n=2k+1
$$

for some $k\in\mathbb{Z}$.

Then:

$$
\begin{aligned}
n^2
&=(2k+1)^2\\
&=4k^2+4k+1\\
&=2(2k^2+2k)+1
\end{aligned}
$$

Thus $n^2$ is odd.

The contrapositive is true, so the original statement is true.

## 5. Proof by Contradiction

A **proof by contradiction** (برهان خلف) assumes that the statement to be proved is false and derives a logical contradiction.

To prove $P$, we assume:

$$
\neg P
$$

and show that this assumption leads to an impossibility.

### Example: There Is No Greatest Integer

**Theorem:** There is no greatest integer.

**Proof:**

Suppose, for contradiction, that a greatest integer $M$ exists.

Since $M$ is an integer:

$$
M+1\in\mathbb{Z}
$$

But:

$$
M+1>M
$$

This contradicts the assumption that $M$ is the greatest integer.

Therefore, no greatest integer exists.

### Example: The Square Root of 2 Is Irrational

**Theorem:**

$$
\sqrt2\notin\mathbb{Q}
$$

**Proof:**

Suppose:

$$
\sqrt2=\frac{a}{b}
$$

where $a,b\in\mathbb{Z}$, $b\neq0$, and the fraction is in lowest terms.

Squaring both sides:

$$
2=\frac{a^2}{b^2}
$$

Therefore:

$$
a^2=2b^2
$$

Hence $a^2$ is even, so $a$ is even.

Write:

$$
a=2k
$$

Substituting:

$$
4k^2=2b^2
$$

Thus:

$$
b^2=2k^2
$$

Therefore $b$ is also even.

Both $a$ and $b$ are divisible by 2, contradicting the assumption that the fraction was in lowest terms.

Consequently:

$$
\sqrt2\notin\mathbb{Q}
$$

## 6. Proof by Cases

A **proof by cases** (اثبات حالت‌به‌حالت) divides a problem into a finite collection of possibilities and proves the statement in every case.

### Example: The Square of Every Integer Is Nonnegative

**Theorem:**

$$
n^2\geq0
$$

for every integer $n$.

**Proof:**

There are two cases.

**Case 1:** $n\geq0$.

Then:

$$
n^2\geq0
$$

**Case 2:** $n<0$.

Then $-n>0$, and:

$$
n^2=(-n)^2\geq0
$$

Both cases establish the required inequality.

Therefore:

$$
n^2\geq0
$$

for every integer $n$.

## 7. Proof by Mathematical Induction

Mathematical induction (استقرای ریاضی) proves a statement for all natural numbers by establishing a base case and an inductive step.

Suppose we want to prove:

$$
P(n)
$$

for all $n\geq n_0$.

The procedure is:

1. Prove $P(n_0)$.
2. Assume $P(k)$ holds for an arbitrary $k\geq n_0$.
3. Use this assumption to prove $P(k+1)$.

### Example 1: Sum of the First $n$ Natural Numbers

Prove:

$$
1+2+\cdots+n=\frac{n(n+1)}2
$$

for $n\geq1$.

**Base case:**

For $n=1$:

$$
1=\frac{1(2)}2
$$

**Inductive hypothesis:**

Assume:

$$
1+2+\cdots+k=\frac{k(k+1)}2
$$

**Inductive step:**

Consider the next case:

$$
1+2+\cdots+k+(k+1)
$$

Using the inductive hypothesis:

$$
=\frac{k(k+1)}2+(k+1)
$$

Factor:

$$
=\frac{(k+1)(k+2)}2
$$

This is the required expression for $k+1$.

Therefore, the formula holds for every $n\geq1$.

### Example 2: Sum of the First $n$ Odd Numbers

Prove:

$$
1+3+5+\cdots+(2n-1)=n^2
$$

**Base case:**

For $n=1$:

$$
1=1^2
$$

**Inductive hypothesis:**

Assume:

$$
1+3+\cdots+(2k-1)=k^2
$$

**Inductive step:**

Add the next odd number:

$$
\begin{aligned}
1+3+\cdots+(2k-1)+(2k+1)
&=k^2+2k+1\\
&=(k+1)^2
\end{aligned}
$$

Therefore, the statement holds for all positive integers $n$.

## 8. Strong Mathematical Induction

**Strong induction** (استقرای نیرومند) is a variation of mathematical induction.

Instead of assuming only $P(k)$, we assume that all previous statements are true:

$$
P(n_0),P(n_0+1),\ldots,P(k)
$$

We then prove $P(k+1)$.

### Example: Every Integer Greater Than 1 Has a Prime Factor

**Theorem:** Every integer $n>1$ is either prime or can be expressed as a product of prime numbers.

**Proof by strong induction:**

**Base case:**

For $n=2$, the statement holds because 2 is prime.

**Inductive hypothesis:**

Assume the statement holds for all integers from 2 through $k$.

**Inductive step:**

Consider $k+1$.

If $k+1$ is prime, the statement is already true.

Otherwise, it is composite, so:

$$
k+1=ab
$$

where:

$$
1<a<k+1,\qquad 1<b<k+1
$$

By the inductive hypothesis, both $a$ and $b$ can be expressed as products of primes.

Therefore, their product $k+1$ can also be expressed as a product of primes.

This completes the induction.

## 9. Disproof by Counterexample

A **counterexample** (نمونهٔ نقض) is a single valid example that demonstrates that a universal statement is false.

### Example

Consider the statement:

"Every prime number is odd."

This statement is false because:

$$
2
$$

is prime and even.

Thus, 2 is a counterexample.

A universal statement requires every element of its domain to satisfy the property. One counterexample is sufficient to disprove it.

## 10. Existence and Uniqueness Proofs

Some mathematical statements assert that an object exists and is unique.

These proofs have two parts.

### 10.1 Existence

We demonstrate that at least one object satisfies the required conditions.

### 10.2 Uniqueness

We assume that two objects satisfy the conditions and prove that they must be equal.

### Example: Uniqueness of the Additive Identity

Suppose $e$ and $e'$ are both additive identities.

Then:

$$
e+e'=e'
$$

because $e$ is an identity.

Also:

$$
e+e'=e
$$

because $e'$ is an identity.

Therefore:

$$
e=e'
$$

The additive identity is unique.

## 11. Common Logical Errors in Proofs

A rigorous proof must avoid invalid logical reasoning.

### 11.1 Affirming the Consequent

The following argument is invalid:

$$
P\Rightarrow Q
$$

$$
Q
$$

$$
\therefore P
$$

For example:

"If a number is divisible by 4, it is even."

A number is even.

We cannot conclude that it is divisible by 4.

The number 6 is a counterexample.

### 11.2 Denying the Antecedent

The following argument is also invalid:

$$
P\Rightarrow Q
$$

$$
\neg P
$$

$$
\therefore\neg Q
$$

For example:

"If a number is divisible by 4, it is even."

A number is not divisible by 4.

It may still be even, as in the case of 6.

### 11.3 Circular Reasoning

Circular reasoning (استدلال دوری) occurs when a proof assumes the conclusion it is supposed to establish.

A proof must derive its conclusion from accepted premises, not use the conclusion as an unsupported assumption.

### 11.4 Confusing Examples with Proofs

Checking a statement for many numerical examples does not establish that it holds for every integer or real number.

Examples can help discover patterns and test conjectures, but a general proof is still required.

## 12. Python Implementation

Python can help investigate mathematical conjectures, search for counterexamples, and verify finite instances of mathematical statements.

It cannot replace a general proof over an infinite domain.

### 12.1 Searching for Counterexamples

```python
def find_counterexample(statement, candidates):
    """
    Find the first candidate for which
    a proposed universal statement is false.
    """
    for x in candidates:
        if not statement(x):
            return x

    return None


# Incorrect conjecture:
# Every prime number is odd.

def is_odd_prime(n):
    if n < 2:
        return True

    if n % 2 == 0:
        return False

    for divisor in range(3, int(n ** 0.5) + 1, 2):
        if n % divisor == 0:
            return False

    return True


counterexample = find_counterexample(
    is_odd_prime,
    range(2, 100)
)

print("Counterexample:", counterexample)
```

### 12.2 Checking an Inductive Identity

```python
def verify_sum_formula(limit):
    """
    Test the identity:
    1 + 2 + ... + n = n(n + 1) / 2
    for a finite range of positive integers.
    """
    for n in range(1, limit + 1):
        left = sum(range(1, n + 1))
        right = n * (n + 1) // 2

        if left != right:
            return False, n

    return True, None


result = verify_sum_formula(1000)

print(result)
```

This verifies the identity for the tested values, not for all positive integers.

### 12.3 Testing the Parity of Squares

```python
def test_square_parity(limit):
    """
    Test whether n and n^2 have
    the same parity for a finite range.
    """
    for n in range(-limit, limit + 1):
        if (n % 2) != ((n * n) % 2):
            return False, n

    return True, None


print(test_square_parity(1000))
```

### 12.4 Generating an Inductive Sequence

```python
def triangular_numbers(count):
    """
    Generate the first 'count' triangular numbers.
    """
    result = []

    for n in range(1, count + 1):
        value = n * (n + 1) // 2
        result.append(value)

    return result


print(triangular_numbers(10))
```

## 13. Worked Examples

### Example 1: Direct Proof

Prove that the difference of two odd integers is even.

**Solution:**

Let:

$$
a=2k+1,\qquad b=2m+1
$$

Then:

$$
a-b=2k+1-(2m+1)
$$

$$
=2(k-m)
$$

Since $k-m$ is an integer, the difference is even.

### Example 2: Contrapositive

Prove that if $n^2$ is odd, then $n$ is odd.

**Solution:**

The contrapositive is:

If $n$ is even, then $n^2$ is even.

Let:

$$
n=2k
$$

Then:

$$
n^2=4k^2=2(2k^2)
$$

Therefore, $n^2$ is even.

Hence the original statement is true.

### Example 3: Mathematical Induction

Prove:

$$
1+2+4+\cdots+2^n=2^{n+1}-1
$$

for $n\geq0$.

**Solution:**

Base case:

$$
1=2^1-1
$$

Inductive hypothesis:

$$
1+2+\cdots+2^k=2^{k+1}-1
$$

Inductive step:

$$
\begin{aligned}
1+2+\cdots+2^k+2^{k+1}
&=2^{k+1}-1+2^{k+1}\\
&=2^{k+2}-1
\end{aligned}
$$

Therefore, the identity holds for all $n\geq0$.

## 14. Computational Experiments

1. Generate numerical examples of statements that can be proved directly.
2. Search for counterexamples to incorrect universal conjectures.
3. Compare direct proofs with their contrapositives.
4. Implement a program that checks the first $n$ cases of an inductive identity.
5. Explore the difference between ordinary induction and strong induction.
6. Write a program that searches for prime factors of integers.
7. Construct examples of invalid logical arguments and identify the exact inference error.

For every experiment, explain what the computation establishes and what still requires mathematical proof.

## 15. Exercises

1. Prove directly that the sum of three even integers is even.
2. Prove that the product of an even integer and an odd integer is even.
3. Prove by contrapositive that if $n^2$ is divisible by 3, then $n$ is divisible by 3.
4. Prove by contradiction that there is no smallest positive real number.
5. Disprove the statement "Every odd integer is prime."
6. Prove by induction:

   $1+3+5+\cdots+(2n-1)=n^2$

7. Prove by induction:

   $1+2+\cdots+n=\frac{n(n+1)}2$

8. Use strong induction to prove that every integer greater than 1 has a prime factor.
9. Explain the difference between a proof by contradiction and a proof by contrapositive.
10. Give an example of an existential statement and prove it.
11. Give an example of a universal statement and disprove it using a counterexample.
12. Explain why checking one million numerical examples does not establish a universal theorem.

## 16. References

1. Velleman, D. J. *How to Prove It: A Structured Approach*. Cambridge University Press.
2. Hammack, R. *Book of Proof*. Virginia Commonwealth University.
3. Epp, S. S. *Discrete Mathematics with Applications*. Cengage Learning.
4. Rosen, K. H. *Discrete Mathematics and Its Applications*. McGraw-Hill.
5. Enderton, H. B. *A Mathematical Introduction to Logic*. Academic Press.
