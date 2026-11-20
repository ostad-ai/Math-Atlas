# Foundations 06 — Mathematical Induction and Recursion

## 1. Introduction

Many mathematical objects are defined in terms of simpler objects of the same type. Similarly, many algorithms solve a problem by reducing it to smaller instances of that problem.

This chapter studies two closely related ideas:

- **Mathematical induction:** a method for proving statements about recursively structured objects and sequences.
- **Recursion:** a method of defining mathematical objects and designing algorithms using smaller instances of themselves.

We will study recursive definitions, recurrence relations, recursive algorithms, termination, correctness, and computational efficiency.

---

## 2. Recursive Definitions

A recursive definition (تعریف بازگشتی) specifies an object using:

1. One or more initial values, called **base cases**.
2. A rule that constructs new values from previously defined values.

### 2.1 Example: Factorial

The factorial of a nonnegative integer $n$ is defined by

$$
0! = 1
$$


and

$$
n! = n(n-1)! \qquad n\geq 1.
$$


The first few values are

$$
\begin{aligned} 0! &= 1,\\ 1! &= 1\cdot 0! = 1,\\ 2! &= 2\cdot 1! = 2,\\ 3! &= 3\cdot 2! = 6,\\ 4! &= 4\cdot 3! = 24. \end{aligned}
$$


The definition is recursive because each factorial is expressed in terms of a smaller factorial.

### 2.2 Example: Fibonacci Sequence

The Fibonacci sequence is defined by

$$
F_0=0,\qquad F_1=1
$$


and

$$
F_n=F_{n-1}+F_{n-2},\qquad n\geq 2.
$$


Its first terms are

$$
0,1,1,2,3,5,8,13,21,\ldots
$$


Each term after the first two is the sum of the preceding two terms.

### 2.3 Recursive Definitions Must Be Well-Founded

A recursive definition must eventually reach its base case.

For example,

$$
f(n)=n f(n-1)
$$


is not a complete definition unless an initial value and a suitable domain are specified.

For factorial, the input is a nonnegative integer, and every recursive step decreases the input by one. Eventually, the argument reaches zero.

This decreasing process is essential for a well-defined recursive computation.

---

## 3. Recurrence Relations

A recurrence relation (رابطه بازگشتی) describes a sequence by expressing its terms using earlier terms.

A recurrence relation generally requires initial conditions to determine a unique sequence.

### 3.1 Arithmetic Sequences

An arithmetic sequence has a constant difference $d$ between consecutive terms.

Its recurrence relation is

$$
a_0=c
$$


$$
a_n=a_{n-1}+d,\qquad n\geq 1.
$$


Expanding the recurrence gives

$$
a_n=c+nd.
$$


**Example**

Let $a_0=3$ and $d=4$.

$$
a_n=a_{n-1}+4.
$$


The sequence is

$$
3,7,11,15,19,\ldots
$$


and its closed-form expression is

$$
a_n=3+4n.
$$


### 3.2 Geometric Sequences

A geometric sequence has a constant ratio $r$ between consecutive terms.

Its recurrence relation is

$$
a_0=c
$$


$$
a_n=ra_{n-1},\qquad n\geq 1.
$$


The closed-form expression is

$$
a_n=cr^n.
$$


**Example**

For $a_0=2$ and $r=3$,

$$
a_n=3a_{n-1}
$$


produces

$$
2,6,18,54,162,\ldots
$$


### 3.3 Linear Recurrence Relations

A linear recurrence relation expresses each term as a linear combination of previous terms.

A second-order homogeneous linear recurrence with constant coefficients has the form

$$
a_n=pa_{n-1}+qa_{n-2}.
$$


The coefficients $p$ and $q$ are constants.

The Fibonacci recurrence is a special case:

$$
F_n=F_{n-1}+F_{n-2}.
$$


### 3.4 Characteristic Equations

For a recurrence of the form

$$
a_n=pa_{n-1}+qa_{n-2},
$$


we try a solution of the form

$$
a_n=r^n.
$$


Substitution gives

$$
r^n=pr^{n-1}+qr^{n-2}.
$$


Dividing by $r^{n-2}$, when $r\neq 0$, gives the characteristic equation

$$
r^2-pr-q=0.
$$


If the characteristic equation has two distinct roots $r_1$ and $r_2$, the general solution is

