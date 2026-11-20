# Algebra 19 — Nonlinear Systems and Inequalities

## 1. Introduction

A system is **nonlinear** when at least one equation is not linear in its variables. Its solution is an ordered pair (or, in higher dimensions, an ordered tuple) that satisfies every equation at the same time. In the plane, solutions are the intersection points of the curves represented by the equations.

Nonlinear systems can have no real solution, one real solution, or several real solutions. Unlike a pair of distinct lines, two nonlinear curves may meet more than once. Algebraic methods such as substitution and elimination reduce many introductory systems to polynomial equations in one variable. Graphs provide geometric insight, while exact substitution is needed to verify every candidate.

A **system of inequalities** describes a region rather than usually a finite list of points. Its solution set is the intersection of the regions satisfying all inequalities in the system. Boundary curves may or may not belong to the solution region, depending on whether the inequalities are strict.

This chapter builds on the linear-system methods in Chapter 06, the coordinate and graph language in Chapter 05, quadratic equations in Chapter 12, and polynomial operations in Chapters 08–09. It focuses on selected nonlinear systems and plane inequalities, not on a general-purpose solver for arbitrary algebraic curves.

### Learning objectives

After completing this chapter, you should be able to:

- Define the solution set of a nonlinear system as an intersection of equation-solution sets.
- Solve selected systems by substitution, elimination, factoring, and symmetry.
- Interpret solutions as intersection points and distinguish crossing, tangency, and no-real-intersection cases.
- Explain why squaring or another non-equivalent transformation can introduce candidates that must be checked.
- Represent linear and quadratic inequalities in two variables and interpret their boundary curves.
- Graph a system of inequalities as the intersection of its regions, using solid or dashed boundaries appropriately.
- Distinguish an intersection (logical AND) from a union (logical OR).
- Use exact rational calculations and point tests while recognizing the limits of a finite computational helper.

Unless a problem states otherwise, variables are real and points are in $\mathbb R^2$.

## 2. What is a nonlinear system?

A system of two equations in $x$ and $y$ may be written as

$$
\begin{cases}
F(x,y)=0,\\
G(x,y)=0.
\end{cases}
$$

An ordered pair $(u,v)$ is a solution exactly when both $F(u,v)=0$ and $G(u,v)=0$. Thus the solution set is

$$
S=\{(x,y)\in\mathbb R^2:F(x,y)=0\text{ and }G(x,y)=0\}.
$$

The word **and** matters: satisfying just one equation is not enough. The solution set is the intersection of the two individual curve sets.

A system is nonlinear if at least one equation is nonlinear. Examples include

$$
\begin{cases}
y=x^2,\\
y=2x+3,
\end{cases}
\qquad
\begin{cases}
x^2+y^2=25,\\
y=x+1,
\end{cases}
\qquad
\begin{cases}
x^2+y^2=25,\\
x^2-y^2=7.
\end{cases}
$$

The first system contains a parabola and a line; the second contains a circle and a line; the third contains two nonlinear curves. Their solutions are the points common to both curves.

### Example 1 — Check a point in a nonlinear system

Consider

$$
\begin{cases}
y=x^2,\\
y=2x+3.
\end{cases}
$$

The point $(3,9)$ satisfies the first equation because $9=3^2$, and it satisfies the second because $9=2(3)+3$. Therefore it is a solution. The point $(0,0)$ satisfies $y=x^2$ but not $y=2x+3$, so it is not a solution of the system.

## 3. Choosing an algebraic method

The best method depends on the form of the equations.

- **Substitution** is often convenient when one equation already gives $x$ or $y$ explicitly, such as $y=x^2$ or $x=y+2$.
- **Elimination** is useful when adding or subtracting equations removes a shared expression, such as $x^2$ or $y^2$.
- **Factoring** is useful after substitution or elimination produces a polynomial equation.
- **Symmetry** can help when equations involve $x+y$, $xy$, $x^2+y^2$, or expressions unchanged by swapping $x$ and $y$.
- **Graphing** helps estimate the number and location of intersections, but a sketch alone does not prove an exact solution.

A complete solution should identify all real candidates, form the corresponding ordered pairs, and check every pair in the original system.

## 4. Solving by substitution

Suppose one equation gives $y=f(x)$. Substitute that expression into the other equation. The resulting equation in $x$ may be quadratic or of a higher degree. After solving it, use $y=f(x)$ to recover the corresponding $y$-coordinates.

This procedure is valid because every solution of the original system must satisfy $y=f(x)$. Conversely, a value of $x$ found after substitution gives a solution only when the recovered pair also satisfies the original equations. If a step involves squaring, clearing a denominator, or dividing by an expression that might be zero, retain the original restrictions and check candidates directly.

### Example 2 — A line and a parabola

Solve

$$
\begin{cases}
y=x^2,\\
y=2x+3.
\end{cases}
$$

At an intersection, the two expressions for $y$ are equal:

$$
x^2=2x+3.
$$

Move all terms to one side and factor:

$$
x^2-2x-3=0,\qquad (x-3)(x+1)=0.
$$

Therefore $x=3$ or $x=-1$. Substituting into $y=2x+3$ gives $y=9$ or $y=1$. The two intersection points are

$$
\boxed{(3,9)\text{ and }(-1,1).}
$$

Both points satisfy both original equations. The system has two real solutions.

### Example 3 — A line and a circle

Solve

$$
\begin{cases}
x^2+y^2=25,\\
y=x+1.
\end{cases}
$$

Substitute $y=x+1$ into the circle equation:

$$
x^2+(x+1)^2=25.
$$

Expand and simplify:

$$
2x^2+2x-24=0
\quad\Longleftrightarrow\quad
(x+4)(x-3)=0.
$$

Thus $x=-4$ or $x=3$. The line equation gives $y=-3$ or $y=4$, respectively. The points are

$$
\boxed{(-4,-3)\text{ and }(3,4).}
$$

Check: $(-4)^2+(-3)^2=25$ and $3^2+4^2=25$; both points also satisfy $y=x+1$.

## 5. Tangency and the discriminant

When substitution produces a quadratic equation $Ax^2+Bx+C=0$ with $A\ne0$, its discriminant

$$
D=B^2-4AC
$$

classifies the real $x$-values:

- $D<0$: there are no real intersection points.
- $D=0$: there is one distinct real $x$-value; the line is tangent to the parabola or circle in the selected examples.
- $D>0$: there are two distinct real $x$-values.

For a line-circle or line-parabola system, each real $x$-value determines one point because the line gives a unique $y$. This classification is specific to the reduction to a quadratic; it is not a universal bound for arbitrary pairs of nonlinear curves.

### Example 4 — Tangent and non-intersecting lines

Consider the circle $x^2+y^2=25$.

For the horizontal line $y=5$, substitution gives $x^2+25=25$, hence $x=0$. The line is tangent to the circle at $(0,5)$.

For the horizontal line $y=6$, substitution gives $x^2+36=25$, or $x^2=-11$. There is no real solution, so the line does not meet the circle in the real plane.

## 6. Elimination in nonlinear systems

Elimination can also work when both equations are nonlinear. If the equations contain the same expression, adding or subtracting them may remove one or more terms. The operation must preserve equivalence: adding equations is useful for deriving a necessary equation, but any information lost during elimination must be recovered by substituting into an original equation.

### Example 5 — Eliminate two squared terms

Solve

$$
\begin{cases}
x^2+y^2=25,\\
x^2-y^2=7.
\end{cases}
$$

Add the equations:

$$
2x^2=32\quad\Longrightarrow\quad x^2=16.
$$

Subtract the second equation from the first:

$$
2y^2=18\quad\Longrightarrow\quad y^2=9.
$$

Therefore $x=\pm4$ and $y=\pm3$. Every independent sign choice satisfies both equations, giving four solutions:

$$
\boxed{(4,3),\ (4,-3),\ (-4,3),\ (-4,-3).}
$$

There are four points because the equations determine the squares of the coordinates but do not determine their signs.

### Example 6 — Use symmetry through the sum and product

Solve

$$
\begin{cases}
x+y=5,\\
x^2+y^2=13.
\end{cases}
$$

Square the first equation:

$$
x^2+2xy+y^2=25.
$$

Use $x^2+y^2=13$ to obtain $2xy=12$, so $xy=6$. The numbers $x$ and $y$ are therefore the roots of

$$
t^2-5t+6=0=(t-2)(t-3).
$$

Hence the ordered pairs are $(2,3)$ and $(3,2)$. Both satisfy the original system.

## 7. Checking candidates and avoiding extraneous solutions

A derived equation can have a solution set that is larger than the original system's solution set if a non-equivalent operation is used. Squaring is the most common example. If $A=B$, then $A^2=B^2$; however, $A^2=B^2$ only implies $A=B$ **or** $A=-B$.

Therefore, after squaring, multiplying by an expression that can be zero, or making another non-reversible transformation, substitute each candidate into the original equations. Also check all domain restrictions.

### Example 7 — Squaring creates an extra candidate

Consider the system

$$
\begin{cases}
y=x,\\
y=\sqrt{x+2}.
\end{cases}
$$

The square root requires $x+2\geq0$, and it is nonnegative, so a solution must have $x\geq0$. Substitution gives $x=\sqrt{x+2}$. Squaring yields

$$
x^2=x+2
\quad\Longrightarrow\quad
(x-2)(x+1)=0.
$$

The candidates are $x=2$ and $x=-1$. But $x=-1$ does not satisfy the original equation: $-1\ne\sqrt1=1$. The only solution is $(2,2)$.

This example shows why the original system, not just the transformed equation, determines the final answer.

## 8. Nonlinear inequalities in two variables

An inequality in $x$ and $y$ describes a region of the plane. For example,

