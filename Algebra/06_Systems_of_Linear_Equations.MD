# Algebra 06 — Systems of Linear Equations

## 1. Introduction

A **system of linear equations** is a collection of linear equations that must be satisfied at the same time. The solution is not a value that makes one equation true in isolation; it is an ordered pair that satisfies every equation in the system.

For two variables, each nondegenerate linear equation describes a line in the Cartesian plane. Solving the system means finding the point or points common to all of its lines. This connects the algebraic methods in Chapters 03 and 05 with the geometric interpretation of graphs.

Unless a problem states otherwise, this chapter works over the real numbers and studies systems in two variables. Applications may impose additional restrictions such as nonnegative or integer solutions.

### Learning objectives

After this chapter, you should be able to:

- Define a solution of a system and distinguish it from a solution of one equation.
- Interpret a two-variable system graphically as the intersection of two lines.
- Solve systems by substitution and elimination, explaining why each transformation preserves the solution set.
- Classify a system as consistent or inconsistent and, when consistent, independent or dependent.
- Recognize unique-solution, no-solution, and infinitely-many-solution cases, including degenerate equations.
- Use exact arithmetic to solve rational-coefficient systems.
- Translate contextual problems into systems, state constraints, and check the result in the original context.

## 2. What is a system?

A typical system of two linear equations is

$$
\begin{cases}
a_1x+b_1y=c_1,\\
a_2x+b_2y=c_2,
\end{cases}
$$

where the coefficients and constants are fixed real numbers. The variables $x$ and $y$ are the unknowns. Each equation is linear because each variable appears only to the first power and variables are not multiplied by one another.

An ordered pair $(r,s)$ is a **solution of the system** if substituting $x=r$ and $y=s$ makes every equation true.

The **solution set** is therefore the intersection of the individual equation-solution sets. In set notation,

$$
S=\left\lbrace (x,y)\in\mathbb{R}^2 : a_1x+b_1y=c_1\text{ and }a_2x+b_2y=c_2 \right\rbrace.
$$

The word *and* is essential: both equations must hold at once.

### Example 1 — Check an ordered pair

Consider

$$
\begin{cases}
2x+y=11,\\
x-y=1.
\end{cases}
$$

Test $(4,3)$:

- First equation: $2(4)+3=11$.
- Second equation: $4-3=1$.

Both statements are true, so $(4,3)$ is a solution. The pair $(5,1)$ is not a solution because it satisfies the first equation but not the second: $5-1=4\ne1$.

## 3. Equivalent systems and valid transformations

Two systems are **equivalent** when they have exactly the same solution set. A solving method is valid when it replaces a system with an equivalent one or otherwise preserves the complete solution set under clearly stated conditions.

The following operations preserve equivalence:

1. Interchange the two equations.
2. Multiply one equation by a nonzero constant.
3. Replace one equation by itself plus a constant multiple of the other equation.

For example, replacing equation $E_2$ by $E_2-2E_1$ is reversible: the original $E_2$ is recovered by adding $2E_1$ back. Thus the pair satisfies the original system exactly when it satisfies the transformed system.

Multiplying an equation by zero is not an allowed equivalence-preserving operation: it can erase information. Likewise, adding two equations and then discarding both originals is not generally justified unless the lost information can be recovered.

### Example 2 — An equivalent system by elimination

Start with

$$
\begin{cases}
2x+y=11,\\
x-y=1.
\end{cases}
$$

Replace the first equation by the sum of the two equations:

$$
\begin{cases}
3x=12,\\
x-y=1.
\end{cases}
$$

The first equation gives $x=4$; the second then gives $y=3$. The replacement is reversible because the original first equation can be recovered by subtracting the original second equation from the new first equation.

## 4. Graphical interpretation

Each equation $a x+b y=c$, with $(a,b)\ne(0,0)$, represents a line in the plane. A solution of the system is a point belonging to both lines, so it is an intersection point.

