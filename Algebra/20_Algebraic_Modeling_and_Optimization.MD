# Algebra 20 — Algebraic Modeling and Optimization

## 1. Introduction

Algebra becomes especially useful when it turns a situation into a mathematical model that can be analyzed. A model is not merely a formula: it specifies quantities, assumptions, relationships, units, and admissible values. Optimization adds a question: among all values allowed by the model, which one makes a chosen quantity as large or as small as possible?

This final chapter brings together ideas from linear models (Chapter 05), quadratic models (Chapter 12), rational and polynomial functions (Chapters 14–15), exponential and logarithmic models (Chapters 16–17), and systems of inequalities (Chapter 19). It does not introduce calculus-based optimization or general linear programming. The methods here are algebraic: construct equations and inequalities, identify a feasible set, analyze a linear or quadratic objective, compare endpoints and vertices, and interpret the result in context.

Unless a problem states otherwise, variables are real. Contextual variables may have additional restrictions, such as nonnegativity or integer values. Parameters are fixed quantities for a given model, even when their numerical values are left symbolic.

### Learning objectives

After completing this chapter, you should be able to:

- Distinguish variables, parameters, decision variables, constraints, feasible sets, and objective functions.
- Translate a verbal or tabular context into a linear or quadratic model and state its assumptions.
- Keep units consistent and distinguish a model's algebraic domain from its contextual feasible domain.
- Construct cost, revenue, and profit models and interpret a break-even quantity.
- Express a constrained geometric or business problem using an objective function and constraints.
- Find maxima and minima of affine or quadratic functions on finite closed intervals by checking endpoints and any interior vertex.
- Distinguish continuous decisions from integer decisions and optimize a quadratic over a finite integer range.
- Analyze exact finite changes in linear and quadratic models without using calculus.
- Perform sensitivity checks and explain why a mathematically optimal result may be impractical or outside the model's assumptions.
- Use exact rational computation where possible and distinguish computational checks from proofs.

## 2. The structure of an algebraic model

A useful algebraic model has five parts.

1. **Variables:** quantities that may change, such as the number of items produced or time elapsed.
2. **Parameters:** fixed values within the problem, such as a price, fixed fee, or available amount of material.
3. **Relationships:** equations or functions connecting the quantities.
4. **Constraints:** equations, inequalities, interval restrictions, or integer conditions that define what is allowed.
5. **Objective:** the quantity to maximize or minimize, such as area, cost, revenue, time, or profit.

The **feasible set** is the set of all variable values satisfying every constraint. An **objective function** assigns a value to each feasible choice. A maximum or minimum is meaningful only after both the feasible set and objective have been specified.

### 2.1 A modeling workflow

A disciplined workflow is:

1. Read the context and identify the quantity being asked for.
2. Define variables, parameters, units, and the time or counting convention.
3. Translate relationships into equations or functions.
4. Translate restrictions into constraints, including nonnegativity, interval bounds, and integer requirements.
5. Identify the feasible set and write the objective function.
6. Choose an algebraic method appropriate to the model.
7. Check candidate solutions against the original relationships and every constraint.
8. State the result with units and explain what it means in context.
9. Test whether the result is reasonable and state limitations of the model.

The order matters. Solving an equation before identifying its domain can produce values that are mathematically valid for the equation but impossible in the original situation.

## 3. Variables, parameters, units, and constraints

Consider a delivery service that charges a fixed booking fee of 6 currency units and 1.5 units per kilometer. Let $d$ denote distance in kilometers and $C$ denote total cost in currency units. The model is

$$
C(d)=6+1.5d,\qquad d\geq0.
$$

Here $d$ is the input variable, the fixed fee 6 and rate 1.5 are parameters, and $C$ is the modeled output. The coefficient 1.5 has units of currency units per kilometer, so multiplying it by a distance produces a cost. The restriction $d\geq0$ is contextual; the affine formula itself can be evaluated at negative real inputs, but those inputs do not describe a physical distance.

A model should not mix units. For example, a rate in currency units per hour must be multiplied by time measured in hours, not minutes, unless a conversion is made first.

### Example 1 — Evaluate a linear cost model

For $C(d)=6+1.5d$, find the modeled cost for a 12-kilometer delivery.

$$
C(12)=6+1.5(12)=24.
$$

The modeled cost is 24 currency units. This conclusion assumes that the fixed fee and per-kilometer rate do not change with distance and that no taxes, waiting charges, or surcharges apply.

### Example 2 — Translate a verbal rule

A workshop charges a setup fee of 40 units and 7 units for each item made. If $q$ is the number of items and $C$ is total cost, then

$$
C(q)=40+7q,\qquad q\in\mathbb Z_{\geq0}.
$$

The integer condition matters because a count of finished items cannot be fractional. The formula is an affine model: 40 is the fixed component and 7 is the marginal cost per item.

## 4. Linear models and rates of change

An affine model has the form

$$
f(x)=mx+b,
$$
where $m$ is the constant rate of change and $b=f(0)$ is the initial value when zero is an admissible input. For two distinct data points $(x_1,y_1)$ and $(x_2,y_2)$, the line through them has slope

$$
m=\frac{y_2-y_1}{x_2-x_1},\qquad x_1\ne x_2.
$$

The slope is a rate with units “output units per input unit.” It is not automatically a causal effect. A linear model is suitable when a constant change per unit is reasonable over the stated range. Chapter 05 develops line graphs and residuals; here the focus is how the model supports decisions.

For an affine model, a change in input by $\Delta x$ changes the output by exactly

$$
\Delta f=m\,\Delta x.
$$

This relation is exact, not an approximation.

### Example 3 — Compare two plans

Plan A costs 18 currency units plus 2.5 units per use, while Plan B costs 33 currency units plus 1.25 units per use. If $n$ is the number of uses, then

$$
A(n)=18+2.5n,\qquad B(n)=33+1.25n.
$$

The break-even point between the plans satisfies

$$
18+2.5n=33+1.25n.
$$

Thus $1.25n=15$ and $n=12$. At 12 uses both plans cost 48 units. For fewer than 12 uses Plan A costs less; for more than 12 uses Plan B costs less. This comparison assumes both plans provide the same service and have no other fees or usage limits.

## 5. Cost, revenue, profit, and break-even analysis

A simple production model often separates three quantities:

- Fixed cost $F$, which does not depend on the production quantity.
- Variable cost per unit $v$.
- Selling price per unit $p$.

For quantity $q\geq0$, define

$$
C(q)=F+vq,\qquad R(q)=pq.
$$

The profit function is revenue minus cost:

$$
P(q)=R(q)-C(q)=(p-v)q-F.
$$

The break-even quantity solves $P(q)=0$. If $p\ne v$, the algebraic break-even value is

$$
q_{\mathrm{BE}}=\frac{F}{p-v}.
$$

For a usual production model with $F\geq0$, $p\geq0$, and $v\geq0$, a nonnegative break-even quantity exists only when $p>v$, except for the special case $F=0$ where $q=0$ is already break-even. If $p=v$ and $F>0$, profit is always negative; if $p=v$ and $F=0$, every quantity breaks even. If quantities must be whole units, a fractional break-even value describes the continuous model's crossing but is not itself an attainable production count.

### Example 4 — A break-even model

Suppose fixed cost is 240 units, variable cost is 6 units per item, and price is 14 units per item. Then

$$
C(q)=240+6q,\quad R(q)=14q,
$$
so

$$
P(q)=8q-240.
$$

Break-even occurs when $8q-240=0$, so $q=30$. At 30 items, revenue and cost are both 420 units. Producing 31 items gives a modeled profit of 8 units, provided the per-unit assumptions remain valid.

### 5.1 Interpreting a break-even equation

A break-even equation is not an optimization problem: it finds where profit is zero. The best production quantity requires a separate objective and additional information, such as capacity limits, demand, or a nonlinear revenue model. Do not claim that break-even is the maximum-profit quantity unless the model proves that it is.

## 6. Quadratic models from geometry

Quadratic functions often appear when two dimensions depend linearly on one variable and are multiplied to form an area or product. The algebraic expression alone does not specify the physical problem; the dimensions and their feasible range must also be stated.

### Example 5 — A rectangle with fixed perimeter