$$
y\geq x^2
$$

describes all points on or above the parabola $y=x^2$. The inequality $y<x^2$ describes points strictly below the same parabola.

A quadratic inequality can also describe an interior or exterior region. For example,

$$
x^2+y^2\leq25
$$

describes the closed disk of radius $5$ centered at the origin, including its circular boundary. Replacing $\leq$ with $<$ excludes the boundary circle and gives the open disk.

For a general linear or quadratic expression $F(x,y)$, an inequality such as $F(x,y)\leq0$ selects the points where that expression is nonpositive. A boundary curve is obtained by replacing the inequality sign with equality, $F(x,y)=0$.

## 9. Boundary curves and test points

To sketch a single inequality:

1. Draw its boundary equation.
2. Use a **solid** boundary for $\leq$ or $\geq$, because equality is included.
3. Use a **dashed** boundary for $<$ or $>$, because equality is excluded.
4. Choose a test point not on the boundary, often $(0,0)$ when it is not on the curve.
5. Substitute the test point into the inequality. Shade the side or region that satisfies it.

For an inequality already written as $y\geq f(x)$, the solution is on or above the graph of $f$. For $y<f(x)$, it is below the graph and excludes the boundary. For an implicit inequality such as $x^2+y^2\leq25$, use a test point or the geometry of the expression to identify the correct region.

A test point identifies the correct side of a boundary only when the boundary separates the relevant plane into regions and the sign does not change within a connected region without crossing the boundary. For complicated curves with several components, test each relevant region rather than assuming one test point settles the entire picture.

## 10. Systems of inequalities: intersection of regions

A system of inequalities uses logical **and**: a point must satisfy every inequality. Its solution region is the intersection of the individual regions.

### Example 8 — A region between a parabola and a line

Find the solution set of

$$
\begin{cases}
y\geq x^2,\\
y<2x+3.
\end{cases}
$$

The first inequality requires $y$ to be on or above the parabola. The second requires $y$ to be strictly below the line. For such a $y$ to exist, the lower boundary must be strictly below the upper boundary:

$$
x^2<2x+3.
$$

Factor:

$$
(x+1)(x-3)<0,
$$

which holds when $-1<x<3$. Thus the region can be written exactly as

$$
\boxed{-1<x<3,\qquad x^2\leq y<2x+3.}
$$

The parabola boundary is included wherever it lies in the region; the line boundary is excluded. The endpoints $x=-1$ and $x=3$ are not included because the two boundaries meet there and the upper inequality is strict.

### Example 9 — A disk intersected with a half-plane

Consider

$$
\begin{cases}
x^2+y^2\leq25,\\
y\geq x.
\end{cases}
$$

The first inequality gives the closed disk of radius $5$. The second keeps the half-plane on or above the line $y=x$. The solution is the portion of the disk lying in that half-plane, including the relevant parts of both boundaries.

The point $(0,4)$ belongs to the region because $0^2+4^2=16\leq25$ and $4\geq0$. The point $(4,0)$ is inside the disk but fails $0\geq4$, so it is not in the system's solution set.

## 11. AND, OR, and boundary inclusion

The distinction between a system and a union is essential:

- **AND / intersection:** satisfy every inequality. The solution region is the overlap of the shaded regions.
- **OR / union:** satisfy at least one inequality. The solution region is the combined area covered by either region.

For example, $y\geq x^2$ **and** $y<2x+3$ gives the region between the parabola and line from Example 8. Replacing “and” with “or” gives a much larger union and is a different problem.

A point on a boundary is included only if the corresponding inequality is non-strict. When several boundaries meet, a point belongs to the final solution only if it passes every inequality in the system.

## 12. Applications and feasible regions

Systems of inequalities often describe constraints. Suppose $x$ and $y$ represent quantities that cannot be negative, and a production or resource model imposes a capacity constraint. The feasible set is the collection of points satisfying all nonnegativity and capacity inequalities simultaneously.

A feasible region is not itself an optimization result. To maximize or minimize a quantity, an objective function must also be specified. Chapter 20 develops algebraic modeling and optimization; here the goal is to construct and interpret the feasible region correctly.

### Example 10 — A simple feasible region

Suppose $x$ and $y$ are nonnegative and must satisfy

$$
\begin{cases}
x\geq0,\\
y\geq0,\\
x+y\leq8,\\
y\geq x^2/4.
\end{cases}
$$

The solution is the portion of the first quadrant lying below or on the line $x+y=8$ and above or on the parabola $y=x^2/4$. The first two inequalities restrict the context to nonnegative quantities. The remaining two constraints must hold at the same point; checking only one of them is insufficient.

## 13. Computational exploration with Python

The self-contained Python implementation in the example below provides deliberately limited exact helpers:

- Intersections of a nondegenerate parabola with a nonvertical line.
- Intersections of a circle $x^2+y^2=R^2$ with a nonvertical line.
- Exact classification as no real intersection, one rational intersection, two rational intersections, or two real irrational intersections.
- Exact point checks for systems of linear or quadratic inequalities in two variables.

The helpers accept integers and `Fraction` values. They do not use floating-point arithmetic for exact decisions. When an intersection exists but is irrational, the module reports the real intersection count and discriminant but does not fabricate rational coordinates. It does not solve arbitrary nonlinear systems, find arbitrary algebraic roots, or draw a graph.

### Example 11 — Exact line-parabola intersections

```python
from __future__ import annotations

# --- Inlined implementation: nonlinear_core ---
"""Exact helpers for selected nonlinear systems and plane inequalities.

Scope:
- Intersections of a nondegenerate real parabola with a line.
- Intersections of a circle x**2 + y**2 = radius_squared with a nonvertical line.
- Exact point checks for systems of linear/quadratic inequalities in two variables.

All coefficients and coordinates must be integers or fractions.Fraction values.
This module reports when intersections are real but irrational; it does not
attempt symbolic radical simplification or solve arbitrary nonlinear systems.
"""


from dataclasses import dataclass
from fractions import Fraction
from math import isqrt
from typing import Iterable, Sequence

Exact = int | Fraction
Point = tuple[Fraction, Fraction]


def _as_fraction(value: Exact, name: str) -> Fraction:
    if isinstance(value, bool) or isinstance(value, float):
        raise TypeError(f"{name} must be an int or Fraction, not bool/float")
    if isinstance(value, Fraction):
        return value
    if isinstance(value, int):
        return Fraction(value)
    raise TypeError(f"{name} must be an int or Fraction")


def _rational_sqrt(value: Fraction) -> Fraction | None:
    """Return the exact nonnegative rational square root, or None."""
    if value < 0:
        return None
    numerator_root = isqrt(value.numerator)
    denominator_root = isqrt(value.denominator)
    if numerator_root * numerator_root != value.numerator:
        return None
    if denominator_root * denominator_root != value.denominator:
        return None
    return Fraction(numerator_root, denominator_root)


@dataclass(frozen=True)
class IntersectionResult:
    """Classification and exact rational points for a line/conic pair.

    ``classification`` is one of:
    - ``no-real-intersection``
    - ``one-rational-intersection``
    - ``two-rational-intersections``
    - ``two-real-irrational-intersections``

    For the last case, ``real_intersection_count`` is 2 but ``points`` is empty
    because this exact-rational helper does not represent irrational roots.
    ``discriminant`` is the discriminant of the reduced quadratic in x.
    """
    classification: str
    real_intersection_count: int
    discriminant: Fraction
    points: tuple[Point, ...]


def _quadratic_intersections(
    a: Fraction,
    b: Fraction,
    c: Fraction,
    y_from_x,
) -> IntersectionResult:
    """Classify ax^2+bx+c=0 and return rational (x,y) points if possible."""
    if a == 0:
        raise ValueError("the reduced equation must remain quadratic")
    discriminant = b * b - 4 * a * c
    if discriminant < 0:
        return IntersectionResult("no-real-intersection", 0, discriminant, ())

    root = _rational_sqrt(discriminant)
    if root is None:
        return IntersectionResult("two-real-irrational-intersections", 2, discriminant, ())

    denominator = 2 * a
    x_values = {(-b - root) / denominator, (-b + root) / denominator}
    ordered_x = tuple(sorted(x_values))
    points = tuple((x, y_from_x(x)) for x in ordered_x)
    if discriminant == 0:
        return IntersectionResult("one-rational-intersection", 1, discriminant, points)
    return IntersectionResult("two-rational-intersections", 2, discriminant, points)


def intersect_line_parabola(
    a: Exact, b: Exact, c: Exact, slope: Exact, intercept: Exact
) -> IntersectionResult:
    """Intersect y=a*x^2+b*x+c (a != 0) with y=slope*x+intercept."""
    qa = _as_fraction(a, "a")
    qb = _as_fraction(b, "b")
    qc = _as_fraction(c, "c")
    m = _as_fraction(slope, "slope")
    d = _as_fraction(intercept, "intercept")
    if qa == 0:
        raise ValueError("a must be nonzero for a nondegenerate parabola")

    # a*x^2 + (b-m)*x + (c-d) = 0
    return _quadratic_intersections(qa, qb - m, qc - d, lambda x: m * x + d)


def intersect_line_circle(
    radius_squared: Exact, slope: Exact, intercept: Exact
) -> IntersectionResult:
    """Intersect x^2+y^2=radius_squared with y=slope*x+intercept.

    The circle is real only when radius_squared >= 0. The line is represented
    as a nonvertical line; vertical lines can be handled by direct substitution.
    """
    r2 = _as_fraction(radius_squared, "radius_squared")
    m = _as_fraction(slope, "slope")
    d = _as_fraction(intercept, "intercept")
    if r2 < 0:
        raise ValueError("radius_squared must be nonnegative")

    # (1+m^2)*x^2 + 2*m*d*x + (d^2-r^2) = 0
    qa = 1 + m * m
    qb = 2 * m * d
    qc = d * d - r2
    return _quadratic_intersections(qa, qb, qc, lambda x: m * x + d)


def _quadratic_form_value(point: Sequence[Exact], coefficients: Sequence[Exact]) -> Fraction:
    """Evaluate A*x^2+B*x*y+C*y^2+D*x+E*y+F exactly."""
    if isinstance(point, (str, bytes)) or len(point) != 2:
        raise ValueError("point must contain exactly two coordinates")
    if isinstance(coefficients, (str, bytes)) or len(coefficients) != 6:
        raise ValueError("coefficients must be (A, B, C, D, E, F)")
    x = _as_fraction(point[0], "x")
    y = _as_fraction(point[1], "y")
    A, B, C, D, E, F = (
        _as_fraction(value, f"coefficient[{index}]")
        for index, value in enumerate(coefficients)
    )
    return A * x * x + B * x * y + C * y * y + D * x + E * y + F


def _relation_holds(value: Fraction, relation: str) -> bool:
    if relation == "<":
        return value < 0
    if relation == "<=":
        return value <= 0
    if relation == ">":
        return value > 0
    if relation == ">=":
        return value >= 0
    raise ValueError("relation must be one of '<', '<=', '>', '>='")


def point_satisfies_inequality(
    point: Sequence[Exact], coefficients: Sequence[Exact], relation: str
) -> bool:
    """Check a quadratic inequality F(x,y) relation 0 exactly.

    Coefficients are ordered as (A, B, C, D, E, F) for
    A*x^2 + B*x*y + C*y^2 + D*x + E*y + F.
    Allowed relations: '<', '<=', '>', '>='.
    """
    value = _quadratic_form_value(point, coefficients)
    return _relation_holds(value, relation)


def point_satisfies_system(
    point: Sequence[Exact],
    inequalities: Iterable[tuple[Sequence[Exact], str]],
) -> bool:
    """Return True when a point satisfies every inequality (logical AND).

    The point and all constraints are validated before evaluating the system,
    so an invalid later constraint is not silently ignored by short-circuiting.
    An empty system is the whole plane, but the supplied point must still be
    a valid exact rational coordinate pair.
    """
    if isinstance(point, (str, bytes)) or len(point) != 2:
        raise ValueError("point must contain exactly two coordinates")
    _as_fraction(point[0], "x")
    _as_fraction(point[1], "y")

    prepared: list[tuple[Fraction, str]] = []
    for item in inequalities:
        if not isinstance(item, (tuple, list)) or len(item) != 2:
            raise ValueError("each inequality must be (six_coefficients, relation)")
        coefficients, relation = item
        value = _quadratic_form_value(point, coefficients)
        if relation not in ("<", "<=", ">", ">="):
            raise ValueError("relation must be one of '<', '<=', '>', '>='")
        prepared.append((value, relation))
    return all(_relation_holds(value, relation) for value, relation in prepared)

# --- Chapter example ---
intersect_line_parabola = intersect_line_parabola

# y = x^2 and y = 2x + 3
result = intersect_line_parabola(1, 0, 0, 2, 3)
assert result.classification == "two-rational-intersections"
assert result.points == ((-1, 1), (3, 9))

# y = x^2 and y = 2x - 1: one tangent point
tangent = intersect_line_parabola(1, 0, 0, 2, -1)
assert tangent.real_intersection_count == 1
```