Two distinct lines in a plane are either parallel and disjoint or intersect at exactly one point. If the two equations describe the same line, every point on that line satisfies both equations.

| Geometric situation | Algebraic classification | Number of solutions |
|---|---|---:|
| Two lines intersect once | Consistent and independent | 1 |
| Two distinct parallel lines | Inconsistent | 0 |
| The equations describe the same line | Consistent and dependent | Infinitely many |

The graphical method is useful for understanding and estimating. A hand-drawn intersection may not give an exact answer, especially when the intersection lies between grid marks. Use algebra to obtain an exact solution when the coefficients are exact.

### Example 3 — Read the intersection

Consider

$$
\begin{cases}
y=2x+1,\\
y=-x+7.
\end{cases}
$$

At an intersection, the two expressions for $y$ are equal:

$$
2x+1=-x+7.
$$

Thus $3x=6$, so $x=2$ and $y=5$. The lines meet at $(2,5)$, which is the unique solution.

### Example 4 — Parallel lines and the same line

The lines $y=2x+1$ and $y=2x-3$ have the same slope but different intercepts. They are distinct parallel lines, so the system has no solution.

The equations $2x-y=4$ and $4x-2y=8$ describe the same line because the second equation is twice the first. Every point on that line is a solution, so there are infinitely many solutions.

## 5. Solving by substitution

The **substitution method** uses one equation to express one variable in terms of the other, then substitutes that expression into the remaining equation.

A reliable procedure is:

1. Choose an equation in which a variable can be isolated conveniently.
2. Solve that equation for the chosen variable. If division is needed, verify that the coefficient being divided by is nonzero.
3. Substitute the expression into the other equation.
4. Solve the resulting one-variable equation.
5. Substitute back to find the second variable.
6. Check the ordered pair in both original equations.

### Example 5 — Substitution with integer coefficients

Solve

$$
\begin{cases}
2x+y=11,\\
x-y=1.
\end{cases}
$$

The second equation gives $y=x-1$. Substitute this into the first:

$$
2x+(x-1)=11.
$$

Therefore $3x=12$ and $x=4$. Then $y=4-1=3$. The solution is $(4,3)$; Example 1 already verified it in both original equations.

### Example 6 — Substitution with fractions

Solve

$$
\begin{cases}
\frac12x+y=4,\\
x-2y=-2.
\end{cases}
$$

The first equation gives $y=4-\frac12x$. Substitute into the second:

$$
x-2\left(4-\frac12x\right)=-2,
$$

so $x-8+x=-2$, hence $2x=6$ and $x=3$. Then $y=4-3/2=5/2$. The solution is $(3,5/2)$.

## 6. Solving by elimination

The **elimination method** combines equations to remove one variable. It is especially useful when the coefficients of one variable are already equal or opposites, or can be made so by multiplying an equation by a nonzero constant.

A reliable procedure is:

1. Write both equations in the same variable order, with like terms aligned.
2. Choose a variable to eliminate.
3. Multiply one or both equations by nonzero constants if needed.
4. Add or subtract the equations to eliminate the chosen variable.
5. Solve the remaining one-variable equation.
6. Substitute back and check both original equations.

The justification is the equivalence-preserving row operation from Section 3. Adding a multiple of one equation to the other does not change which ordered pairs satisfy both equations.

### Example 7 — Eliminate by addition

Solve

$$
\begin{cases}
3x+2y=16,\\
5x-2y=8.
\end{cases}
$$

Add the equations. The $y$-terms cancel:

$$
8x=24,
$$

so $x=3$. Substitute into the first equation:

$$
9+2y=16,
$$

which gives $y=7/2$. The solution is $(3,7/2)$.

### Example 8 — Make coefficients opposites

Solve

$$
\begin{cases}
2x+3y=13,\\
4x+y=11.
\end{cases}
$$

Multiply the second equation by $-3$:

$$
-12x-3y=-33.
$$

Add it to the first equation:

$$
-10x=-20,
$$

so $x=2$. From $4x+y=11$, we obtain $y=3$. The solution is $(2,3)$.

### Example 9 — Eliminate with fractional coefficients

Solve

$$
\begin{cases}
\frac12x+\frac13y=2,\\
 x-\frac13y=1.
\end{cases}
$$

Add the equations directly after aligning terms:

$$
\frac32x=3,
$$

so $x=2$. The second equation gives $2-y/3=1$, hence $y=3$. The solution is $(2,3)$.

## 7. Classifying the result of elimination

Elimination does more than find numerical values. The final equation tells us how many solutions the system has.

### 7.1 One solution

If elimination produces a statement such as $3x=12$, one variable has a unique value. Substitution then determines the other variable. The system is **consistent** (at least one solution exists) and **independent** (the equations do not reduce to the same line).

### 7.2 No solution

If elimination produces a false statement such as $0=5$, the equations cannot both be true. The system is **inconsistent** and has no solution.

### 7.3 Infinitely many solutions

If elimination produces an identity such as $0=0$, one equation is redundant relative to the other, provided the reduction was done by valid reversible operations. The equations describe the same line, so the system is **consistent** and **dependent** and has infinitely many solutions.

The statements $0=0$ and $0=5$ are not answers for $x$ or $y$. They describe the compatibility of the original equations.

### Example 10 — An identity after elimination

Solve

$$
\begin{cases}
2x+3y=6,\\
4x+6y=12.
\end{cases}
$$

Subtract twice the first equation from the second. The result is $0=0$. The second equation adds no new restriction. The solution set is the entire line $2x+3y=6$, not a single pair.

### Example 11 — A contradiction after elimination

Solve

$$
\begin{cases}
2x-y=1,\\
4x-2y=5.
\end{cases}
$$

Subtract twice the first equation from the second. The left side becomes zero, but the right side becomes $3$, giving $0=3$. There is no solution. The two lines are parallel and distinct.

## 8. Consistency, independence, and dependence

The terminology can be summarized as follows:

| Term | Meaning | Possible number of solutions |
|---|---|---:|
| Consistent | At least one solution exists | 1 or infinitely many |
| Inconsistent | No solution exists | 0 |
| Independent system | The equations impose independent restrictions | 1 in a two-variable, two-equation system with nondegenerate rows |
| Dependent system | At least one equation is redundant | Infinitely many, if consistent |

For ordinary systems of two nondegenerate line equations, consistent independent systems have one intersection; consistent dependent systems represent the same line. Degenerate equations such as $0x+0y=0$ or $0x+0y=5$ are handled explicitly in Section 10 and in the Python classifier.

## 9. A coefficient test for a unique solution

For the system

$$
\begin{cases}
a_1x+b_1y=c_1,\\
a_2x+b_2y=c_2,
\end{cases}
$$

define the coefficient determinant

$$
D=a_1b_2-a_2b_1.
$$

If $D\ne0$, the system has exactly one solution. This criterion is a compact form of the elimination result: the two coefficient rows are not proportional, so one variable cannot disappear from both equations in a way that leaves a dependent pair.

When $D\ne0$, elimination gives

$$
x=\frac{c_1b_2-c_2b_1}{D},\qquad
y=\frac{a_1c_2-a_2c_1}{D}.
$$

These formulas are valid only when $D$ is nonzero. If $D=0$, do not divide by it. Instead use elimination and inspect whether the resulting statement is an identity or a contradiction. This distinction also requires care with zero coefficient rows.

### Example 12 — Use the determinant as a uniqueness test

For

$$
\begin{cases}
2x+y=11,\\
x-y=1,
\end{cases}
$$

we have $D=2(-1)-1(1)=-3\ne0$, so there is a unique solution. The formulas give $x=4$ and $y=3$.