A rectangle has perimeter 40 meters. Let one side be $x$ meters and the adjacent side be $y$ meters. The perimeter constraint gives

$$
2x+2y=40\quad\Longrightarrow\quad y=20-x.
$$

The area objective is

$$
A(x)=xy=x(20-x)= -x^2+20x.
$$

For a nondegenerate rectangle, both side lengths must be positive, so $0<x<20$. The vertex occurs at $x=10$ and gives $A(10)=100$. Since the parabola opens downward, the maximum area is 100 square meters, attained by a 10-meter by 10-meter square. The open endpoints correspond to degenerate rectangles with zero area and are not feasible rectangles.

### Example 6 — Three fenced sides beside a wall

A rectangular enclosure uses 72 meters of fencing on three sides; the fourth side lies along a straight wall and needs no fence. Let $x$ be the width perpendicular to the wall and $L$ the length parallel to it. The constraint is

$$
2x+L=72,\qquad L=72-2x.
$$

The area is

$$
A(x)=x(72-2x)=-2x^2+72x.
$$

The dimensions must satisfy $0<x<36$. The vertex is at $x=-72/(2(-2))=18$, and $L=36$. The maximum area is

$$
A(18)=648\text{ square meters}.
$$

This result assumes the wall is straight, the enclosure is rectangular, and fencing length is measured without gates, thickness, or waste.

## 7. Objective functions and feasible sets

A **constraint** restricts which inputs are allowed. For a one-variable model, several constraints may define an interval or a finite collection of intervals. For two variables, a system of inequalities defines a region in the plane; Chapter 19 explains how to describe and graph such regions.

The **objective function** is the quantity being optimized. The same feasible set can produce different optima for different objectives. For example, a production region may be unchanged while the objective switches from maximizing revenue to minimizing cost.

A model can have:

- A maximum or minimum that is attained.
- A supremum or infimum that is approached but not attained.
- No finite maximum or minimum because the objective is unbounded on the feasible set.
- Every feasible point optimal when the objective is constant.

The distinction between closed and open boundaries matters. On the interval $(0,1)$, the function $f(x)=x$ has no maximum: values approach 1 but never equal it. Its supremum is 1. On $[0,1]$, the maximum is 1 and is attained at $x=1$.

### Example 7 — Intersect several interval constraints

Suppose a machine setting $x$ must satisfy

$$
0\leq x\leq 12,\qquad 3\leq x\leq 10,\qquad x\leq8.
$$

The feasible set is their intersection, $[3,8]$. A proposed optimum outside this interval is inadmissible even if it optimizes the unconstrained formula.

## 8. Optimizing a quadratic on a finite closed interval

Let

$$
f(x)=ax^2+bx+c,\qquad a\ne0,
$$
on the closed interval $[L,U]$ with $L\leq U$. Completing the square gives

$$
f(x)=a(x-h)^2+k,
\qquad h=-\frac{b}{2a}.
$$

If $h$ lies in the interval, it is the vertex and gives the unrestricted minimum when $a>0$ or maximum when $a<0$. The opposite extreme on the interval must occur at an endpoint. If the vertex lies outside the interval, the quadratic is monotone over the interval, so both extrema occur at endpoints. Therefore it is sufficient to compare

- $f(L)$,
- $f(U)$,
- $f(h)$ when $L\leq h\leq U$.

This endpoint-and-vertex rule is valid for a continuous quadratic on a finite closed interval. It is not a rule for arbitrary functions, open intervals, or unbounded domains.

### Theorem — Endpoint-and-vertex test

A continuous quadratic function on a finite closed interval attains both a maximum and a minimum. Every maximizing or minimizing input is among the interval endpoints and, if it lies in the interval, the vertex.

**Reason.** A continuous function on a finite closed interval attains its extrema. For a quadratic, vertex form shows that the function is monotone on each side of the vertex: for $a>0$, it decreases toward the vertex and increases after it; for $a<0$, the directions reverse. If the vertex is inside the interval, it gives one extremum and the other must be at an endpoint. If it is outside, the function is monotone throughout the interval and both extrema are at endpoints. A constant function is the special case in which every point is optimal.

### Example 8 — A quadratic with an interior maximum

Maximize

$$
f(x)=-3x^2+12x+5
$$
on $[0,5]$. The vertex input is

$$
h=-\frac{12}{2(-3)}=2.
$$
Since $2\in[0,5]$ and the leading coefficient is negative, the maximum is at the vertex:

$$
f(2)=-12+24+5=17.
$$
The endpoints give $f(0)=5$ and $f(5)=-10$, confirming the maximum 17. The minimum on this interval is $-10$ at $x=5$.

### Example 9 — The vertex is outside the feasible interval

Maximize $g(x)=-(x-7)^2+10$ on $[0,5]$. The vertex input 7 is outside the feasible set. Since the parabola is increasing for $x<7$, the maximum on the interval is at $x=5$:

$$
g(5)=-( -2)^2+10=6.
$$
The minimum is at the other endpoint, $g(0)=-49+10=-39$. The unconstrained maximum 10 is not attainable because its input is infeasible.

## 9. Integer decision variables

Some decisions cannot be fractional. Numbers of products, vehicles, workers, or machines are typically integers. A continuous optimum can guide the search, but it may not be an admissible decision.

For a quadratic on a finite integer interval, check the integer endpoints and the integer(s) nearest the vertex. More precisely, if the vertex input is $h$, the floor and ceiling of $h$ are sufficient candidates when they lie in the allowed integer interval, along with both endpoints. The objective values must still be evaluated and compared exactly.

### Example 10 — Maximum profit with whole-unit production

Suppose a simplified profit model is

$$
P(q)=-2q^2+19q-20,
$$
where $q$ must be an integer with $0\leq q\leq10$. The continuous vertex occurs at

$$
q=-\frac{19}{2(-2)}=\frac{19}{4}=4.75.
$$
The relevant integer candidates are $q=4$ and $q=5$, together with the interval endpoints. Their profits are

$$
P(4)=24,\qquad P(5)=25.
$$
The endpoint values are $P(0)=-20$ and $P(10)=-30$. Thus the maximum feasible integer profit is 25, attained at $q=5$. This example assumes the stated quadratic is valid across the entire integer range.

## 10. Constraints from multiple requirements

When multiple conditions restrict the same variable, all must hold simultaneously. For interval constraints, this means taking their intersection. For more complicated inequalities, first solve each condition and then intersect the resulting sets. Chapter 19 develops two-variable feasible regions; an objective function must still be added before optimization can be performed.

### Example 11 — A feasible interval from practical constraints

A supplier requires an order of at least 20 units, storage capacity is at most 75 units, and a second condition restricts the quantity to at most 60 units. The integer feasible set is

$$
q\in\mathbb Z,\qquad 20\leq q\leq60.
$$
The storage upper bound 75 is redundant because the stricter upper bound 60 already applies. A redundant constraint can be retained for traceability, but it does not change the feasible set.

### Example 12 — Distinguish a feasible point from an optimum

Suppose a feasible region is $0\leq x\leq4$ and $0\leq y\leq3$. The point $(2,2)$ is feasible. It is not automatically an optimum. To decide whether it maximizes or minimizes anything, an objective such as $F(x,y)=3x+2y$ must be specified, and the objective must be compared over the entire feasible region.

## 11. Sensitivity analysis using finite changes

**Sensitivity analysis** asks how a model's output changes when an input or parameter changes. It is important to distinguish a change caused by the decision variable from a change caused by a parameter. The calculations in this section use exact finite differences and do not require calculus.

For an affine model $f(x)=mx+b$,

$$
f(x+\Delta x)-f(x)=m\Delta x.
$$

For a quadratic model $f(x)=ax^2+bx+c$,

$$
\begin{aligned}
f(x+\Delta x)-f(x)
&=a(x+\Delta x)^2+b(x+\Delta x)+c-(ax^2+bx+c)\\
&=(2ax+b)\Delta x+a(\Delta x)^2.
\end{aligned}
$$

The formula is exact for every real $x$ and $\Delta x$. The coefficient $2ax+b$ is the linear part of the change, while $a(\Delta x)^2$ is the additional quadratic contribution. This is not a derivative-based approximation.

### Example 13 — Exact sensitivity of a quadratic model