### Example 12 — Check a point in an inequality region

```python
from __future__ import annotations

# --- Inlined implementation: nonlinear_core ---
"""Exact helpers for selected nonlinear systems and plane inequalities.

Scope:
- Intersections of a nondegenerate real parabola with a line.
- Intersections of a circle x**2 + y**2 = radius_squared with a nonvertical line.
- Exact point checks for systems of linear/quadratic inequalities in two variables.

All coefficients and coordinates must be integers or fractions.Fraction values.
This module reports when intersections are real but irrational; it does not
attempt symbolic radical simplification or solve arbitrary nonlinear systems.
"""


from dataclasses import dataclass
from fractions import Fraction
from math import isqrt
from typing import Iterable, Sequence

Exact = int | Fraction
Point = tuple[Fraction, Fraction]


def _as_fraction(value: Exact, name: str) -> Fraction:
    if isinstance(value, bool) or isinstance(value, float):
        raise TypeError(f"{name} must be an int or Fraction, not bool/float")
    if isinstance(value, Fraction):
        return value
    if isinstance(value, int):
        return Fraction(value)
    raise TypeError(f"{name} must be an int or Fraction")


def _rational_sqrt(value: Fraction) -> Fraction | None:
    """Return the exact nonnegative rational square root, or None."""
    if value < 0:
        return None
    numerator_root = isqrt(value.numerator)
    denominator_root = isqrt(value.denominator)
    if numerator_root * numerator_root != value.numerator:
        return None
    if denominator_root * denominator_root != value.denominator:
        return None
    return Fraction(numerator_root, denominator_root)


@dataclass(frozen=True)
class IntersectionResult:
    """Classification and exact rational points for a line/conic pair.

    ``classification`` is one of:
    - ``no-real-intersection``
    - ``one-rational-intersection``
    - ``two-rational-intersections``
    - ``two-real-irrational-intersections``

    For the last case, ``real_intersection_count`` is 2 but ``points`` is empty
    because this exact-rational helper does not represent irrational roots.
    ``discriminant`` is the discriminant of the reduced quadratic in x.
    """
    classification: str
    real_intersection_count: int
    discriminant: Fraction
    points: tuple[Point, ...]


def _quadratic_intersections(
    a: Fraction,
    b: Fraction,
    c: Fraction,
    y_from_x,
) -> IntersectionResult:
    """Classify ax^2+bx+c=0 and return rational (x,y) points if possible."""
    if a == 0:
        raise ValueError("the reduced equation must remain quadratic")
    discriminant = b * b - 4 * a * c
    if discriminant < 0:
        return IntersectionResult("no-real-intersection", 0, discriminant, ())

    root = _rational_sqrt(discriminant)
    if root is None:
        return IntersectionResult("two-real-irrational-intersections", 2, discriminant, ())

    denominator = 2 * a
    x_values = {(-b - root) / denominator, (-b + root) / denominator}
    ordered_x = tuple(sorted(x_values))
    points = tuple((x, y_from_x(x)) for x in ordered_x)
    if discriminant == 0:
        return IntersectionResult("one-rational-intersection", 1, discriminant, points)
    return IntersectionResult("two-rational-intersections", 2, discriminant, points)


def intersect_line_parabola(
    a: Exact, b: Exact, c: Exact, slope: Exact, intercept: Exact
) -> IntersectionResult:
    """Intersect y=a*x^2+b*x+c (a != 0) with y=slope*x+intercept."""
    qa = _as_fraction(a, "a")
    qb = _as_fraction(b, "b")
    qc = _as_fraction(c, "c")
    m = _as_fraction(slope, "slope")
    d = _as_fraction(intercept, "intercept")
    if qa == 0:
        raise ValueError("a must be nonzero for a nondegenerate parabola")

    # a*x^2 + (b-m)*x + (c-d) = 0
    return _quadratic_intersections(qa, qb - m, qc - d, lambda x: m * x + d)


def intersect_line_circle(
    radius_squared: Exact, slope: Exact, intercept: Exact
) -> IntersectionResult:
    """Intersect x^2+y^2=radius_squared with y=slope*x+intercept.

    The circle is real only when radius_squared >= 0. The line is represented
    as a nonvertical line; vertical lines can be handled by direct substitution.
    """
    r2 = _as_fraction(radius_squared, "radius_squared")
    m = _as_fraction(slope, "slope")
    d = _as_fraction(intercept, "intercept")
    if r2 < 0:
        raise ValueError("radius_squared must be nonnegative")

    # (1+m^2)*x^2 + 2*m*d*x + (d^2-r^2) = 0
    qa = 1 + m * m
    qb = 2 * m * d
    qc = d * d - r2
    return _quadratic_intersections(qa, qb, qc, lambda x: m * x + d)


def _quadratic_form_value(point: Sequence[Exact], coefficients: Sequence[Exact]) -> Fraction:
    """Evaluate A*x^2+B*x*y+C*y^2+D*x+E*y+F exactly."""
    if isinstance(point, (str, bytes)) or len(point) != 2:
        raise ValueError("point must contain exactly two coordinates")
    if isinstance(coefficients, (str, bytes)) or len(coefficients) != 6:
        raise ValueError("coefficients must be (A, B, C, D, E, F)")
    x = _as_fraction(point[0], "x")
    y = _as_fraction(point[1], "y")
    A, B, C, D, E, F = (
        _as_fraction(value, f"coefficient[{index}]")
        for index, value in enumerate(coefficients)
    )
    return A * x * x + B * x * y + C * y * y + D * x + E * y + F


def _relation_holds(value: Fraction, relation: str) -> bool:
    if relation == "<":
        return value < 0
    if relation == "<=":
        return value <= 0
    if relation == ">":
        return value > 0
    if relation == ">=":
        return value >= 0
    raise ValueError("relation must be one of '<', '<=', '>', '>='")


def point_satisfies_inequality(
    point: Sequence[Exact], coefficients: Sequence[Exact], relation: str
) -> bool:
    """Check a quadratic inequality F(x,y) relation 0 exactly.

    Coefficients are ordered as (A, B, C, D, E, F) for
    A*x^2 + B*x*y + C*y^2 + D*x + E*y + F.
    Allowed relations: '<', '<=', '>', '>='.
    """
    value = _quadratic_form_value(point, coefficients)
    return _relation_holds(value, relation)


def point_satisfies_system(
    point: Sequence[Exact],
    inequalities: Iterable[tuple[Sequence[Exact], str]],
) -> bool:
    """Return True when a point satisfies every inequality (logical AND).

    The point and all constraints are validated before evaluating the system,
    so an invalid later constraint is not silently ignored by short-circuiting.
    An empty system is the whole plane, but the supplied point must still be
    a valid exact rational coordinate pair.
    """
    if isinstance(point, (str, bytes)) or len(point) != 2:
        raise ValueError("point must contain exactly two coordinates")
    _as_fraction(point[0], "x")
    _as_fraction(point[1], "y")

    prepared: list[tuple[Fraction, str]] = []
    for item in inequalities:
        if not isinstance(item, (tuple, list)) or len(item) != 2:
            raise ValueError("each inequality must be (six_coefficients, relation)")
        coefficients, relation = item
        value = _quadratic_form_value(point, coefficients)
        if relation not in ("<", "<=", ">", ">="):
            raise ValueError("relation must be one of '<', '<=', '>', '>='")
        prepared.append((value, relation))
    return all(_relation_holds(value, relation) for value, relation in prepared)

# --- Chapter example ---
point_satisfies_system = point_satisfies_system

# F(x,y) = A*x^2 + B*x*y + C*y^2 + D*x + E*y + F
# y >= x^2  <=>  -x^2 + y >= 0
above_parabola = ((-1, 0, 0, 0, 1, 0), ">=")
# y < 2x + 3  <=>  y - 2x - 3 < 0
below_line = ((0, 0, 0, -2, 1, -3), "<")

region = (above_parabola, below_line)
assert point_satisfies_system((0, 1), region)
assert not point_satisfies_system((0, 3), region)
```