The determinant is a test and a shortcut, not a replacement for checking the solution in the original equations.

## 10. Degenerate equations and zero rows

The general form $ax+by=c$ includes two special cases when $a=b=0$:

- $0x+0y=0$ is true for every ordered pair. It imposes no restriction.
- $0x+0y=k$, where $k\ne0$, is false for every ordered pair. It makes the whole system inconsistent.

A zero row must not be treated as a line. It represents either the entire plane or the empty set.

### Example 13 — One identity and one line

Consider

$$
\begin{cases}
0x+0y=0,\\
x+2y=4.
\end{cases}
$$

The first equation imposes no restriction. Every point on the line $x+2y=4$ satisfies the system, so there are infinitely many solutions.

### Example 14 — A contradiction in a zero row

Consider

$$
\begin{cases}
0x+0y=3,\\
x+2y=4.
\end{cases}
$$

The first equation is impossible. The system has no solution, regardless of the second equation.

If both equations have zero coefficients, then the system has infinitely many solutions only when both constants are zero; otherwise it has no solution.

## 11. Applications: translating a context into a system

A contextual system should be built in a deliberate order:

1. Define each unknown with its meaning and unit.
2. Identify two independent relationships supplied by the context.
3. Translate each relationship into an equation.
4. Solve the system using a suitable method.
5. Check the result in both equations and in the original context.
6. Apply contextual restrictions such as nonnegative or integer values.

A mathematically valid real solution may be unsuitable if the quantities count people, objects, or events. In such cases, the model's domain must be restricted to integers or another appropriate set.

### Example 15 — Ticket sales

A school sells 32 tickets. Adult tickets cost 11 currency units and student tickets cost 7 currency units. Total revenue is 284 currency units. How many of each ticket were sold?

Let $a$ be the number of adult tickets and $s$ the number of student tickets. The count and revenue relationships are

$$
\begin{cases}
a+s=32,\\
11a+7s=284.
\end{cases}
$$

Multiply the first equation by $7$ and subtract it from the second:

$$
(11a+7s)-(7a+7s)=284-224,
$$

so $4a=60$ and $a=15$. Then $s=17$. Both values are nonnegative integers and satisfy the original conditions. The school sold 15 adult tickets and 17 student tickets.

### Example 16 — Two quantities from total and difference

Two numbers have sum 41, and the larger exceeds the smaller by 9. Let $x$ be the larger and $y$ the smaller:

$$
\begin{cases}
x+y=41,\\
x-y=9.
\end{cases}
$$

Adding gives $2x=50$, hence $x=25$ and $y=16$. The conditions are satisfied because $25+16=41$ and $25-16=9$.

### Example 17 — A distance and time model

Two cyclists travel at constant speeds on the same straight route. At a chosen time origin, cyclist A is 18 km from the start and travels at 12 km/h. Cyclist B is 6 km from the start and travels at 16 km/h in the same direction. When are they at the same position?

Let $t$ be time in hours after the chosen origin, and let $d$ be distance in kilometres. Their models are $d_A=18+12t$ and $d_B=6+16t$. Set the positions equal:

$$
18+12t=6+16t.
$$

Thus $12=4t$, so $t=3$ hours. The common position is $d=54$ km. The answer assumes both constant-speed models remain valid for at least three hours and that the chosen origin is meaningful for both cyclists.

## 12. Python: exact classification and solution

The following function classifies a two-equation system with exact integer or `Fraction` input. It deliberately rejects floats: a decimal such as `0.1` is not represented exactly by binary floating-point. Use `Fraction("0.1")` when the intended input is the exact decimal rational one tenth.

The function returns one of three classifications:

- `unique`: one ordered pair, included in `solution`.
- `infinite`: infinitely many solutions; no single pair is returned.
- `none`: no solution.