Let $f(x)=2x^2+3x+5$. At $x=4$, increase the input by $\Delta x=0.1=1/10$. Then

$$
\begin{aligned}
\Delta f&=(2(2)(4)+3)\left(\frac1{10}\right)
+2\left(\frac1{10}\right)^2\\
&=\frac{19}{10}+\frac1{50}=\frac{48}{25}=1.92.
\end{aligned}
$$

Indeed, $f(4)=49$ and $f(4.1)=50.92$, so the exact difference is 1.92.

### 11.1 Parameter sensitivity

If a model is $C(q)=F+vq$, changing the fixed-cost parameter by $\Delta F$ changes cost by exactly $\Delta F$ at every quantity. Changing the variable-cost parameter by $\Delta v$ changes cost by $q\Delta v$. The effect of a parameter can depend on the current decision value; therefore a sensitivity statement should name which parameter changes and which other quantities remain fixed.

## 12. Model validation and limitations

An algebraic model is a simplified representation of a situation. Before accepting a result, ask:

- **Units:** Do all terms in an equation have compatible units?
- **Domain:** Are negative, fractional, or very large input values meaningful?
- **Feasibility:** Does the proposed solution satisfy every constraint?
- **Assumptions:** Are fixed rates, constant prices, or constant growth factors realistic over the modeled range?
- **Rounding:** Does rounding change feasibility or the selected integer decision?
- **Data quality:** Were the parameters measured accurately, and are observations representative?
- **Validation:** Does the model agree with independent observations or known boundary cases?
- **Extrapolation:** Is the model being used far outside the data range on which it was based?

Model limitations must be stated: a model can be algebraically correct and still be a poor description of reality. For example, a linear cost model may be reasonable for a limited production range but fail when overtime, volume discounts, or capacity limits appear. A quadratic area model may assume exact dimensions and ignore material thickness. State limitations rather than hiding them.

## 13. Python: exact modeling and bounded optimization

The self-contained Python implementation in the example below uses integers and `Fraction` values for exact arithmetic. It deliberately rejects floating-point inputs in its exact routines. Use `Fraction("0.1")` rather than `0.1` when an exact one-tenth is intended.

### Example 14 — Evaluate an affine model and a profit model

```python
from __future__ import annotations

# --- Inlined implementation: modeling_core ---
"""Exact helpers for elementary algebraic modeling and bounded optimization.

The module intentionally supports rational coefficients and finite closed
intervals. It is an instructional companion, not a general optimizer.
"""


from dataclasses import dataclass
from fractions import Fraction
from typing import Iterable


def _q(value: int | Fraction, name: str) -> Fraction:
    """Convert an integer or Fraction to Fraction; reject bools and floats."""
    if isinstance(value, bool):
        raise TypeError(f"{name} must be an int or Fraction, not bool")
    if isinstance(value, Fraction):
        return value
    if isinstance(value, int):
        return Fraction(value)
    raise TypeError(f"{name} must be an int or Fraction; floats are not exact")


@dataclass(frozen=True)
class Optimum:
    """Result for optimization on a finite closed interval.

    `x_values` lists the maximizing/minimizing points when the polynomial is
    nonconstant. If `constant_on_interval` is true, every point in the interval
    is optimal and `x_values` contains its two endpoints as compact markers.
    """

    value: Fraction
    x_values: tuple[Fraction, ...]
    maximize: bool
    constant_on_interval: bool = False


def affine_value(slope: int | Fraction, intercept: int | Fraction,
                 x: int | Fraction) -> Fraction:
    """Evaluate m*x+b exactly."""
    m = _q(slope, "slope")
    b = _q(intercept, "intercept")
    xq = _q(x, "x")
    return m * xq + b


def quadratic_value(a: int | Fraction, b: int | Fraction,
                    c: int | Fraction, x: int | Fraction) -> Fraction:
    """Evaluate a*x**2+b*x+c exactly."""
    aq, bq, cq, xq = (_q(a, "a"), _q(b, "b"), _q(c, "c"), _q(x, "x"))
    return aq * xq * xq + bq * xq + cq


def quadratic_vertex(a: int | Fraction, b: int | Fraction,
                     c: int | Fraction) -> tuple[Fraction, Fraction]:
    """Return the exact vertex (h,k) of a*x**2+b*x+c; require a != 0."""
    aq, bq, cq = _q(a, "a"), _q(b, "b"), _q(c, "c")
    if aq == 0:
        raise ValueError("a must be nonzero for a quadratic vertex")
    h = -bq / (2 * aq)
    k = quadratic_value(aq, bq, cq, h)
    return h, k


def optimize_quadratic_on_closed_interval(
    a: int | Fraction,
    b: int | Fraction,
    c: int | Fraction,
    lower: int | Fraction,
    upper: int | Fraction,
    *,
    maximize: bool = True,
) -> Optimum:
    """Optimize a quadratic/affine/constant polynomial on [lower, upper].

    For a nonconstant quadratic, an extremum on a compact interval occurs at
    an endpoint or at the vertex when the vertex lies in the interval. For an
    affine function, endpoints suffice. The function rejects open or unbounded
    intervals because endpoint attainment would need a different result type.
    """
    if not isinstance(maximize, bool):
        raise TypeError("maximize must be bool")
    aq, bq, cq = _q(a, "a"), _q(b, "b"), _q(c, "c")
    lo, hi = _q(lower, "lower"), _q(upper, "upper")
    if lo > hi:
        raise ValueError("lower must be less than or equal to upper")

    candidates = {lo, hi}
    if aq != 0:
        h, _ = quadratic_vertex(aq, bq, cq)
        if lo <= h <= hi:
            candidates.add(h)

    values = {x: quadratic_value(aq, bq, cq, x) for x in candidates}
    best = (max if maximize else min)(values.values())
    if aq == 0 and bq == 0:
        return Optimum(best, (lo, hi), maximize, constant_on_interval=True)
    xs = tuple(sorted(x for x, value in values.items() if value == best))
    return Optimum(best, xs, maximize, constant_on_interval=False)


def optimize_quadratic_over_integers(
    a: int | Fraction,
    b: int | Fraction,
    c: int | Fraction,
    lower: int,
    upper: int,
    *,
    maximize: bool = True,
) -> Optimum:
    """Optimize exactly over integer x in the inclusive range [lower, upper].

    For a quadratic, checking the integer endpoints and the floor/ceiling of
    the vertex is sufficient. For an affine or constant objective, endpoints
    suffice. The returned x_values are integer-valued Fractions.
    """
    if isinstance(lower, bool) or not isinstance(lower, int):
        raise TypeError("lower must be an integer")
    if isinstance(upper, bool) or not isinstance(upper, int):
        raise TypeError("upper must be an integer")
    if lower > upper:
        raise ValueError("lower must be less than or equal to upper")
    if not isinstance(maximize, bool):
        raise TypeError("maximize must be bool")
    aq, bq, cq = _q(a, "a"), _q(b, "b"), _q(c, "c")
    candidates = {lower, upper}
    if aq != 0:
        h, _ = quadratic_vertex(aq, bq, cq)
        floor_h = h.numerator // h.denominator
        for candidate in (floor_h, floor_h + 1):
            if lower <= candidate <= upper:
                candidates.add(candidate)
    values = {x: quadratic_value(aq, bq, cq, x) for x in candidates}
    best = (max if maximize else min)(values.values())
    if aq == 0 and bq == 0:
        return Optimum(best, (Fraction(lower), Fraction(upper)), maximize,
                       constant_on_interval=True)
    xs = tuple(Fraction(x) for x, value in sorted(values.items()) if value == best)
    return Optimum(best, xs, maximize, constant_on_interval=False)


def linear_change(slope: int | Fraction, delta_x: int | Fraction) -> Fraction:
    """Return the exact output change m*delta_x of an affine model."""
    return _q(slope, "slope") * _q(delta_x, "delta_x")


def quadratic_change(a: int | Fraction, b: int | Fraction,
                     x0: int | Fraction, delta_x: int | Fraction) -> Fraction:
    """Return f(x0+dx)-f(x0) exactly for f(x)=a*x**2+b*x+c."""
    aq, bq = _q(a, "a"), _q(b, "b")
    xq, dx = _q(x0, "x0"), _q(delta_x, "delta_x")
    return (2 * aq * xq + bq) * dx + aq * dx * dx


def profit_at_quantity(price: int | Fraction, unit_cost: int | Fraction,
                       fixed_cost: int | Fraction,
                       quantity: int | Fraction) -> Fraction:
    """Return P(q)=(price-unit_cost)*q-fixed_cost for q >= 0."""
    p, v, f, q = (_q(price, "price"), _q(unit_cost, "unit_cost"),
                  _q(fixed_cost, "fixed_cost"), _q(quantity, "quantity"))
    if q < 0:
        raise ValueError("quantity must be nonnegative")
    return (p - v) * q - f


def intersect_closed_intervals(
    intervals: Iterable[tuple[int | Fraction, int | Fraction]],
) -> tuple[Fraction, Fraction] | None:
    """Return the intersection of finitely many closed intervals, or None.

    An empty iterable represents the whole real line and is therefore not a
    finite interval; this helper rejects it rather than inventing bounds.
    """
    normalized = []
    for index, interval in enumerate(intervals):
        try:
            left, right = interval
        except Exception as exc:
            raise TypeError(f"interval {index} must contain exactly two bounds") from exc
        lo, hi = _q(left, f"interval[{index}].lower"), _q(right, f"interval[{index}].upper")
        if lo > hi:
            raise ValueError(f"interval {index} has lower bound above upper bound")
        normalized.append((lo, hi))
    if not normalized:
        raise ValueError("at least one bounded interval is required")
    lo = max(pair[0] for pair in normalized)
    hi = min(pair[1] for pair in normalized)
    return (lo, hi) if lo <= hi else None

# --- Chapter example ---
affine_value = affine_value
profit_at_quantity = profit_at_quantity

from fractions import Fraction


cost = affine_value(Fraction(3, 2), 6, 12)
profit = profit_at_quantity(14, 6, 240, 30)
print(cost, profit)
```