The code tests individual points exactly. It does not replace the algebraic derivation or prove that a plotted region has been shaded correctly.

## 14. Common errors and cautions

- A point that satisfies only one equation is not a solution of a system.
- A system of nonlinear equations may have several real solutions; do not stop after finding the first one.
- Adding or subtracting equations can help eliminate terms, but substitute back to recover and verify all coordinates.
- Squaring an equation can introduce extraneous candidates. Check candidates in the original system.
- A tangent intersection is one distinct point, even though the reduced quadratic has a repeated root.
- A negative discriminant means no real intersection for the corresponding quadratic reduction; it does not mean there are no complex algebraic roots.
- In a system of inequalities, all conditions must hold simultaneously. Shading the union instead of the intersection changes the problem.
- A dashed boundary is excluded; a solid boundary is included. At an intersection of several boundaries, apply each inequality separately.
- A feasible region does not identify a maximum or minimum until an objective function is provided.
- Exact algebraic results should not be replaced by rounded graph estimates unless approximation is explicitly requested.

## 15. Exercises

### A. Nonlinear systems

1. Solve the system $y=x^2$ and $y=3x-2$.
2. Solve the system $y=x^2-4$ and $y=2x-1$.
3. Find the intersection points of $x^2+y^2=25$ and $y=x+1$.
4. Solve $x^2+y^2=13$ and $x+y=5$.
5. Solve $x^2+y^2=25$ and $x^2-y^2=7$.
6. Determine whether the line $y=5$ is tangent to, secant to, or disjoint from the circle $x^2+y^2=25$. Then answer the same question for $y=6$.
7. Solve $y=x^2$ and $y=4$ over the real numbers.
8. Solve the system $y=x^2$ and $y=-x^2+8$.
9. Solve $x^2+y^2=10$ and $x+y=4$.
10. Explain why the system $y=x^2$ and $y=x^2+1$ has no solution.
11. A point is on both $y=x^2-1$ and $y=2x+2$. Find all such points and verify them in both equations.
12. Solve $x^2+y^2=50$ and $x+y=0$.