```python
from fractions import Fraction


def _as_exact_fraction(value):
    """Accept exact integers and Fractions, but not bools or floats."""
    if isinstance(value, bool) or not isinstance(value, (int, Fraction)):
        raise TypeError("Coefficients must be integers or Fraction values.")
    return Fraction(value)


def solve_2x2(a1, b1, c1, a2, b2, c2):
    """Classify and solve a1*x+b1*y=c1, a2*x+b2*y=c2 exactly."""
    a1, b1, c1, a2, b2, c2 = map(
        _as_exact_fraction, (a1, b1, c1, a2, b2, c2)
    )

    # A zero coefficient row is either an identity or a contradiction.
    if a1 == 0 and b1 == 0:
        if c1 != 0:
            return {"kind": "none", "solution": None}
        if a2 == 0 and b2 == 0:
            if c2 == 0:
                return {"kind": "infinite", "solution": None}
            return {"kind": "none", "solution": None}
        return {"kind": "infinite", "solution": None}

    if a2 == 0 and b2 == 0:
        if c2 == 0:
            return {"kind": "infinite", "solution": None}
        return {"kind": "none", "solution": None}

    determinant = a1 * b2 - a2 * b1
    if determinant != 0:
        x = (c1 * b2 - c2 * b1) / determinant
        y = (a1 * c2 - a2 * c1) / determinant
        return {"kind": "unique", "solution": (x, y)}

    # With nonzero coefficient rows and determinant zero, the
    # coefficient rows are proportional. Their constants must scale
    # by the same factor for the equations to describe the same line.
    if a1 != 0:
        scale = a2 / a1
    else:
        scale = b2 / b1

    if a2 == scale * a1 and b2 == scale * b1 and c2 == scale * c1:
        return {"kind": "infinite", "solution": None}
    return {"kind": "none", "solution": None}


# Unique solution with integer coefficients.
result = solve_2x2(2, 1, 11, 1, -1, 1)
assert result == {
    "kind": "unique",
    "solution": (Fraction(4), Fraction(3)),
}

# Unique solution with an exact rational coefficient.
result_fraction = solve_2x2(Fraction(1, 2), 1, 4, 1, -2, -2)
assert result_fraction["solution"] == (Fraction(3), Fraction(5, 2))

# Dependent equations: infinitely many points on one line.
assert solve_2x2(2, 3, 6, 4, 6, 12)["kind"] == "infinite"

# Parallel distinct equations: no solution.
assert solve_2x2(2, -1, 1, 4, -2, 5)["kind"] == "none"

# Degenerate rows: 0=0 adds no restriction; 0=3 is impossible.
assert solve_2x2(0, 0, 0, 1, 2, 4)["kind"] == "infinite"
assert solve_2x2(0, 0, 3, 1, 2, 4)["kind"] == "none"

print("Exact 2x2 system examples passed.")
```

### 12.1 What the program does and does not establish

The program uses exact rational arithmetic to classify systems of two equations in two variables, including zero coefficient rows. The formulas and classification are justified by elimination and proportionality arguments in this chapter. Executing code checks selected implementations and examples; it is not a proof of the general theorem.

The function is intentionally limited to two equations and two variables. Systems with three or more variables require methods beyond this chapter's scope.

## 13. Common errors and how to avoid them

1. **Solving each equation separately and treating the answers as the system solution.** A solution must satisfy both equations simultaneously.
2. **Adding equations without aligning like terms.** Write both equations in the same variable order first.
3. **Multiplying an equation by zero during elimination.** This can destroy information and is not an equivalent transformation.
4. **Stopping at $0=0$ and calling it one solution.** It means a redundant equation remains; determine the complete line of solutions.
5. **Stopping at $0=k$ with $k\ne0$ and trying to solve for a variable.** It is a contradiction, so the system has no solution.
6. **Dividing by a coefficient without checking whether it is zero.** If it may be zero, split into cases or choose another equation/variable.
7. **Assuming every equation in the general form is a line.** The equation $0=0$ describes the whole plane, while $0=5$ describes the empty set.
8. **Relying on a hand-drawn graph for an exact answer.** Use algebra when exact coordinates matter.
9. **Ignoring domain restrictions in a word problem.** Counts may need to be nonnegative integers, even if the algebraic system is solved over the reals.
10. **Failing to check the ordered pair in the original system.** Verify both original equations, not only the reduced equation.
11. **Using determinant formulas when the determinant is zero.** The formulas require a nonzero denominator; classify the system instead.
12. **Rounding too early.** Keep exact fractions through the algebra and round only when the context requires an approximation.