Expected output:

```text
24 0
```

### Example 15 — Optimize a quadratic on a closed interval

```python
from __future__ import annotations

# --- Inlined implementation: modeling_core ---
"""Exact helpers for elementary algebraic modeling and bounded optimization.

The module intentionally supports rational coefficients and finite closed
intervals. It is an instructional companion, not a general optimizer.
"""


from dataclasses import dataclass
from fractions import Fraction
from typing import Iterable


def _q(value: int | Fraction, name: str) -> Fraction:
    """Convert an integer or Fraction to Fraction; reject bools and floats."""
    if isinstance(value, bool):
        raise TypeError(f"{name} must be an int or Fraction, not bool")
    if isinstance(value, Fraction):
        return value
    if isinstance(value, int):
        return Fraction(value)
    raise TypeError(f"{name} must be an int or Fraction; floats are not exact")


@dataclass(frozen=True)
class Optimum:
    """Result for optimization on a finite closed interval.

    `x_values` lists the maximizing/minimizing points when the polynomial is
    nonconstant. If `constant_on_interval` is true, every point in the interval
    is optimal and `x_values` contains its two endpoints as compact markers.
    """

    value: Fraction
    x_values: tuple[Fraction, ...]
    maximize: bool
    constant_on_interval: bool = False


def affine_value(slope: int | Fraction, intercept: int | Fraction,
                 x: int | Fraction) -> Fraction:
    """Evaluate m*x+b exactly."""
    m = _q(slope, "slope")
    b = _q(intercept, "intercept")
    xq = _q(x, "x")
    return m * xq + b


def quadratic_value(a: int | Fraction, b: int | Fraction,
                    c: int | Fraction, x: int | Fraction) -> Fraction:
    """Evaluate a*x**2+b*x+c exactly."""
    aq, bq, cq, xq = (_q(a, "a"), _q(b, "b"), _q(c, "c"), _q(x, "x"))
    return aq * xq * xq + bq * xq + cq


def quadratic_vertex(a: int | Fraction, b: int | Fraction,
                     c: int | Fraction) -> tuple[Fraction, Fraction]:
    """Return the exact vertex (h,k) of a*x**2+b*x+c; require a != 0."""
    aq, bq, cq = _q(a, "a"), _q(b, "b"), _q(c, "c")
    if aq == 0:
        raise ValueError("a must be nonzero for a quadratic vertex")
    h = -bq / (2 * aq)
    k = quadratic_value(aq, bq, cq, h)
    return h, k


def optimize_quadratic_on_closed_interval(
    a: int | Fraction,
    b: int | Fraction,
    c: int | Fraction,
    lower: int | Fraction,
    upper: int | Fraction,
    *,
    maximize: bool = True,
) -> Optimum:
    """Optimize a quadratic/affine/constant polynomial on [lower, upper].

    For a nonconstant quadratic, an extremum on a compact interval occurs at
    an endpoint or at the vertex when the vertex lies in the interval. For an
    affine function, endpoints suffice. The function rejects open or unbounded
    intervals because endpoint attainment would need a different result type.
    """
    if not isinstance(maximize, bool):
        raise TypeError("maximize must be bool")
    aq, bq, cq = _q(a, "a"), _q(b, "b"), _q(c, "c")
    lo, hi = _q(lower, "lower"), _q(upper, "upper")
    if lo > hi:
        raise ValueError("lower must be less than or equal to upper")

    candidates = {lo, hi}
    if aq != 0:
        h, _ = quadratic_vertex(aq, bq, cq)
        if lo <= h <= hi:
            candidates.add(h)

    values = {x: quadratic_value(aq, bq, cq, x) for x in candidates}
    best = (max if maximize else min)(values.values())
    if aq == 0 and bq == 0:
        return Optimum(best, (lo, hi), maximize, constant_on_interval=True)
    xs = tuple(sorted(x for x, value in values.items() if value == best))
    return Optimum(best, xs, maximize, constant_on_interval=False)


def optimize_quadratic_over_integers(
    a: int | Fraction,
    b: int | Fraction,
    c: int | Fraction,
    lower: int,
    upper: int,
    *,
    maximize: bool = True,
) -> Optimum:
    """Optimize exactly over integer x in the inclusive range [lower, upper].

    For a quadratic, checking the integer endpoints and the floor/ceiling of
    the vertex is sufficient. For an affine or constant objective, endpoints
    suffice. The returned x_values are integer-valued Fractions.
    """
    if isinstance(lower, bool) or not isinstance(lower, int):
        raise TypeError("lower must be an integer")
    if isinstance(upper, bool) or not isinstance(upper, int):
        raise TypeError("upper must be an integer")
    if lower > upper:
        raise ValueError("lower must be less than or equal to upper")
    if not isinstance(maximize, bool):
        raise TypeError("maximize must be bool")
    aq, bq, cq = _q(a, "a"), _q(b, "b"), _q(c, "c")
    candidates = {lower, upper}
    if aq != 0:
        h, _ = quadratic_vertex(aq, bq, cq)
        floor_h = h.numerator // h.denominator
        for candidate in (floor_h, floor_h + 1):
            if lower <= candidate <= upper:
                candidates.add(candidate)
    values = {x: quadratic_value(aq, bq, cq, x) for x in candidates}
    best = (max if maximize else min)(values.values())
    if aq == 0 and bq == 0:
        return Optimum(best, (Fraction(lower), Fraction(upper)), maximize,
                       constant_on_interval=True)
    xs = tuple(Fraction(x) for x, value in sorted(values.items()) if value == best)
    return Optimum(best, xs, maximize, constant_on_interval=False)


def linear_change(slope: int | Fraction, delta_x: int | Fraction) -> Fraction:
    """Return the exact output change m*delta_x of an affine model."""
    return _q(slope, "slope") * _q(delta_x, "delta_x")


def quadratic_change(a: int | Fraction, b: int | Fraction,
                     x0: int | Fraction, delta_x: int | Fraction) -> Fraction:
    """Return f(x0+dx)-f(x0) exactly for f(x)=a*x**2+b*x+c."""
    aq, bq = _q(a, "a"), _q(b, "b")
    xq, dx = _q(x0, "x0"), _q(delta_x, "delta_x")
    return (2 * aq * xq + bq) * dx + aq * dx * dx


def profit_at_quantity(price: int | Fraction, unit_cost: int | Fraction,
                       fixed_cost: int | Fraction,
                       quantity: int | Fraction) -> Fraction:
    """Return P(q)=(price-unit_cost)*q-fixed_cost for q >= 0."""
    p, v, f, q = (_q(price, "price"), _q(unit_cost, "unit_cost"),
                  _q(fixed_cost, "fixed_cost"), _q(quantity, "quantity"))
    if q < 0:
        raise ValueError("quantity must be nonnegative")
    return (p - v) * q - f


def intersect_closed_intervals(
    intervals: Iterable[tuple[int | Fraction, int | Fraction]],
) -> tuple[Fraction, Fraction] | None:
    """Return the intersection of finitely many closed intervals, or None.

    An empty iterable represents the whole real line and is therefore not a
    finite interval; this helper rejects it rather than inventing bounds.
    """
    normalized = []
    for index, interval in enumerate(intervals):
        try:
            left, right = interval
        except Exception as exc:
            raise TypeError(f"interval {index} must contain exactly two bounds") from exc
        lo, hi = _q(left, f"interval[{index}].lower"), _q(right, f"interval[{index}].upper")
        if lo > hi:
            raise ValueError(f"interval {index} has lower bound above upper bound")
        normalized.append((lo, hi))
    if not normalized:
        raise ValueError("at least one bounded interval is required")
    lo = max(pair[0] for pair in normalized)
    hi = min(pair[1] for pair in normalized)
    return (lo, hi) if lo <= hi else None

# --- Chapter example ---
optimize_quadratic_on_closed_interval = optimize_quadratic_on_closed_interval

result = optimize_quadratic_on_closed_interval(-3, 12, 5, 0, 5, maximize=True)
print(result.value, result.x_values)
```