$$
a_n=Ar_1^n+Br_2^n.
$$


The constants $A$ and $B$ are determined by the initial conditions.

**Example: Fibonacci Sequence**

Its recurrence is

$$
F_n=F_{n-1}+F_{n-2}.
$$


The characteristic equation is

$$
r^2-r-1=0.
$$


Its roots are

$$
r_1=\frac{1+\sqrt5}{2}, \qquad r_2=\frac{1-\sqrt5}{2}.
$$


Using $F_0=0$ and $F_1=1$, we obtain

$$
F_n= \frac{1}{\sqrt5} \left[ \left(\frac{1+\sqrt5}{2}\right)^n - \left(\frac{1-\sqrt5}{2}\right)^n \right].
$$


This is called the **closed-form expression** (فرمول بسته) of the Fibonacci sequence.

---

## 4. Recursive Structures

Recursion is not limited to numerical sequences. It can also define structures such as strings, lists, and trees.

### 4.1 Recursive Definition of Strings

Consider strings over an alphabet $\Sigma$.

A simple recursive definition is:

1. The empty string $\varepsilon$ is a string.
2. If $s$ is a string and $a\in\Sigma$, then $sa$ is also a string.

For example, with

$$
\Sigma=\lbrace 0,1\rbrace,
$$


the following are valid strings:

$$
\varepsilon,\quad 0,\quad 1,\quad 00,\quad 01,\quad 10,\quad 11.
$$


### 4.2 Recursive Definition of Binary Trees

A binary tree can be defined recursively:

1. An empty tree is a binary tree.
2. A node containing a value, together with a left binary tree and a right binary tree, forms a binary tree.

This definition is important in computer science because many tree algorithms naturally use recursion.

### 4.3 Structural Recursion

Structural recursion (بازگشت ساختاری) means defining a function by following the structure of the object it processes.

For example, to calculate the number of nodes in a binary tree:

$$
\mathop{\text{size}}(T)= \begin{cases} 0 & \text{if }T\text{ is empty},\\ 1+\mathop{\text{size}}(L)+\mathop{\text{size}}(R) & \text{otherwise}. \end{cases}
$$


Here, $L$ and $R$ are the left and right subtrees.

---

## 5. Recursive Algorithms

A recursive algorithm (الگوریتم بازگشتی) solves a problem by calling itself on smaller instances.

A correct recursive algorithm needs:

1. **Base case:** a condition under which the algorithm returns without another recursive call.
2. **Recursive case:** a step that reduces the problem to smaller instances.
3. **Termination:** a guarantee that repeated recursive calls eventually reach a base case.

### 5.1 Recursive Factorial

```python
def factorial_recursive(n):
    if n < 0:
        raise ValueError("n must be nonnegative")

    if n == 0:
        return 1

    return n * factorial_recursive(n - 1)


print(factorial_recursive(5))  # 120
```

The function follows the mathematical definition directly.

### 5.2 Iterative Factorial

The same problem can be solved using iteration.

```python
def factorial_iterative(n):
    if n < 0:
        raise ValueError("n must be nonnegative")

    result = 1

    for k in range(1, n + 1):
        result *= k

    return result


print(factorial_iterative(5))  # 120
```

Both implementations calculate $n!$.

Their time complexity is

$$
O(n).
$$


The iterative implementation uses constant auxiliary space, while the recursive implementation uses a call stack whose depth is proportional to $n$.

---

## 6. Fibonacci: Recursive and Efficient Implementations

The Fibonacci sequence illustrates why a mathematically natural recursive definition does not always produce an efficient algorithm.

### 6.1 Naive Recursive Implementation

```python
def fibonacci_recursive(n):
    if n < 0:
        raise ValueError("n must be nonnegative")

    if n == 0:
        return 0

    if n == 1:
        return 1

    return (
        fibonacci_recursive(n - 1)
        + fibonacci_recursive(n - 2)
    )


print(fibonacci_recursive(10))  # 55
```

This implementation repeatedly calculates the same values.

For example, calculating $F_5$ requires calculating $F_3$ more than once.

Its time complexity grows exponentially:

$$
O(\varphi^n),
$$


where

$$
\varphi=\frac{1+\sqrt5}{2}.
$$