## 14. Exercises

Unless otherwise stated, solve over the real numbers. Show enough work to justify the method and check each unique ordered pair in the original equations. For contextual questions, define variables and state relevant restrictions.

### A. Meaning and graphical interpretation

1. Determine whether $(2,3)$ is a solution of $x+2y=8$ and $3x-y=3$.
2. Explain why the solution set of a system is the intersection of the solution sets of its equations.
3. Describe the graphical meaning of a system with exactly one solution.
4. Describe the graphical meaning of a system with no solution when both equations represent nondegenerate lines.
5. Explain why a system whose equations represent the same line has infinitely many solutions.

### B. Substitution

6. Solve $y=2x-1$ and $x+y=8$ by substitution.
7. Solve $3x+y=10$ and $y=x+2$.
8. Solve $\frac12x+y=4$ and $x-2y=-2$.
9. Solve $2x-3y=1$ and $y=2x-5$.
10. Solve $x=4$ and $2x+y=9$. Explain why this substitution is valid without dividing by a variable expression.

### C. Elimination and classification

11. Solve $2x+y=9$ and $2x-y=3$ by elimination.
12. Solve $3x+2y=16$ and $5x-2y=8$.
13. Solve $2x+3y=13$ and $4x+y=11$.
14. Classify $3x-2y=7$ and $6x-4y=14$.
15. Classify $2x+y=5$ and $4x+2y=13$.
16. Classify $0x+0y=0$ and $x-y=4$.
17. Classify $0x+0y=2$ and $x-y=4$.
18. Classify $0x+0y=0$ and $0x+0y=0$.
19. Classify $0x+0y=0$ and $0x+0y=5$.
20. For the system $a_1x+b_1y=c_1$, $a_2x+b_2y=c_2$, explain what the condition $a_1b_2-a_2b_1\ne0$ guarantees.

### D. Applications and modeling

21. A school sells 32 tickets. Adult tickets cost 11 units and student tickets cost 7 units. Total revenue is 284 units. Find the number of each type.
22. Two numbers have sum 41 and difference 9. Find them.
23. Two cyclists have position models $d_A=18+12t$ and $d_B=6+16t$, with distance in kilometres and time in hours. Find when and where they meet, and state the assumptions needed.
24. A shop sells notebooks and pens. It sells 18 items in total and receives 54 currency units. Each notebook costs 4 units and each pen costs 2 units. Find the number of each item.
25. A mixture contains two solutions, one with 10% salt and one with 30% salt. How many litres of each are needed to make 20 litres of a 22% mixture? Assume additive volumes and no loss during mixing.
26. A student obtains a real solution $(x,y)$ to a ticket-count problem, but one coordinate is negative or non-integer. Explain why the algebra can be correct while the contextual answer is invalid, and describe what should be checked.

## 15. Selected answers and solution outlines

