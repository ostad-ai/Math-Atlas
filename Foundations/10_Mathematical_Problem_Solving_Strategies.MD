# Foundations 10 — Mathematical Problem-Solving Strategies

## 1. Introduction

Mathematical problem solving is the process of understanding a problem, selecting suitable mathematical tools, developing a solution, and verifying its correctness.

Knowing mathematical definitions, formulas, and theorems is essential, but it is not always enough. Many problems require us to decide *which* concepts to use and *how* to connect them.

A problem-solving strategy, also called a heuristic (راهبرد ابتکاری), is a general approach that can help us discover a solution. A heuristic does not guarantee success or replace mathematical proof. It guides our reasoning and helps us explore possible solutions.

This chapter introduces several widely useful strategies and demonstrates how they can be combined with mathematical reasoning and Python.

## 2. A General Problem-Solving Framework

A useful framework consists of five stages.

### 2.1 Understand the Problem

Identify:

- What information is given?
- What must be found or proved?
- What conditions must the solution satisfy?
- Are there hidden assumptions?
- Is any information unnecessary?

Rewrite the problem in your own words if necessary.

### 2.2 Develop a Plan

Choose a possible strategy:

- Draw a diagram.
- Introduce variables.
- Search for a pattern.
- Consider a simpler case.
- Work backward.
- Divide the problem into smaller parts.
- Look for an invariant.
- Use symmetry.

More than one strategy may be appropriate.

### 2.3 Carry Out the Plan

Perform the calculations, transformations, constructions, or logical deductions required by the selected strategy.

Keep each step mathematically justified.

### 2.4 Verify the Result

Check whether the proposed solution:

- Satisfies the original conditions.
- Uses all necessary assumptions.
- Contains valid mathematical transformations.
- Produces the expected result in relevant special cases.

### 2.5 Reflect and Generalize

After solving the problem, ask:

- Can the solution be simplified?
- Is there another method?
- Does the method work for a broader class of problems?
- Can the result be expressed as a general theorem?

This five-stage framework is closely related to George Pólya's well-known four-step approach: understand the problem, devise a plan, carry out the plan, and look back.

## 3. Fundamental Problem-Solving Strategies

### 3.1 Draw a Diagram

A diagram can make relationships easier to understand.

It is especially useful in:

- Geometry.
- Coordinate problems.
- Problems involving motion.
- Spatial relationships.
- Problems involving several connected quantities.

A diagram does not need to be perfectly accurate. Its purpose is to represent the mathematical relationships clearly.

For example, a geometric problem involving a triangle may become easier when we mark its known angles, side lengths, parallel lines, and relevant points.

### 3.2 Introduce Variables

When a problem contains unknown quantities, represent them using variables.

**Example:**

The sum of three consecutive integers is 75. Find the integers.

Let the first integer be $x$. The next two are $x+1$ and $x+2$.

Therefore,

$$
x+(x+1)+(x+2)=75
$$


Simplifying,

$$
3x+3=75
$$


$$
3x=72
$$


$$
x=24
$$


The integers are:

$$
\boxed{24,\ 25,\ 26}
$$


Introducing variables converts a verbal description into an algebraic representation.

### 3.3 Solve a Simpler Problem First

A complicated problem may become more understandable when we examine a smaller or simpler version.

This strategy is useful when:

- The problem involves a large number of objects.
- A general formula is difficult to identify.
- The relationships are not immediately obvious.
- We suspect a pattern exists.

**Example: Sum of the first $n$ positive odd integers**

Consider the first few cases:

$$
1=1^2
$$


$$
1+3=2^2
$$


$$
1+3+5=3^2
$$


$$
1+3+5+7=4^2
$$


These examples suggest the conjecture:

$$
1+3+5+\cdots +(2n-1)=n^2
$$


The examples help us discover the formula. They do not, by themselves, prove that it holds for every positive integer.

A proof can be developed using mathematical induction, as discussed in Chapter 06.

### 3.4 Search for Patterns

Patterns can reveal relationships that are difficult to see directly.

Consider the sequence:

$$
2,\ 5,\ 8,\ 11,\ 14,\ldots
$$


The difference between consecutive terms is always 3.

This suggests the general formula:

$$
a_n=2+3(n-1)
$$


or

$$
\boxed{a_n=3n-1}
$$


Pattern recognition is particularly useful in:

- Sequences and series.
- Number theory.
- Combinatorics.
- Algebraic identities.
- Algorithm design.