### 6.2 Recursive Implementation with Memoization

Memoization (یادسپاری) stores previously calculated results.

```python
def fibonacci_memoized(n, memo=None):
    if n < 0:
        raise ValueError("n must be nonnegative")

    if memo is None:
        memo = {0: 0, 1: 1}

    if n in memo:
        return memo[n]

    memo[n] = (
        fibonacci_memoized(n - 1, memo)
        + fibonacci_memoized(n - 2, memo)
    )

    return memo[n]


print(fibonacci_memoized(10))  # 55
```

Each Fibonacci value is calculated only once.

The time complexity becomes

$$
O(n),
$$


and the storage requirement is also

$$
O(n).
$$


### 6.3 Iterative Fibonacci

```python
def fibonacci_iterative(n):
    if n < 0:
        raise ValueError("n must be nonnegative")

    a, b = 0, 1

    for _ in range(n):
        a, b = b, a + b

    return a


print(fibonacci_iterative(10))  # 55
```

This implementation has

$$
O(n)
$$


time complexity and

$$
O(1)
$$


auxiliary space complexity.

### 6.4 Comparing the Implementations

| Method | Time Complexity | Auxiliary Space |
|---|---:|---:|
| Naive recursion | Exponential | $O(n)$ stack depth |
| Memoized recursion | $O(n)$ | $O(n)$ |
| Iteration | $O(n)$ | $O(1)$ |

The comparison demonstrates an important principle:

**A recursive definition and an efficient recursive algorithm are not necessarily the same thing.**

---

## 7. Recursion and Mathematical Induction

Recursion and mathematical induction (استقرای ریاضی) are closely connected.

- Recursion defines an object using simpler objects.
- Induction proves that a property holds for all objects generated by that definition.

### 7.1 Example: Correctness of Factorial

Recall the recursive definition:

$$
0!=1
$$


$$
n!=n(n-1)!,\qquad n\geq1.
$$


We prove that the recursive algorithm calculates the factorial correctly.

**Base case**

For $n=0$, the algorithm returns $1$.

This agrees with

$$
0!=1.
$$


**Inductive hypothesis**

Assume that the algorithm correctly calculates

$$
(n-1)!.
$$


**Inductive step**

For input $n$, the algorithm returns

$$
n\cdot\mathop{\text{factorial}}(n-1).
$$


By the inductive hypothesis, this equals

$$
n(n-1)!.
$$


By the factorial definition,

$$
n(n-1)!=n!.
$$


Therefore, the algorithm correctly calculates $n!$ for every nonnegative integer $n$.

### 7.2 Strong Induction and Recursive Algorithms

Some recursive algorithms reduce a problem into several smaller problems whose sizes are not necessarily consecutive.

Strong induction (استقرای نیرومند) is useful in these cases.

For example, consider an algorithm that divides an integer $n$ by one of its proper divisors and recursively processes the resulting smaller integer.

To prove correctness, we may assume the property holds for every smaller positive integer, rather than only for $n-1$.

This is precisely the assumption used in strong induction.

---

## 8. Termination of Recursive Algorithms

A recursive algorithm must not continue indefinitely.

One common way to prove termination is to identify a **decreasing measure** (معیار کاهنده).

A decreasing measure must:

1. Have a value in a well-ordered set, such as the nonnegative integers.
2. Strictly decrease at every recursive step.
3. Never decrease indefinitely.

### Example: Factorial

The recursive call changes the argument from $n$ to $n-1$.

For every positive integer $n$,

$$
n-1<n.
$$


Since the input is a nonnegative integer, repeated decreases must eventually reach zero.

Therefore, the factorial algorithm terminates.

### A Non-Terminating Example

```python
def infinite_recursion(n):
    return infinite_recursion(n + 1)
```

This function has no base case and moves farther away from termination.

It will eventually exceed Python's recursion limit.

---

## 9. Recursion Versus Iteration

Iteration (تکرار) uses loops to repeat operations. Recursion uses function calls to solve smaller instances of a problem.

| Property | Recursion | Iteration |
|---|---|---|
| Main mechanism | Function calls | Loops |
| Termination | Reaches a base case | Loop condition becomes false |
| Memory usage | Often uses call stack | Often uses less auxiliary memory |
| Natural applications | Trees, divide-and-conquer | Sequential repetition |
| Potential limitation | Recursion depth | Loop complexity |