### B. Systems of inequalities

13. Describe and sketch the region $y\geq x^2$.
14. Describe and sketch the region $x^2+y^2<16$.
15. Find the solution region of $y\geq x^2$ and $y\leq1$.
16. Find the solution region of $y\geq x^2$ and $y<2x+3$.
17. Describe the region satisfying $x^2+y^2\leq25$ and $y\geq x$.
18. Determine whether each point belongs to the system $y\geq x^2$ and $y<2x+3$: (a) $(0,1)$, (b) $(0,3)$, (c) $(2,4)$, and (d) $(-1,1)$.
19. Describe the feasible region $x\geq0$, $y\geq0$, and $x+y\leq6$.
20. Explain the difference between the solution of $y\geq x^2$ **and** $y<3$ and the solution of $y\geq x^2$ **or** $y<3$.
21. A point must satisfy $x^2+y^2\leq9$, $x\geq0$, and $y\geq0$. Describe the region and test whether $(2,2)$ and $(3,1)$ belong to it.
22. Find all real $x$ for which there is at least one $y$ satisfying $x^2\leq y\leq4$.
23. A system is given by $y\leq x^2$ and $y>2x-3$. Find the interval of $x$-values for which the vertical slice of the region is nonempty.
24. Write a system of inequalities describing the region inside the circle $x^2+y^2=16$ and strictly above the $x$-axis.