1. First equation: $2+2(3)=8$; second: $3(2)-3=3$. Yes, $(2,3)$ satisfies both.
2. Each equation permits a set of ordered pairs; a system requires membership in every such set, hence their intersection.
3. The lines intersect at exactly one point; its coordinates are the unique solution.
4. The lines are distinct and parallel, so they do not intersect.
5. Every point on the common line satisfies both equations.
6. Substitute: $x+(2x-1)=8$, so $x=3$ and $y=5$.
7. $3x+(x+2)=10$, so $x=2$, $y=4$.
8. $(x,y)=(3,5/2)$.
9. Substitute: $2x-3(2x-5)=1$, so $x=7/2$ and $y=2$.
10. $x=4$ gives $8+y=9$, hence $(4,1)$.
11. Add: $4x=12$, so $x=3$ and $y=3$.
12. $(x,y)=(3,7/2)$.
13. $(x,y)=(2,3)$.
14. Infinitely many solutions; the second equation is twice the first.
15. No solution; doubling the first equation gives $4x+2y=10$, which contradicts the second.
16. Infinitely many solutions: the first equation is always true, leaving the line $x-y=4$.
17. No solution: $0=2$ is false.
18. Every ordered pair in $\mathbb{R}^2$ is a solution.
19. No solution because the second equation is false.
20. The coefficient rows are not proportional; elimination leaves a nonzero coefficient for one variable, so there is exactly one solution.
21. 15 adult tickets and 17 student tickets.
22. The numbers are 25 and 16.
23. $18+12t=6+16t$ gives $t=3$ hours and $d=54$ km. Assume constant speeds and valid position models through that time.
24. Let $n$ be notebooks and $p$ be pens: $n+p=18$, $4n+2p=54$. The solution is $n=9$, $p=9$.
25. Let $x$ be litres of 10% solution and $y$ litres of 30% solution. Then $x+y=20$ and $0.10x+0.30y=0.22(20)=4.4$. Solving gives $x=8$, $y=12$ litres.
26. Recheck variable definitions, equation setup, units, total and price data, and any omitted constraints. Counts must be nonnegative integers; a real algebraic solution alone does not make an infeasible context valid.

## 16. Chapter summary

- A solution of a system satisfies every equation at the same time; the solution set is the intersection of the individual solution sets.
- Substitution replaces a variable by an equivalent expression obtained from another equation.
- Elimination combines equations using reversible operations to remove a variable.
- A system is consistent when it has at least one solution and inconsistent when it has none.
- A consistent independent two-line system has one solution; a consistent dependent system has infinitely many.
- Elimination leading to a false statement such as $0=5$ indicates no solution. An identity such as $0=0$ indicates a redundant equation, after degenerate zero rows have been considered.
- For a two-equation system, a nonzero coefficient determinant guarantees one unique solution. A zero determinant requires further consistency analysis.
- Equations with zero coefficients are not ordinary lines: $0=0$ imposes no restriction, while $0=k$ for $k\ne0$ is impossible.
- Contextual models require variable definitions, units, assumptions, constraints, and a check against the original situation.
- Exact rational arithmetic avoids premature rounding and helps preserve exact solutions.

## 17. References and connections

- Math-Atlas, [**Foundations 03 — Relations and Functions**](../Foundations/03_Relations_and_Functions.MD): solution sets, mappings, and the language of relations.
- Math-Atlas, [**Foundations 05 — Mathematical Proof Techniques**](../Foundations/05_Mathematical_Proof_Techniques.MD): justification of equivalence-preserving transformations.
- Math-Atlas, [**Foundations 07 — Mathematical Notation and Symbols**](../Foundations/07_Mathematical_Notation_and_Symbols.MD): notation used for systems and sets.
- Math-Atlas, [**Foundations 09 — Mathematical Modeling and Problem Solving**](../Foundations/09_Mathematical_Modeling_and_Problem_Solving.MD): translating contexts into mathematical models and checking assumptions.
- Math-Atlas, [**Algebra 03 — Linear Equations and Literal Equations**](03_Linear_Equations_and_Literal_Equations.MD): solving a single equation and preserving solution sets.
- Math-Atlas, [**Algebra 05 — Coordinate Graphs and Linear Models**](05_Coordinate_Graphs_and_Linear_Models.MD): slope, line equations, and graphical interpretation.

**Next chapter:** Chapter 07 — Exponents and Scientific Notation.