Neither method is universally better.

The choice depends on the problem structure, clarity, performance, and programming environment.

---

## 10. Recurrence Relations in Algorithm Analysis

The running time of a recursive algorithm can itself be described by a recurrence relation.

### 10.1 Linear Recursion

Suppose an algorithm performs a constant amount of work and makes one recursive call on an input of size $n-1$.

Its running time satisfies

$$
T(n)=T(n-1)+c,
$$


where $c$ is a constant.

Expanding:

$$
\begin{aligned} T(n)&=T(n-1)+c\\ &=T(n-2)+2c\\ &=T(n-3)+3c\\ &\ \vdots\\ &=T(0)+nc. \end{aligned}
$$


Therefore,

$$
T(n)=O(n).
$$


### 10.2 Divide-and-Conquer Recursion

Suppose an algorithm divides a problem into two subproblems of size $n/2$, solves both recursively, and performs $cn$ additional operations.

Its recurrence is

$$
T(n)=2T(n/2)+cn.
$$


For simplicity, assume $n$ is a power of two.

At each recursion level, the total work outside recursive calls is proportional to $n$.

The number of levels is approximately

$$
\log_2 n.
$$


Therefore,

$$
T(n)=O(n\log n).
$$


This recurrence appears in algorithms such as merge sort.

A systematic study of recurrence solving and algorithmic complexity belongs to the Algorithms section of Math-Atlas.

---

## 11. Worked Examples

### Example 1: Sum of the First $n$ Positive Integers

Define

$$
S(0)=0
$$


and

$$
S(n)=n+S(n-1),\qquad n\geq1.
$$


The closed-form expression is

$$
S(n)=\frac{n(n+1)}{2}.
$$


For $n=5$,

$$
S(5)=1+2+3+4+5=15.
$$


### Example 2: A Recursive Power Function

For a nonnegative integer exponent, define

$$
a^0=1
$$


and

$$
a^n=a\cdot a^{n-1},\qquad n\geq1.
$$


```python
def power_recursive(a, n):
    if n < 0:
        raise ValueError("Exponent must be nonnegative")

    if n == 0:
        return 1

    return a * power_recursive(a, n - 1)


print(power_recursive(2, 5))  # 32
```

This implementation performs $n$ multiplications, giving $O(n)$ time complexity.

A more efficient approach, called exponentiation by squaring, is studied later in the Algorithms section.

### Example 3: Sum of a List

A list can be processed recursively by separating its first element from the remaining elements.

```python
def recursive_sum(values):
    if len(values) == 0:
        return 0

    return values[0] + recursive_sum(values[1:])


numbers = [2, 4, 6, 8]
print(recursive_sum(numbers))  # 20
```

This version creates smaller list slices at each call, so its total copying cost can be quadratic.

An index-based implementation avoids that repeated slicing:

```python
def recursive_sum_indexed(values, index=0):
    if index == len(values):
        return 0

    return (
        values[index]
        + recursive_sum_indexed(values, index + 1)
    )


numbers = [2, 4, 6, 8]
print(recursive_sum_indexed(numbers))  # 20
```

The indexed implementation performs $O(n)$ total work and uses $O(n)$ call-stack space.

---

## 12. Computational Experiments

### Experiment 1: Compare Fibonacci Implementations

Run the following experiment to compare execution times.

```python
from time import perf_counter


def measure_time(function, n):
    start = perf_counter()
    result = function(n)
    elapsed = perf_counter() - start

    return result, elapsed


n = 30

methods = [
    ("Naive recursion", fibonacci_recursive),
    ("Memoization", fibonacci_memoized),
    ("Iteration", fibonacci_iterative),
]

for name, function in methods:
    result, elapsed = measure_time(function, n)

    print(
        f"{name:20s} "
        f"Result: {result:10d} "
        f"Time: {elapsed:.6f} seconds"
    )
```

Questions:

1. Which implementation is fastest?
2. Why does naive recursion become slow for larger inputs?
3. How does memoization reduce repeated calculations?
4. Why does iteration use less auxiliary memory?

### Experiment 2: Generate a Recursive Sequence