However, a pattern observed in finitely many examples is not automatically a universal mathematical result.

### 3.5 Work Backward

Sometimes it is easier to start from the desired result and reverse the operations that produced it.

**Example:**

A number is multiplied by 2, and then 6 is added. The final result is 20. Find the original number.

Instead of guessing the original number, reverse the operations.

First subtract 6:

$$
20-6=14
$$


Then divide by 2:

$$
14/2=7
$$


Therefore, the original number was:

$$
\boxed{7}
$$


Working backward is useful in:

- Algebraic problems.
- Number puzzles.
- Recursive problems.
- Problems involving sequences of operations.
- Some combinatorial constructions.

### 3.6 Divide the Problem into Subproblems

A complex problem can often be decomposed into smaller problems.

Suppose we want to calculate the average of a collection of numbers.

We can divide the task into:

1. Calculate the sum.
2. Count the numbers.
3. Divide the sum by the count.

Mathematically,

$$
\bar{x}=\frac{x_1+x_2+\cdots+x_n}{n}
$$


This strategy is also fundamental in algorithm design, particularly in divide-and-conquer algorithms.

### 3.7 Use Symmetry

Symmetry means that certain transformations leave the essential structure of a problem unchanged.

Recognizing symmetry can reduce the number of cases that need to be considered.

**Example:**

Suppose two numbers satisfy:

$$
x+y=10
$$


$$
xy=21
$$


The equations are symmetric in $x$ and $y$. Exchanging the two variables does not change either equation.

We can form the quadratic equation whose roots are the two numbers:

$$
t^2-10t+21=0
$$


Factoring,

$$
(t-3)(t-7)=0
$$


Thus,

$$
\boxed{\lbrace x,y\rbrace=\lbrace 3,7\rbrace}
$$


The unordered pair is determined without needing to decide which number must be $x$ or $y$.

### 3.8 Introduce Auxiliary Variables

An auxiliary variable (متغیر کمکی) is a new variable introduced to simplify a problem.

For example, suppose:

$$
x+y=12
$$


and

$$
x-y=4
$$


Adding the equations eliminates $y$:

$$
2x=16
$$


Therefore,

$$
x=8,\qquad y=4
$$


In more complicated problems, a suitable substitution can turn a difficult expression into a simpler one.

For example, if an expression repeatedly contains $x^2+1$, introducing

$$
u=x^2+1
$$


may simplify subsequent calculations.

A substitution must preserve the conditions of the original problem. Any restrictions on the new variable must also be considered.

### 3.9 Look for Invariants

An invariant (ناوردا) is a property that remains unchanged after a sequence of permitted operations.

Invariants are useful for proving that certain outcomes are possible or impossible.

**Example: A coin-flipping problem**

Suppose three coins are initially arranged with exactly one head.

An allowed operation consists of flipping exactly two coins.

Can we reach a state in which all three coins show tails?

Consider the parity of the number of heads.

Initially, the number of heads is:

$$
1
$$


Flipping two coins can change the number of heads by:

$$
-2,\quad 0,\quad \text{or}\quad +2
$$


Therefore, the parity of the number of heads never changes.

The initial number of heads is odd. Consequently, it must remain odd after every permitted operation.

But the all-tails state contains zero heads, which is even.

Therefore:

$$
\boxed{\text{The all-tails state is unreachable.}}
$$


We did not need to examine every possible sequence of operations. The invariant was sufficient to establish impossibility.

### 3.10 Examine Extreme and Special Cases

Testing extreme or special cases can reveal mistakes and suggest a general solution.

For example, if a formula is claimed to hold for every positive integer $n$, test:

$$
n=1,\quad n=2,\quad n=3
$$


For inequalities, consider values near zero, very large values, or boundary conditions.

For geometric problems, examine degenerate or limiting configurations when they are allowed by the assumptions.

Special cases are useful for exploration, but a finite collection of successful tests does not establish a universal theorem.

### 3.11 Eliminate Impossible Cases

Sometimes it is easier to eliminate possibilities than to construct the answer directly.

Useful techniques include:

- Parity arguments.
- Divisibility.
- Bounds and inequalities.
- Contradiction.
- Checking necessary conditions.

For example, the square of an integer is always nonnegative. Therefore, an equation of the form

$$
x^2=-9
$$


has no integer solution.

This simple observation eliminates the possibility without solving the equation through trial and error.