### C. Reasoning and computation

25. For the system $y=x^2$ and $y=2x+2$, use the discriminant to determine the number of real intersection points before finding them.
26. The module reports two real irrational intersections for a line-parabola pair but returns no rational points. Explain why this is not a contradiction.
27. Use the self-contained Python implementation in this chapter to verify that $(2,4)$ lies in the region $y\geq x^2$ and $y<2x+3$.
28. Construct a system consisting of a circle and a horizontal line that has exactly one real intersection. State the intersection point and justify tangency.

## 16. Selected answers

1. $x^2-3x+2=0$, so $x=1,2$; the points are $(1,1)$ and $(2,4)$.
2. $x^2-2x-3=0$, so $x=-1,3$; the points are $(-1,-3)$ and $(3,5)$.
3. The points are $(-4,-3)$ and $(3,4)$.
4. The points are $(2,3)$ and $(3,2)$.
5. $x^2=16$ and $y^2=9$; all four independent sign choices are solutions.
6. $y=5$ is tangent at $(0,5)$; $y=6$ is disjoint from the circle in the real plane.
7. $x=\pm2$; the points are $(-2,4)$ and $(2,4)$.
8. $2x^2=8$, so $x=\pm2$ and $y=4$; the points are $(-2,4)$ and $(2,4)$.
9. From $(x+y)^2=16=10+2xy$, obtain $xy=3$; then $t^2-4t+3=0$, giving $(1,3)$ and $(3,1)$.
10. The equations require the same $y$ to equal two expressions that differ by $1$, which is impossible.
11. $x^2-1=2x+2$ gives $(x-3)(x+1)=0$. The points are $(-1,0)$ and $(3,8)$.
12. Since $y=-x$, $2x^2=50$; the points are $(5,-5)$ and $(-5,5)$.
13. The closed region on or above the parabola; the boundary is solid.
14. The open disk centered at the origin with radius $4$; the circle is excluded.
15. $-1\leq x\leq1$ and $x^2\leq y\leq1$.
16. $-1<x<3$ and $x^2\leq y<2x+3$.
17. The part of the closed disk of radius $5$ on or above $y=x$.
18. (a) yes; (b) no; (c) yes; (d) no.
19. The closed triangle in the first quadrant bounded by $x=0$, $y=0$, and $x+y=6$.
20. AND gives the overlap; OR gives the union. These regions are not the same.
21. The closed quarter-disk in the first quadrant; $(2,2)$ belongs because $8\leq9$, while $(3,1)$ does not because $10>9$.
22. $x^2\leq4$, so $-2\leq x\leq2$.
23. Require $2x-3<x^2$, or $x^2-2x+3>0$. Since its discriminant is negative and its leading coefficient is positive, this holds for every real $x$; each vertical slice has at least one admissible $y$.
24. $x^2+y^2\leq16$ and $y>0$.
25. $x^2-2x-2=0$ has discriminant $12>0$, so there are two distinct real intersections.
26. The two real $x$-coordinates are irrational, so a helper restricted to exact rational coordinates can correctly report two real intersections while listing no rational points.
27. The function returns `True`: both inequalities hold with equality in the lower boundary and strict inequality at the upper boundary.
28. For example, $x^2+y^2=9$ and $y=3$ meet only at $(0,3)$; substitution gives $x^2=0$.

## 17. Chapter summary

- A solution of a nonlinear system is a point satisfying every equation; geometrically it is an intersection of the corresponding curves.
- Substitution reduces a system to one-variable equations when one variable can be expressed conveniently.
- Elimination can remove shared nonlinear terms, but original equations must be used to recover and verify all coordinates.
- A quadratic discriminant classifies the real intersections when the system reduces to a quadratic in one variable.
- Squaring and other non-equivalent transformations can introduce extraneous candidates; check every candidate in the original system.
- A two-variable inequality describes a plane region bounded by a line or curve.
- A system of inequalities describes the intersection of all individual regions (logical AND); OR describes a union.
- Solid boundaries are included and dashed boundaries are excluded.
- The companion code performs exact rational checks for selected line-conic intersections and point membership; it is not a general symbolic solver or graphing engine.
## References

- OpenStax, *Algebra and Trigonometry*, sections on systems of nonlinear equations and systems of inequalities.
- OpenStax, *Precalculus 2e*, sections on nonlinear systems and inequalities in two variables.
- The earlier chapters of this Math-Atlas Algebra volume: Chapters 05, 06, 12, 14, and 18.

**Next chapter:** Chapter 20 — Algebraic Modeling and Optimization.