```python
def generate_sequence(n, first=3, difference=4):
    if n < 0:
        raise ValueError("n must be nonnegative")

    if n == 0:
        return []

    if n == 1:
        return [first]

    previous = generate_sequence(
        n - 1,
        first,
        difference
    )

    return previous + [
        previous[-1] + difference
    ]


print(generate_sequence(6))
# [3, 7, 11, 15, 19, 23]
```

Questions:

1. What is the recurrence relation?
2. What is its closed-form expression?
3. What is the time complexity of this implementation?
4. How could it be implemented more efficiently using iteration?

---

## 13. Common Mistakes

1. **Missing base cases:** A recursive function may never terminate.
2. **Incorrect base cases:** The algorithm may terminate but return an incorrect result.
3. **No reduction in problem size:** Recursive calls may repeat the same problem indefinitely.
4. **Unnecessary repeated calculations:** Naive Fibonacci recursion is a classic example.
5. **Ignoring stack limitations:** Deep recursion may exceed the programming language's recursion limit.
6. **Confusing a recurrence with its solution:** A recurrence describes how values depend on one another; a closed form gives an explicit expression for the values.
7. **Assuming recursion is always efficient:** A clear recursive definition can lead to an inefficient implementation.

---

## 14. Exercises

### Exercise 1 — Recursive Definitions

Define the following recursively:

1. The sum of the first $n$ nonnegative integers.
2. The powers of 3.
3. The sequence $2,5,8,11,\ldots$.

### Exercise 2 — Recurrence Relations

Find the first six terms of each sequence.

1. $a_0=4,\quad a_n=a_{n-1}+3$.
2. $b_0=2,\quad b_n=2b_{n-1}$.
3. $c_0=1,\quad c_1=2,\quad c_n=c_{n-1}+c_{n-2}$.

### Exercise 3 — Closed Forms

Find a closed-form expression for:

1. $a_0=5,\quad a_n=a_{n-1}+2$.
2. $b_0=3,\quad b_n=4b_{n-1}$.

### Exercise 4 — Recursive Programming

Implement recursive functions for:

1. Calculating the sum of the digits of a nonnegative integer.
2. Reversing a string.
3. Calculating the greatest common divisor using Euclid's algorithm.
4. Finding the maximum element of a nonempty list.

### Exercise 5 — Correctness

Prove by mathematical induction that

$$
1+2+\cdots+n=\frac{n(n+1)}{2}
$$


for every positive integer $n$.

### Exercise 6 — Termination

For each recursive function, identify a decreasing measure and explain whether termination is guaranteed.

1. $f(n)=f(n-1)$, with $f(0)=1$.
2. $g(n)=g(n+1)$, with no base case.
3. $h(n)=h(\lfloor n/2\rfloor)$, with a base case at $n\leq1$.

### Exercise 7 — Algorithm Analysis

Solve the following recurrences:

1. $T(n)=T(n-1)+2$, with $T(0)=1$.
2. $T(n)=T(n/2)+1$, with $T(1)=1$.
3. $T(n)=2T(n/2)+n$, with $T(1)=1$.

Assume suitable integer input sizes, such as powers of two, where necessary.

---

## 15. References

1. Kenneth H. Rosen, *Discrete Mathematics and Its Applications*. McGraw-Hill.
2. Susanna S. Epp, *Discrete Mathematics with Applications*. Cengage Learning.
3. Ronald L. Graham, Donald E. Knuth, and Oren Patashnik, *Concrete Mathematics*. Addison-Wesley.
4. Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, and Clifford Stein, *Introduction to Algorithms*. MIT Press.
5. Michael T. Goodrich, Roberto Tamassia, and Michael H. Goldwasser, *Data Structures and Algorithms in Python*. Wiley.

---

## 16. Summary

This chapter introduced recursive mathematical definitions and their computational applications.

The main ideas are:

- Recursive definitions use base cases and recursive rules.
- Recurrence relations describe sequences through previous terms.
- Some recurrence relations can be transformed into closed-form expressions.
- Recursive algorithms solve problems through smaller instances.
- Mathematical induction provides a natural method for proving recursive algorithms correct.
- Termination can often be established using a decreasing measure.
- Memoization can eliminate repeated calculations.
- Recurrence relations can describe the running time of recursive algorithms.

Recursion is a fundamental connection between mathematical reasoning, discrete structures, and algorithm design.