Expected output:

```text
17 (Fraction(2, 1),)
```

### Example 16 — Respect an integer decision

```python
from __future__ import annotations

# --- Inlined implementation: modeling_core ---
"""Exact helpers for elementary algebraic modeling and bounded optimization.

The module intentionally supports rational coefficients and finite closed
intervals. It is an instructional companion, not a general optimizer.
"""


from dataclasses import dataclass
from fractions import Fraction
from typing import Iterable


def _q(value: int | Fraction, name: str) -> Fraction:
    """Convert an integer or Fraction to Fraction; reject bools and floats."""
    if isinstance(value, bool):
        raise TypeError(f"{name} must be an int or Fraction, not bool")
    if isinstance(value, Fraction):
        return value
    if isinstance(value, int):
        return Fraction(value)
    raise TypeError(f"{name} must be an int or Fraction; floats are not exact")


@dataclass(frozen=True)
class Optimum:
    """Result for optimization on a finite closed interval.

    `x_values` lists the maximizing/minimizing points when the polynomial is
    nonconstant. If `constant_on_interval` is true, every point in the interval
    is optimal and `x_values` contains its two endpoints as compact markers.
    """

    value: Fraction
    x_values: tuple[Fraction, ...]
    maximize: bool
    constant_on_interval: bool = False


def affine_value(slope: int | Fraction, intercept: int | Fraction,
                 x: int | Fraction) -> Fraction:
    """Evaluate m*x+b exactly."""
    m = _q(slope, "slope")
    b = _q(intercept, "intercept")
    xq = _q(x, "x")
    return m * xq + b


def quadratic_value(a: int | Fraction, b: int | Fraction,
                    c: int | Fraction, x: int | Fraction) -> Fraction:
    """Evaluate a*x**2+b*x+c exactly."""
    aq, bq, cq, xq = (_q(a, "a"), _q(b, "b"), _q(c, "c"), _q(x, "x"))
    return aq * xq * xq + bq * xq + cq


def quadratic_vertex(a: int | Fraction, b: int | Fraction,
                     c: int | Fraction) -> tuple[Fraction, Fraction]:
    """Return the exact vertex (h,k) of a*x**2+b*x+c; require a != 0."""
    aq, bq, cq = _q(a, "a"), _q(b, "b"), _q(c, "c")
    if aq == 0:
        raise ValueError("a must be nonzero for a quadratic vertex")
    h = -bq / (2 * aq)
    k = quadratic_value(aq, bq, cq, h)
    return h, k


def optimize_quadratic_on_closed_interval(
    a: int | Fraction,
    b: int | Fraction,
    c: int | Fraction,
    lower: int | Fraction,
    upper: int | Fraction,
    *,
    maximize: bool = True,
) -> Optimum:
    """Optimize a quadratic/affine/constant polynomial on [lower, upper].

    For a nonconstant quadratic, an extremum on a compact interval occurs at
    an endpoint or at the vertex when the vertex lies in the interval. For an
    affine function, endpoints suffice. The function rejects open or unbounded
    intervals because endpoint attainment would need a different result type.
    """
    if not isinstance(maximize, bool):
        raise TypeError("maximize must be bool")
    aq, bq, cq = _q(a, "a"), _q(b, "b"), _q(c, "c")
    lo, hi = _q(lower, "lower"), _q(upper, "upper")
    if lo > hi:
        raise ValueError("lower must be less than or equal to upper")

    candidates = {lo, hi}
    if aq != 0:
        h, _ = quadratic_vertex(aq, bq, cq)
        if lo <= h <= hi:
            candidates.add(h)

    values = {x: quadratic_value(aq, bq, cq, x) for x in candidates}
    best = (max if maximize else min)(values.values())
    if aq == 0 and bq == 0:
        return Optimum(best, (lo, hi), maximize, constant_on_interval=True)
    xs = tuple(sorted(x for x, value in values.items() if value == best))
    return Optimum(best, xs, maximize, constant_on_interval=False)


def optimize_quadratic_over_integers(
    a: int | Fraction,
    b: int | Fraction,
    c: int | Fraction,
    lower: int,
    upper: int,
    *,
    maximize: bool = True,
) -> Optimum:
    """Optimize exactly over integer x in the inclusive range [lower, upper].

    For a quadratic, checking the integer endpoints and the floor/ceiling of
    the vertex is sufficient. For an affine or constant objective, endpoints
    suffice. The returned x_values are integer-valued Fractions.
    """
    if isinstance(lower, bool) or not isinstance(lower, int):
        raise TypeError("lower must be an integer")
    if isinstance(upper, bool) or not isinstance(upper, int):
        raise TypeError("upper must be an integer")
    if lower > upper:
        raise ValueError("lower must be less than or equal to upper")
    if not isinstance(maximize, bool):
        raise TypeError("maximize must be bool")
    aq, bq, cq = _q(a, "a"), _q(b, "b"), _q(c, "c")
    candidates = {lower, upper}
    if aq != 0:
        h, _ = quadratic_vertex(aq, bq, cq)
        floor_h = h.numerator // h.denominator
        for candidate in (floor_h, floor_h + 1):
            if lower <= candidate <= upper:
                candidates.add(candidate)
    values = {x: quadratic_value(aq, bq, cq, x) for x in candidates}
    best = (max if maximize else min)(values.values())
    if aq == 0 and bq == 0:
        return Optimum(best, (Fraction(lower), Fraction(upper)), maximize,
                       constant_on_interval=True)
    xs = tuple(Fraction(x) for x, value in sorted(values.items()) if value == best)
    return Optimum(best, xs, maximize, constant_on_interval=False)


def linear_change(slope: int | Fraction, delta_x: int | Fraction) -> Fraction:
    """Return the exact output change m*delta_x of an affine model."""
    return _q(slope, "slope") * _q(delta_x, "delta_x")


def quadratic_change(a: int | Fraction, b: int | Fraction,
                     x0: int | Fraction, delta_x: int | Fraction) -> Fraction:
    """Return f(x0+dx)-f(x0) exactly for f(x)=a*x**2+b*x+c."""
    aq, bq = _q(a, "a"), _q(b, "b")
    xq, dx = _q(x0, "x0"), _q(delta_x, "delta_x")
    return (2 * aq * xq + bq) * dx + aq * dx * dx


def profit_at_quantity(price: int | Fraction, unit_cost: int | Fraction,
                       fixed_cost: int | Fraction,
                       quantity: int | Fraction) -> Fraction:
    """Return P(q)=(price-unit_cost)*q-fixed_cost for q >= 0."""
    p, v, f, q = (_q(price, "price"), _q(unit_cost, "unit_cost"),
                  _q(fixed_cost, "fixed_cost"), _q(quantity, "quantity"))
    if q < 0:
        raise ValueError("quantity must be nonnegative")
    return (p - v) * q - f


def intersect_closed_intervals(
    intervals: Iterable[tuple[int | Fraction, int | Fraction]],
) -> tuple[Fraction, Fraction] | None:
    """Return the intersection of finitely many closed intervals, or None.

    An empty iterable represents the whole real line and is therefore not a
    finite interval; this helper rejects it rather than inventing bounds.
    """
    normalized = []
    for index, interval in enumerate(intervals):
        try:
            left, right = interval
        except Exception as exc:
            raise TypeError(f"interval {index} must contain exactly two bounds") from exc
        lo, hi = _q(left, f"interval[{index}].lower"), _q(right, f"interval[{index}].upper")
        if lo > hi:
            raise ValueError(f"interval {index} has lower bound above upper bound")
        normalized.append((lo, hi))
    if not normalized:
        raise ValueError("at least one bounded interval is required")
    lo = max(pair[0] for pair in normalized)
    hi = min(pair[1] for pair in normalized)
    return (lo, hi) if lo <= hi else None

# --- Chapter example ---
optimize_quadratic_over_integers = optimize_quadratic_over_integers

result = optimize_quadratic_over_integers(-2, 19, -20, 0, 10, maximize=True)
print(result.value, result.x_values)
```