### 3.12 Use Tables and Systematic Enumeration

A table can organize possible values and reveal relationships.

Suppose we want to find all nonnegative integer solutions of:

$$
x+y=6
$$


A systematic table is:

| $x$ | $y$ |
|---:|---:|
| 0 | 6 |
| 1 | 5 |
| 2 | 4 |
| 3 | 3 |
| 4 | 2 |
| 5 | 1 |
| 6 | 0 |

The table makes it clear that there are seven ordered solutions.

Systematic enumeration is particularly useful when the search space is finite and manageable.

## 4. Heuristic Reasoning and Mathematical Proof

A crucial distinction in mathematics is the difference between discovering a possible result and proving it.

A heuristic helps us discover a conjecture (گمانه).

A mathematical proof establishes that the conjecture follows logically from accepted definitions, assumptions, and previously established results.

Consider the statement:

$$
1+3+5+\cdots +(2n-1)=n^2
$$


We may test several values:

| $n$ | Sum of first $n$ odd numbers | $n^2$ |
|---:|---:|---:|
| 1 | 1 | 1 |
| 2 | 4 | 4 |
| 3 | 9 | 9 |
| 4 | 16 | 16 |
| 5 | 25 | 25 |

The table supports the conjecture, but it does not prove it for every positive integer.

To establish the result, we need a valid proof, such as mathematical induction.

This distinction is essential:

- Exploration suggests what might be true.
- Computation provides evidence and helps test examples.
- Mathematical reasoning establishes why a result is true.
- Proof validates the conclusion within a mathematical framework.

## 5. Computational Exploration with Python

Python can help us explore mathematical problems, test conjectures, and examine finite cases.

However, computational testing must not be confused with mathematical proof.

### 5.1 Testing a Conjecture

We can investigate the sum of the first $n$ positive odd integers.

```python
def sum_first_n_odds(n):
    return sum(2 * k - 1 for k in range(1, n + 1))


def test_square_conjecture(max_n=100):
    for n in range(1, max_n + 1):
        actual = sum_first_n_odds(n)
        expected = n ** 2

        if actual != expected:
            return False, n, actual, expected

    return True, None, None, None


result = test_square_conjecture(100)

print(result)
```

The program checks the conjecture for the first 100 positive integers.

A successful result provides computational evidence for those tested values. It does not prove the identity for all positive integers.

### 5.2 Systematic Search for Integer Solutions

Consider:

$$
x^2+y^2=25
$$


We can search for nonnegative integer solutions.

```python
def find_integer_solutions(target):
    solutions = []

    limit = int(target ** 0.5)

    for x in range(limit + 1):
        for y in range(limit + 1):
            if x**2 + y**2 == target:
                solutions.append((x, y))

    return solutions


solutions = find_integer_solutions(25)

print(solutions)
```

The program finds:

```text
[(0, 5), (3, 4), (4, 3), (5, 0)]
```

Because the search is bounded and systematic, it finds every nonnegative integer solution within the specified range.

### 5.3 Exploring a Sequence

We can generate the first several terms of a sequence to investigate its behavior.

```python
def generate_sequence(n):
    return [3 * k - 1 for k in range(1, n + 1)]


terms = generate_sequence(10)

print(terms)
```

Output:

```text
[2, 5, 8, 11, 14, 17, 20, 23, 26, 29]
```

Computational exploration can help us identify patterns, but the general formula still requires mathematical justification.

## 6. Combining Multiple Strategies

Many mathematical problems require more than one strategy.

Consider the following problem:

Find all nonnegative integer pairs satisfying:

$$
x+y=10
$$


$$
x^2+y^2=58
$$


**Step 1 — Understand the conditions**

We know the sum and the sum of squares.

**Step 2 — Use algebraic transformation**

Square the first equation:

$$
(x+y)^2=100
$$


Expand:

$$
x^2+2xy+y^2=100
$$


Using the second equation:

$$
58+2xy=100
$$


Therefore:

$$
xy=21
$$


**Step 3 — Use symmetry and a quadratic equation**

The two numbers have sum 10 and product 21.

They are the roots of:

$$
t^2-10t+21=0
$$


Factoring:

$$
(t-3)(t-7)=0
$$


Thus:

$$
\boxed{(x,y)=(3,7)\text{ or }(7,3)}
$$


This solution combines algebraic transformation, auxiliary reasoning, and symmetry.

## 7. Common Problem-Solving Mistakes