Expected output:

```text
25 (Fraction(5, 1),)
```

### Example 17 — Intersect constraints exactly

```python
from __future__ import annotations

# --- Inlined implementation: modeling_core ---
"""Exact helpers for elementary algebraic modeling and bounded optimization.

The module intentionally supports rational coefficients and finite closed
intervals. It is an instructional companion, not a general optimizer.
"""


from dataclasses import dataclass
from fractions import Fraction
from typing import Iterable


def _q(value: int | Fraction, name: str) -> Fraction:
    """Convert an integer or Fraction to Fraction; reject bools and floats."""
    if isinstance(value, bool):
        raise TypeError(f"{name} must be an int or Fraction, not bool")
    if isinstance(value, Fraction):
        return value
    if isinstance(value, int):
        return Fraction(value)
    raise TypeError(f"{name} must be an int or Fraction; floats are not exact")


@dataclass(frozen=True)
class Optimum:
    """Result for optimization on a finite closed interval.

    `x_values` lists the maximizing/minimizing points when the polynomial is
    nonconstant. If `constant_on_interval` is true, every point in the interval
    is optimal and `x_values` contains its two endpoints as compact markers.
    """

    value: Fraction
    x_values: tuple[Fraction, ...]
    maximize: bool
    constant_on_interval: bool = False


def affine_value(slope: int | Fraction, intercept: int | Fraction,
                 x: int | Fraction) -> Fraction:
    """Evaluate m*x+b exactly."""
    m = _q(slope, "slope")
    b = _q(intercept, "intercept")
    xq = _q(x, "x")
    return m * xq + b


def quadratic_value(a: int | Fraction, b: int | Fraction,
                    c: int | Fraction, x: int | Fraction) -> Fraction:
    """Evaluate a*x**2+b*x+c exactly."""
    aq, bq, cq, xq = (_q(a, "a"), _q(b, "b"), _q(c, "c"), _q(x, "x"))
    return aq * xq * xq + bq * xq + cq


def quadratic_vertex(a: int | Fraction, b: int | Fraction,
                     c: int | Fraction) -> tuple[Fraction, Fraction]:
    """Return the exact vertex (h,k) of a*x**2+b*x+c; require a != 0."""
    aq, bq, cq = _q(a, "a"), _q(b, "b"), _q(c, "c")
    if aq == 0:
        raise ValueError("a must be nonzero for a quadratic vertex")
    h = -bq / (2 * aq)
    k = quadratic_value(aq, bq, cq, h)
    return h, k


def optimize_quadratic_on_closed_interval(
    a: int | Fraction,
    b: int | Fraction,
    c: int | Fraction,
    lower: int | Fraction,
    upper: int | Fraction,
    *,
    maximize: bool = True,
) -> Optimum:
    """Optimize a quadratic/affine/constant polynomial on [lower, upper].

    For a nonconstant quadratic, an extremum on a compact interval occurs at
    an endpoint or at the vertex when the vertex lies in the interval. For an
    affine function, endpoints suffice. The function rejects open or unbounded
    intervals because endpoint attainment would need a different result type.
    """
    if not isinstance(maximize, bool):
        raise TypeError("maximize must be bool")
    aq, bq, cq = _q(a, "a"), _q(b, "b"), _q(c, "c")
    lo, hi = _q(lower, "lower"), _q(upper, "upper")
    if lo > hi:
        raise ValueError("lower must be less than or equal to upper")

    candidates = {lo, hi}
    if aq != 0:
        h, _ = quadratic_vertex(aq, bq, cq)
        if lo <= h <= hi:
            candidates.add(h)

    values = {x: quadratic_value(aq, bq, cq, x) for x in candidates}
    best = (max if maximize else min)(values.values())
    if aq == 0 and bq == 0:
        return Optimum(best, (lo, hi), maximize, constant_on_interval=True)
    xs = tuple(sorted(x for x, value in values.items() if value == best))
    return Optimum(best, xs, maximize, constant_on_interval=False)


def optimize_quadratic_over_integers(
    a: int | Fraction,
    b: int | Fraction,
    c: int | Fraction,
    lower: int,
    upper: int,
    *,
    maximize: bool = True,
) -> Optimum:
    """Optimize exactly over integer x in the inclusive range [lower, upper].

    For a quadratic, checking the integer endpoints and the floor/ceiling of
    the vertex is sufficient. For an affine or constant objective, endpoints
    suffice. The returned x_values are integer-valued Fractions.
    """
    if isinstance(lower, bool) or not isinstance(lower, int):
        raise TypeError("lower must be an integer")
    if isinstance(upper, bool) or not isinstance(upper, int):
        raise TypeError("upper must be an integer")
    if lower > upper:
        raise ValueError("lower must be less than or equal to upper")
    if not isinstance(maximize, bool):
        raise TypeError("maximize must be bool")
    aq, bq, cq = _q(a, "a"), _q(b, "b"), _q(c, "c")
    candidates = {lower, upper}
    if aq != 0:
        h, _ = quadratic_vertex(aq, bq, cq)
        floor_h = h.numerator // h.denominator
        for candidate in (floor_h, floor_h + 1):
            if lower <= candidate <= upper:
                candidates.add(candidate)
    values = {x: quadratic_value(aq, bq, cq, x) for x in candidates}
    best = (max if maximize else min)(values.values())
    if aq == 0 and bq == 0:
        return Optimum(best, (Fraction(lower), Fraction(upper)), maximize,
                       constant_on_interval=True)
    xs = tuple(Fraction(x) for x, value in sorted(values.items()) if value == best)
    return Optimum(best, xs, maximize, constant_on_interval=False)


def linear_change(slope: int | Fraction, delta_x: int | Fraction) -> Fraction:
    """Return the exact output change m*delta_x of an affine model."""
    return _q(slope, "slope") * _q(delta_x, "delta_x")


def quadratic_change(a: int | Fraction, b: int | Fraction,
                     x0: int | Fraction, delta_x: int | Fraction) -> Fraction:
    """Return f(x0+dx)-f(x0) exactly for f(x)=a*x**2+b*x+c."""
    aq, bq = _q(a, "a"), _q(b, "b")
    xq, dx = _q(x0, "x0"), _q(delta_x, "delta_x")
    return (2 * aq * xq + bq) * dx + aq * dx * dx


def profit_at_quantity(price: int | Fraction, unit_cost: int | Fraction,
                       fixed_cost: int | Fraction,
                       quantity: int | Fraction) -> Fraction:
    """Return P(q)=(price-unit_cost)*q-fixed_cost for q >= 0."""
    p, v, f, q = (_q(price, "price"), _q(unit_cost, "unit_cost"),
                  _q(fixed_cost, "fixed_cost"), _q(quantity, "quantity"))
    if q < 0:
        raise ValueError("quantity must be nonnegative")
    return (p - v) * q - f


def intersect_closed_intervals(
    intervals: Iterable[tuple[int | Fraction, int | Fraction]],
) -> tuple[Fraction, Fraction] | None:
    """Return the intersection of finitely many closed intervals, or None.

    An empty iterable represents the whole real line and is therefore not a
    finite interval; this helper rejects it rather than inventing bounds.
    """
    normalized = []
    for index, interval in enumerate(intervals):
        try:
            left, right = interval
        except Exception as exc:
            raise TypeError(f"interval {index} must contain exactly two bounds") from exc
        lo, hi = _q(left, f"interval[{index}].lower"), _q(right, f"interval[{index}].upper")
        if lo > hi:
            raise ValueError(f"interval {index} has lower bound above upper bound")
        normalized.append((lo, hi))
    if not normalized:
        raise ValueError("at least one bounded interval is required")
    lo = max(pair[0] for pair in normalized)
    hi = min(pair[1] for pair in normalized)
    return (lo, hi) if lo <= hi else None

# --- Chapter example ---
intersect_closed_intervals = intersect_closed_intervals

from fractions import Fraction


feasible = intersect_closed_intervals([
    (0, 12),
    (3, 10),
    (Fraction(7, 2), 8),
])
print(feasible)
```

Expected output:

```text
(Fraction(7, 2), Fraction(8, 1))
```

### Example 18 — Compute a finite sensitivity change

```python
from __future__ import annotations

# --- Inlined implementation: modeling_core ---
"""Exact helpers for elementary algebraic modeling and bounded optimization.

The module intentionally supports rational coefficients and finite closed
intervals. It is an instructional companion, not a general optimizer.
"""


from dataclasses import dataclass
from fractions import Fraction
from typing import Iterable


def _q(value: int | Fraction, name: str) -> Fraction:
    """Convert an integer or Fraction to Fraction; reject bools and floats."""
    if isinstance(value, bool):
        raise TypeError(f"{name} must be an int or Fraction, not bool")
    if isinstance(value, Fraction):
        return value
    if isinstance(value, int):
        return Fraction(value)
    raise TypeError(f"{name} must be an int or Fraction; floats are not exact")


@dataclass(frozen=True)
class Optimum:
    """Result for optimization on a finite closed interval.

    `x_values` lists the maximizing/minimizing points when the polynomial is
    nonconstant. If `constant_on_interval` is true, every point in the interval
    is optimal and `x_values` contains its two endpoints as compact markers.
    """

    value: Fraction
    x_values: tuple[Fraction, ...]
    maximize: bool
    constant_on_interval: bool = False


def affine_value(slope: int | Fraction, intercept: int | Fraction,
                 x: int | Fraction) -> Fraction:
    """Evaluate m*x+b exactly."""
    m = _q(slope, "slope")
    b = _q(intercept, "intercept")
    xq = _q(x, "x")
    return m * xq + b


def quadratic_value(a: int | Fraction, b: int | Fraction,
                    c: int | Fraction, x: int | Fraction) -> Fraction:
    """Evaluate a*x**2+b*x+c exactly."""
    aq, bq, cq, xq = (_q(a, "a"), _q(b, "b"), _q(c, "c"), _q(x, "x"))
    return aq * xq * xq + bq * xq + cq


def quadratic_vertex(a: int | Fraction, b: int | Fraction,
                     c: int | Fraction) -> tuple[Fraction, Fraction]:
    """Return the exact vertex (h,k) of a*x**2+b*x+c; require a != 0."""
    aq, bq, cq = _q(a, "a"), _q(b, "b"), _q(c, "c")
    if aq == 0:
        raise ValueError("a must be nonzero for a quadratic vertex")
    h = -bq / (2 * aq)
    k = quadratic_value(aq, bq, cq, h)
    return h, k


def optimize_quadratic_on_closed_interval(
    a: int | Fraction,
    b: int | Fraction,
    c: int | Fraction,
    lower: int | Fraction,
    upper: int | Fraction,
    *,
    maximize: bool = True,
) -> Optimum:
    """Optimize a quadratic/affine/constant polynomial on [lower, upper].

    For a nonconstant quadratic, an extremum on a compact interval occurs at
    an endpoint or at the vertex when the vertex lies in the interval. For an
    affine function, endpoints suffice. The function rejects open or unbounded
    intervals because endpoint attainment would need a different result type.
    """
    if not isinstance(maximize, bool):
        raise TypeError("maximize must be bool")
    aq, bq, cq = _q(a, "a"), _q(b, "b"), _q(c, "c")
    lo, hi = _q(lower, "lower"), _q(upper, "upper")
    if lo > hi:
        raise ValueError("lower must be less than or equal to upper")

    candidates = {lo, hi}
    if aq != 0:
        h, _ = quadratic_vertex(aq, bq, cq)
        if lo <= h <= hi:
            candidates.add(h)

    values = {x: quadratic_value(aq, bq, cq, x) for x in candidates}
    best = (max if maximize else min)(values.values())
    if aq == 0 and bq == 0:
        return Optimum(best, (lo, hi), maximize, constant_on_interval=True)
    xs = tuple(sorted(x for x, value in values.items() if value == best))
    return Optimum(best, xs, maximize, constant_on_interval=False)


def optimize_quadratic_over_integers(
    a: int | Fraction,
    b: int | Fraction,
    c: int | Fraction,
    lower: int,
    upper: int,
    *,
    maximize: bool = True,
) -> Optimum:
    """Optimize exactly over integer x in the inclusive range [lower, upper].

    For a quadratic, checking the integer endpoints and the floor/ceiling of
    the vertex is sufficient. For an affine or constant objective, endpoints
    suffice. The returned x_values are integer-valued Fractions.
    """
    if isinstance(lower, bool) or not isinstance(lower, int):
        raise TypeError("lower must be an integer")
    if isinstance(upper, bool) or not isinstance(upper, int):
        raise TypeError("upper must be an integer")
    if lower > upper:
        raise ValueError("lower must be less than or equal to upper")
    if not isinstance(maximize, bool):
        raise TypeError("maximize must be bool")
    aq, bq, cq = _q(a, "a"), _q(b, "b"), _q(c, "c")
    candidates = {lower, upper}
    if aq != 0:
        h, _ = quadratic_vertex(aq, bq, cq)
        floor_h = h.numerator // h.denominator
        for candidate in (floor_h, floor_h + 1):
            if lower <= candidate <= upper:
                candidates.add(candidate)
    values = {x: quadratic_value(aq, bq, cq, x) for x in candidates}
    best = (max if maximize else min)(values.values())
    if aq == 0 and bq == 0:
        return Optimum(best, (Fraction(lower), Fraction(upper)), maximize,
                       constant_on_interval=True)
    xs = tuple(Fraction(x) for x, value in sorted(values.items()) if value == best)
    return Optimum(best, xs, maximize, constant_on_interval=False)


def linear_change(slope: int | Fraction, delta_x: int | Fraction) -> Fraction:
    """Return the exact output change m*delta_x of an affine model."""
    return _q(slope, "slope") * _q(delta_x, "delta_x")


def quadratic_change(a: int | Fraction, b: int | Fraction,
                     x0: int | Fraction, delta_x: int | Fraction) -> Fraction:
    """Return f(x0+dx)-f(x0) exactly for f(x)=a*x**2+b*x+c."""
    aq, bq = _q(a, "a"), _q(b, "b")
    xq, dx = _q(x0, "x0"), _q(delta_x, "delta_x")
    return (2 * aq * xq + bq) * dx + aq * dx * dx


def profit_at_quantity(price: int | Fraction, unit_cost: int | Fraction,
                       fixed_cost: int | Fraction,
                       quantity: int | Fraction) -> Fraction:
    """Return P(q)=(price-unit_cost)*q-fixed_cost for q >= 0."""
    p, v, f, q = (_q(price, "price"), _q(unit_cost, "unit_cost"),
                  _q(fixed_cost, "fixed_cost"), _q(quantity, "quantity"))
    if q < 0:
        raise ValueError("quantity must be nonnegative")
    return (p - v) * q - f


def intersect_closed_intervals(
    intervals: Iterable[tuple[int | Fraction, int | Fraction]],
) -> tuple[Fraction, Fraction] | None:
    """Return the intersection of finitely many closed intervals, or None.

    An empty iterable represents the whole real line and is therefore not a
    finite interval; this helper rejects it rather than inventing bounds.
    """
    normalized = []
    for index, interval in enumerate(intervals):
        try:
            left, right = interval
        except Exception as exc:
            raise TypeError(f"interval {index} must contain exactly two bounds") from exc
        lo, hi = _q(left, f"interval[{index}].lower"), _q(right, f"interval[{index}].upper")
        if lo > hi:
            raise ValueError(f"interval {index} has lower bound above upper bound")
        normalized.append((lo, hi))
    if not normalized:
        raise ValueError("at least one bounded interval is required")
    lo = max(pair[0] for pair in normalized)
    hi = min(pair[1] for pair in normalized)
    return (lo, hi) if lo <= hi else None

# --- Chapter example ---
quadratic_change = quadratic_change

from fractions import Fraction


change = quadratic_change(2, 3, 4, Fraction(1, 10))
print(change)
```