### 7.1 Assuming a Pattern Is a Proof

A formula may work for many examples and still fail later.

Always distinguish between a conjecture and a proven statement.

### 7.2 Using Unjustified Transformations

Every algebraic transformation must be valid under the assumptions of the problem.

For example, dividing both sides of an equation by an expression that may equal zero can remove valid solutions.

### 7.3 Ignoring the Original Conditions

A calculated answer may satisfy a transformed equation but violate a restriction in the original problem.

Always check the final result against the original statement.

### 7.4 Trying Random Approaches Without a Plan

Exploration is useful, but it should be systematic.

Record what has been tested, identify what each attempt reveals, and use that information to guide the next step.

### 7.5 Using Computation as a Substitute for Proof

A program can test thousands or millions of examples. Unless the problem is explicitly finite and the search is exhaustive, this does not establish a universal mathematical statement.

## 8. Worked Examples

### Example 1 — Consecutive Integers

Find four consecutive integers whose sum is 86.

Let the first integer be $x$.

$$
x+(x+1)+(x+2)+(x+3)=86
$$


$$
4x+6=86
$$


$$
4x=80
$$


$$
x=20
$$


Therefore:

$$
\boxed{20,\ 21,\ 22,\ 23}
$$


**Strategies used:** introducing variables and translating a verbal problem into an equation.

### Example 2 — Working Backward

A number is first increased by 4, then multiplied by 3. The final result is 30.

Let the original number be $x$.

$$
3(x+4)=30
$$


$$
x+4=10
$$


$$
x=6
$$


Alternatively, reverse the operations:

$$
30/3=10
$$


$$
10-4=6
$$


**Strategies used:** working backward and algebraic representation.

### Example 3 — The Pigeonhole Principle

Suppose 13 people are in a room.

Can we guarantee that at least two of them were born in the same calendar month?

There are only 12 calendar months.

If every month contained at most one person's birthday month, there could be at most 12 people.

But there are 13 people.

Therefore, at least two people must share a birth month.

This is an application of the pigeonhole principle (اصل لانه‌کبوتری).

More generally, if $n+1$ objects are distributed among $n$ categories, at least one category must contain two or more objects.

## 9. Exercises

### Exercise 1 — Algebraic Representation

The sum of five consecutive integers is 120. Find the integers.

### Exercise 2 — Pattern Recognition

Consider the sequence:

$$
1,\ 4,\ 9,\ 16,\ 25,\ldots
$$


Find a general formula for its $n$-th term and justify your answer.

### Exercise 3 — Working Backward

A number is multiplied by 5, then 7 is subtracted. The result is 38. Find the original number.

### Exercise 4 — Symmetry

Two positive integers have a sum of 12 and a product of 35. Find the integers.

### Exercise 5 — Invariants

Three coins initially show two heads and one tail. At each step, exactly two coins must be flipped.

Is it possible to reach a state in which all three coins show tails? Justify your answer using an invariant.

### Exercise 6 — Computational Exploration

Write a Python program that searches for all nonnegative integer pairs satisfying:

$$
x+y=15
$$


$$
xy=44
$$


Then solve the problem algebraically and compare the results.

### Exercise 7 — Generalization

Investigate the sum:

$$
1+2+3+\cdots+n
$$


Use small cases to formulate a conjecture for its general formula. Then prove the formula mathematically.

## 10. Summary

Mathematical problem solving involves more than applying known formulas. It requires choosing appropriate representations, recognizing relationships, exploring possibilities, and justifying conclusions.

The central strategies introduced in this chapter are:

1. Drawing diagrams.
2. Introducing variables.
3. Solving simpler cases.
4. Recognizing patterns.
5. Working backward.
6. Decomposing problems.
7. Using symmetry.
8. Introducing auxiliary variables.
9. Identifying invariants.
10. Examining special and extreme cases.
11. Eliminating impossible cases.
12. Using tables and systematic enumeration.

These strategies are not isolated techniques. They often work together and provide a foundation for more advanced mathematical reasoning.

## 11. References

1. Pólya, George. *How to Solve It: A New Aspect of Mathematical Method*. Princeton University Press, 1945.
2. Zeitz, Paul. *The Art and Craft of Problem Solving*. Wiley.
3. Engel, Arthur. *Problem-Solving Strategies*. Springer.
4. Schoenfeld, Alan H. *Mathematical Problem Solving*. Academic Press, 1985.