Expected output:

```text
48/25
```

These helpers validate selected calculations; they do not infer a model from raw data, establish that the assumptions are appropriate, or solve arbitrary nonlinear optimization problems. A numerical result is not a proof that a model accurately represents the real situation.

## 14. Common modeling and optimization errors

- Defining an objective but forgetting the constraints that define feasible choices.
- Treating parameters as variables or changing several parameters without stating which are held fixed.
- Mixing units, such as multiplying a per-minute rate by a number of hours.
- Reporting a break-even quantity as a profit maximum.
- Using the unrestricted vertex when it lies outside the feasible interval.
- Checking only the vertex and omitting interval endpoints.
- Treating a continuous optimum as an attainable integer decision.
- Claiming a maximum on an open interval when only a supremum exists.
- Ignoring the original context after solving the algebraic model.
- Interpreting a model outside its calibration range without qualification.
- Treating computed or sampled values as proof of a general statement.

## 15. Exercises

### A. Construct and interpret models

1. A membership costs 18 units initially and 4 units per visit. Define a total-cost model $C(n)$ and state the contextual domain of $n$.
2. A mobile plan charges 25 units per month plus 0.08 units per text message. Write a model and calculate the monthly charge for 150 messages.
3. A manufacturer has fixed cost 180, variable cost 7 per item, and selling price 19 per item. Write cost, revenue, and profit models.
4. For Exercise 3, find the break-even quantity and explain whether it is an integer production quantity.
5. A rectangle has perimeter 36 meters. Express its area in terms of one side $x$ and state the feasible interval for a nondegenerate rectangle.
6. A rectangular pen uses 72 meters of fencing on three sides beside a wall. Write its area model and state the feasible interval.
7. A company uses the model $D(t)=500-12t$ for remaining inventory after $t$ days. State when the model predicts zero inventory and explain why negative predictions may be inadmissible.
8. A service has total cost $C(q)=90+5q$ and revenue $R(q)=11q$. Write the profit function and find the break-even quantity.

### B. Continuous optimization

9. Maximize $A(x)=x(18-x)$ for $0\leq x\leq18$.
10. Find the maximum and minimum of $f(x)=-3x^2+12x+5$ on $[0,5]$.
11. Find the maximum and minimum of $g(x)=-(x-7)^2+10$ on $[0,5]$.
12. Find the minimum of $h(x)=x^2+4x+8$ on $[-4,1]$.
13. Find the maximum and minimum of the affine function $p(x)=7-2x$ on $[2,6]$.
14. On the open interval $(0,1)$, does $f(x)=x$ have a maximum? State its supremum.
15. A feasible set is $[0,12]\cap[3,10]\cap[7/2,8]$. Find the resulting interval.
16. Explain why a feasible point is not necessarily an optimal point.

### C. Integer decisions and sensitivity

17. Maximize $P(q)=-2q^2+19q-20$ over integers $0\leq q\leq10$.
18. Maximize $Q(n)=-(n-7.5)^2+20$ over integers $2\leq n\leq12$. Identify every maximizing integer.
19. For $f(x)=2x^2+3x+5$, calculate the exact change when $x$ moves from 4 to $4.1$.
20. For the affine model $y=8-3x$, find the output change when $x$ increases by $5/2$.
21. In $C(q)=F+vq$, explain how a change $\Delta v$ in the variable-cost parameter changes the modeled cost at a fixed quantity $q$.
22. A quadratic model has vertex input $x=9$, but the contextual feasible interval is $[0,6]$. Explain why the vertex value is not an attainable optimum and state which inputs must be checked for extrema.

### D. Model reasoning

23. Give two assumptions behind a constant-price revenue model $R(q)=pq$ and describe one situation in which it could fail.
24. A continuous model predicts an optimal production quantity of 6.4 items. Explain what additional step is required when only whole items can be produced.

## 16. Selected answers

1. $C(n)=18+4n$, with $n\in\mathbb Z_{\geq0}$.
2. $C(m)=25+0.08m$; $C(150)=37$ units.
3. $C(q)=180+7q$, $R(q)=19q$, and $P(q)=12q-180$, with $q\geq0$ and normally integer-valued.
4. $12q-180=0$ gives $q=15$, an admissible whole-item quantity.
5. $y=18-x$, so $A(x)=x(18-x)$ and $0<x<18$.
6. $L=72-2x$, $A(x)=x(72-2x)$, and $0<x<36$.
7. $500-12t=0$ gives $t=125/3$ days. Negative inventory predictions occur after that time and are outside a nonnegative-inventory interpretation.
8. $P(q)=6q-90$; break-even is $q=15$.
9. $A(x)=-(x-9)^2+81$; maximum 81 at $x=9$.
10. Vertex $x=2$ gives maximum 17; the minimum on the interval is $f(5)=-10$.
11. The vertex $x=7$ is outside the interval. The maximum is $g(5)=6$ and the minimum is $g(0)=-39$.
12. $h(x)=(x+2)^2+4$; minimum 4 at $x=-2$.
13. Decreasing on the interval; maximum $p(2)=3$, minimum $p(6)=-5$.
14. No maximum is attained; the supremum is 1.
15. $[7/2,8]$.
16. Feasibility checks constraints only; optimality requires comparing the objective over the entire feasible set.
17. Maximum 25 at integer $q=5$.
18. $Q(7)=Q(8)=19.75$; both integers maximize.
19. The exact change is $48/25=1.92$.
20. $\Delta y=-3(5/2)=-15/2$.
21. The cost change is $q\Delta v$, with all other parameters and $q$ held fixed.
22. The vertex is infeasible. For a continuous quadratic on a closed interval, check both endpoints and any vertex inside the interval; here only the endpoints are candidates.
23. Examples: every unit is sold at the same price, and all produced units can be sold. Demand limits or price discounts can invalidate the constant-price assumption.
24. Evaluate the objective at feasible integers near 6.4 (typically 6 and 7), as well as any integer endpoints, then compare the exact values.

## 17. Chapter summary

- An algebraic model identifies variables, parameters, relationships, constraints, and an objective.
- Units and contextual domains are part of the model, not optional annotations.
- Cost, revenue, and profit are distinct functions; break-even is not the same as maximum profit.
- Constraints define the feasible set. An objective is needed before the terms maximum and minimum have meaning.
- A quadratic on a finite closed interval can be optimized by comparing endpoints and any feasible vertex.
- For integer decisions, compare integer candidates near the vertex and the permitted endpoints.
- Open intervals may have suprema or infima that are not attained.
- Exact finite differences quantify sensitivity without calculus.
- A mathematically correct optimum must still be interpreted against assumptions, units, data quality, and practical limitations.

## References

- OpenStax, *Algebra and Trigonometry*, chapters on linear and quadratic functions, systems, and mathematical modeling.
- OpenStax, *Precalculus 2e*, sections on modeling with functions, systems of inequalities, and optimization contexts.
- The earlier chapters of this Math-Atlas Algebra volume, especially Chapters 05, 12, 16, and 19.

**End of volume:** Chapter 20 completes the planned Algebra curriculum map. The next phase is a full-volume editorial, mathematical, navigation, accessibility, and live-rendering review.
