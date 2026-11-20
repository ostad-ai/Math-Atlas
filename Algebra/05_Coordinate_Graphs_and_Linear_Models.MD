# Algebra 05 — Coordinate Graphs and Linear Models

## 1. Introduction

A coordinate graph connects algebraic relationships to geometric pictures. A point records two numerical quantities at once, and a straight line can represent a relationship with a constant rate of change. This chapter develops the coordinate and line tools needed to read, construct, and interpret linear models.

The chapter assumes the real-number and equation skills developed in Chapters 01–04. It uses the general language of functions from Foundations 03, but focuses on the special behavior of straight lines and linear relationships.

### Learning objectives

After this chapter, you should be able to:

- Plot and interpret ordered pairs in the Cartesian coordinate plane.
- Calculate and interpret slope as a constant rate of change.
- Distinguish a nonvertical line, which is the graph of a function of $x$, from a vertical line.
- Construct a line equation from a point and slope or from two distinct points.
- Move among slope-intercept, point-slope, and standard forms.
- Find and interpret horizontal and vertical intercepts.
- Recognize parallel and perpendicular lines, including horizontal and vertical cases.
- Build and assess a linear model from contextual information or data.
- Use exact rational arithmetic in Python for line calculations.

## 2. The Cartesian coordinate plane

The **Cartesian coordinate plane** consists of two perpendicular number lines:

- The horizontal axis is the $x$-axis.
- The vertical axis is the $y$-axis.
- Their intersection is the **origin**, $(0,0)$.

A point is represented by an ordered pair $(x,y)$. The first coordinate gives the horizontal position; the second gives the vertical position. The order matters: $(2,5)$ and $(5,2)$ are generally different points.

The axes divide the plane into four quadrants. Quadrant I has $x>0$ and $y>0$; Quadrant II has $x<0$ and $y>0$; Quadrant III has $x<0$ and $y<0$; Quadrant IV has $x>0$ and $y<0$. Points on either axis do not belong to a quadrant.

### Example 1 — Interpreting coordinates

The point $P=(-3,2)$ is three units left of the vertical axis and two units above the horizontal axis. It lies in Quadrant II.

The point $Q=(0,-4)$ lies on the $y$-axis, four units below the origin. It is not in any quadrant.

### 2.1 Scale and units

A graph must state what each axis measures and what one unit represents. Equal visual distances should represent equal numerical differences along the same axis. The scales on the two axes need not be identical, but they must be clear. In applied problems, label axes with both quantity and unit, for example, time (hours) and distance (kilometres).

A plotted point without axis labels or a stated scale may be mathematically located but contextually uninterpretable.

## 3. Relations, graphs, and functions

The **graph** of a relation between $x$ and $y$ is the set of all points $(x,y)$ whose coordinates satisfy the relation.

For a relation to define $y$ as a function of $x$, each admissible $x$ must correspond to exactly one $y$. On a graph, this is equivalent to the **vertical-line test**: every vertical line must intersect the graph at most once.

A nonvertical straight line passes the vertical-line test and can be written as $y=mx+b$. A vertical line such as $x=3$ does not pass the test and is not the graph of $y$ as a function of $x$. It is still a valid line and a valid relation in the plane.

This chapter uses function notation when a line is nonvertical and its input domain is stated. For a vertical line, the relation form $x=c$ is used instead.

## 4. Slope: steepness and rate of change

For a nonvertical line, the **slope** is the change in $y$ divided by the corresponding nonzero change in $x$:

$$
m=\frac{\text{change in }y}{\text{change in }x}=\frac{\Delta y}{\Delta x}.
$$

If two distinct points on the line are $(x_1,y_1)$ and $(x_2,y_2)$, with $x_1\ne x_2$, then

$$
m=\frac{y_2-y_1}{x_2-x_1}.
$$

The numerator is often called the **rise** and the denominator the **run**. The order of subtraction must match in numerator and denominator. Reversing both differences leaves the slope unchanged; reversing only one changes its sign incorrectly.

### Example 2 — Calculate a slope

Find the slope through $A=(1,2)$ and $B=(4,11)$:

$$
m=\frac{11-2}{4-1}=\frac{9}{3}=3.
$$

For every increase of one unit in $x$, $y$ increases by three units along this line.

### 4.1 Positive, negative, zero, and undefined slope

- **Positive slope:** the line rises from left to right.
- **Negative slope:** the line falls from left to right.
- **Zero slope:** the line is horizontal, with equation $y=c$.
- **Undefined slope:** the line is vertical, with equation $x=c$.

For a vertical line, two points have the same $x$-coordinate, so $x_2-x_1=0$. The slope formula would require division by zero. The slope is therefore undefined; it is not an infinite real number.

### Example 3 — Classify four lines

- $y=2x+1$ has positive slope $2$.
- $y=-\frac{1}{3}x+4$ has negative slope $-\frac13$.
- $y=5$ is horizontal and has slope $0$.
- $x=-2$ is vertical and has undefined slope.

### 4.2 Slope as a unit rate

If $x$ measures hours and $y$ measures kilometres, then the slope has units of kilometres per hour. The numerical slope is a rate, not just a visual measure of steepness.

If the horizontal and vertical axes use different physical units, a slope is interpreted in output-units per input-unit. Its apparent angle on the screen can change when the graph's scale changes, but its numerical value and units do not.

## 5. Constructing a line from information

### 5.1 A point and a slope: point-slope form

A nonvertical line with slope $m$ through $(x_1,y_1)$ has equation

$$
y-y_1=m(x-x_1).
$$

This is the **point-slope form**. It follows directly from the slope definition: the slope from the fixed point $(x_1,y_1)$ to any point $(x,y)$ on the line must equal $m$.

### Example 4 — Use point-slope form

Find the line with slope $-2$ through $(3,5)$:

$$
y-5=-2(x-3).
$$

Expanding gives $y-5=-2x+6$, so

$$
y=-2x+11.
$$

### 5.2 Two distinct points

If two distinct points have different $x$-coordinates, first calculate the slope and then use point-slope form. If the points have the same $x$-coordinate, they determine a vertical line instead.

Two identical points do **not** determine a unique line: infinitely many lines pass through one point. This is a data insufficiency, not a vertical-line case.

### Example 5 — Find a line through two points

Find the line through $(-2,5)$ and $(4,-1)$.

First calculate the slope:

$$
m=\frac{-1-5}{4-(-2)}=\frac{-6}{6}=-1.
$$

Use the first point:

$$
y-5=-(x+2).
$$

Therefore $y=-x+3$. Both given points satisfy the equation.

### Example 6 — Detect a vertical line

The points $(3,-2)$ and $(3,7)$ have the same $x$-coordinate. Every point on the line has $x=3$, so the equation is

$$
x=3.
$$

It has no slope-intercept form $y=mx+b$.

## 6. Common forms of a line equation

### 6.1 Slope-intercept form

For a nonvertical line,

$$
y=mx+b,
$$

where $m$ is the slope and $b$ is the $y$-intercept. Setting $x=0$ gives $y=b$, so the line crosses the vertical axis at $(0,b)$.

This form is useful when the slope and starting value are known or when a linear model is being interpreted as output = rate $\times$ input + initial value.

### 6.2 Point-slope form

$$
y-y_1=m(x-x_1).
$$

This form is convenient when one point and the slope are known. It also avoids calculating the $y$-intercept before writing an equation.

### 6.3 Standard form

A line can also be written as

$$
Ax+By=C,
$$

where $A$, $B$, and $C$ are constants and $A$ and $B$ are not both zero. Standard form is useful for integer coefficients, intercept calculations, and systems of equations.

The equation is not a unique representation: multiplying all three coefficients by the same nonzero number gives an equivalent equation. For example, $2x-3y=6$ and $-4x+6y=-12$ describe the same line.

If $B\ne0$, standard form can be rearranged into slope-intercept form:

$$
y=-\frac ABx+\frac CB.
$$

Thus its slope is $-A/B$. If $B=0$, the equation is vertical: $x=C/A$, where $A\ne0$.

### Example 7 — Convert to standard form

Convert $y=\frac23x-5$ to standard form. Multiply by 3:

$$
3y=2x-15.
$$

Rearrange:

$$
2x-3y=15.
$$

### 6.4 Horizontal and vertical lines

A horizontal line has equation $y=c$. It is the graph of the constant function $f(x)=c$ for all real $x$, unless the contextual domain is restricted.

A vertical line has equation $x=c$. It is not the graph of $y$ as a function of $x$, because the same input $x=c$ corresponds to multiple $y$-values.

## 7. Intercepts and graphing a line

The **$x$-intercept** is where a line meets the $x$-axis; there $y=0$. The **$y$-intercept** is where it meets the $y$-axis; there $x=0$.

For the standard-form line $Ax+By=C$:

- If $A\ne0$, the $x$-intercept is $(C/A,0)$.
- If $B\ne0$, the $y$-intercept is $(0,C/B)$.

These formulas have conditions because division by zero is undefined. A line coinciding with an axis has infinitely many points on that axis, so it does not have a single intercept there. For example, $y=0$ is the entire $x$-axis.

### Example 8 — Find both intercepts

For $2x+3y=12$:

- Set $y=0$: $2x=12$, so the $x$-intercept is $(6,0)$.
- Set $x=0$: $3y=12$, so the $y$-intercept is $(0,4)$.

Plot these two points and draw the unique line through them.

### Example 9 — A line through the origin

The line $y=-3x$ meets both axes at the origin. Its $x$- and $y$-intercepts are the same point $(0,0)$; they are not two different points.

### 7.1 A reliable graphing procedure

To graph a nonvertical line:

1. Identify its equation form and any domain restriction.
2. Plot two distinct points that satisfy the equation. Intercepts are convenient when they exist and are easy to calculate.
3. Draw the straight line through the points, extending it as appropriate for the domain.
4. Label the axes, scale, points, and any contextual units.
5. Check a third point or substitute the plotted points into the equation.

A graph based on only two points is exact only when both points are exact and the relationship is known to be a line. For measured data, a line may instead be an approximate model; that situation is treated later in this chapter.

## 8. Parallel and perpendicular lines

### 8.1 Parallel lines

Two distinct nonvertical lines are parallel exactly when they have the same slope. Their $y$-intercepts are different. Thus $y=m x+b_1$ and $y=m x+b_2$ are distinct parallel lines when $b_1\ne b_2$.

Two distinct vertical lines are also parallel. A vertical line is not parallel to a nonvertical line.

### Example 10 — A parallel line

Find the line parallel to $y=4x-6$ that passes through $(1,2)$. Parallel nonvertical lines have equal slopes, so $m=4$:

$$
y-2=4(x-1),
$$

hence $y=4x-2$.

### 8.2 Perpendicular lines

Two nonvertical lines with slopes $m_1$ and $m_2$ are perpendicular exactly when

$$
m_1m_2=-1.
$$

Equivalently, their slopes are negative reciprocals. The condition is not used when either line is vertical; a vertical line is perpendicular to a horizontal line, whose slope is zero.

The slope condition can be understood through direction vectors. A nonvertical line with slope $m$ has direction vector $(1,m)$. Two direction vectors are perpendicular when their dot product is zero:

$$
(1,m_1)\cdot(1,m_2)=1+m_1m_2=0.
$$

This gives $m_1m_2=-1$.

### Example 11 — A perpendicular line

Find the line perpendicular to $y=2x+1$ through $(4,0)$. The given slope is 2, so the required slope is $-1/2$:

$$
y-0=-\frac12(x-4),
$$

or $y=-\frac12x+2$.

### Example 12 — Perpendicular to a vertical line

A line perpendicular to $x=3$ is horizontal. The horizontal line through $(4,-7)$ is

$$
y=-7.
$$

## 9. Linear relationships and models

A **linear model** describes an output that changes at a constant rate with respect to an input. In function form it is

$$
y=mx+b,
$$

where:

- $x$ is the input quantity;
- $y$ is the predicted output quantity;
- $m$ is the rate of change, or slope;
- $b$ is the output when $x=0$, provided zero is in the model's meaningful domain.

The slope's units are output-units per input-unit. The intercept's units are output-units. A model should state the meaning and units of each variable and the range of inputs over which it is intended to apply.

### Example 13 — Distance at constant speed

A cyclist begins 4 km from a checkpoint and travels toward it at a constant speed of 12 km per hour. Let $t$ be elapsed hours and let $d$ be distance from the checkpoint in kilometres, with the sign convention that distance from the checkpoint decreases as the cyclist approaches it. Then

$$
d(t)=4-12t.
$$

The slope is $-12$ km/h, and the initial value is 4 km. The contextual model is meaningful for $0\leq t\leq1/3$ if the cyclist stops at the checkpoint. Extending the line to later times would require a new interpretation of signed position or continued travel beyond the checkpoint.

### Example 14 — A fixed charge plus a rate

A service charges 12 currency units as a fixed fee and 0.08 currency units per unit of usage. If $n$ is usage and $C$ is the total charge, then

$$
C(n)=0.08n+12.
$$

The slope 0.08 is the cost per usage unit; the intercept 12 is the fixed fee. If usage cannot be negative, the contextual domain is $n\geq0$.

### 9.1 Constructing a model from two observations

If two observations have distinct input values and the relationship is assumed to be linear, they determine exactly one line. Calculate the slope from the two data points, then use point-slope form or calculate the intercept.

### Example 15 — Build a model from two observations

A tank contains 5 litres at time 0 and 17 litres at time 4 minutes. Assuming a constant fill rate, the slope is

$$
m=\frac{17-5}{4-0}=3\text{ litres per minute}.
$$

Since the initial amount is 5 litres, the model is

$$
V(t)=3t+5.
$$

This model is valid only while the filling rate remains constant and the tank has sufficient capacity.

### 9.2 When more than two observations are given

If more than two measured points lie exactly on one nonvertical line, they share a common slope and intercept. Real measurements often do not lie exactly on one line because of measurement variation or because the underlying process is not perfectly linear.

In that case, a **trend line** may summarize the overall pattern. A common formal method is least-squares linear regression, which chooses the line minimizing the sum of squared vertical residuals. This chapter introduces residuals but does not develop the full regression procedure.

For an observation $(x_i,y_i)$ and a proposed model $\hat y=mx+b$, the **residual** is

$$
e_i=y_i-\hat y_i=y_i-(mx_i+b).
$$

A positive residual means the observation lies above the model line; a negative residual means it lies below. Residual size and pattern help assess whether a linear model is reasonable. Residuals do not by themselves prove causation or guarantee that extrapolation is reliable.

### Example 16 — Calculate a residual

A model predicts $\hat y=2x+3$. At $x=4$, it predicts $\hat y=11$. If the observed value is 13, then

$$
e=13-11=2.
$$

The observation is 2 output-units above the model prediction.

## 10. Interpolation, extrapolation, and model limitations

**Interpolation** estimates a value within the range of observed input values. **Extrapolation** estimates beyond that range. Extrapolation is generally more uncertain because the relationship may change outside the observed interval.

A linear model should be judged using:

- whether the context supports a roughly constant rate of change;
- whether the input domain is stated and appropriate;
- whether the units and intercept have meaningful interpretations;
- whether residuals show systematic curvature or another pattern;
- whether predictions stay within realistic constraints.

Correlation or a visually straight trend does not alone establish a causal relationship. A model is a simplified description of a context, not an explanation of every mechanism that produced the data.

## 11. Computational exploration with Python

The following standard-library program constructs the exact line through two rational-coordinate points. It returns a vertical-line description when the input coordinates have equal $x$-values. Two identical points are rejected because they do not determine a unique line.

Pass integers, strings such as `"1.25"`, or `Fraction` values for exact rational arithmetic. Avoid passing binary floating-point values when exact decimal meaning is intended.

```python
from fractions import Fraction


def as_point(point):
    """Convert a two-coordinate point to exact rational coordinates."""
    if len(point) != 2:
        raise ValueError("A point must contain exactly two coordinates.")
    try:
        return Fraction(point[0]), Fraction(point[1])
    except (TypeError, ValueError, ZeroDivisionError) as exc:
        raise ValueError("Coordinates must be integers or rational values.") from exc


def line_through(point_a, point_b):
    """Return an exact description of the unique line through two distinct points."""
    x1, y1 = as_point(point_a)
    x2, y2 = as_point(point_b)

    if (x1, y1) == (x2, y2):
        raise ValueError("Two identical points do not determine a unique line.")

    if x1 == x2:
        return {"kind": "vertical", "x": x1}

    slope = (y2 - y1) / (x2 - x1)
    intercept = y1 - slope * x1
    return {"kind": "nonvertical", "slope": slope, "intercept": intercept}


def evaluate_line(line, x_value):
    """Evaluate a nonvertical line at an exact rational x-value."""
    if line["kind"] == "vertical":
        raise ValueError("A vertical line is not a function y = f(x).")
    x_value = Fraction(x_value)
    return line["slope"] * x_value + line["intercept"]


line = line_through((1, 2), (3, 8))
assert line == {
    "kind": "nonvertical",
    "slope": Fraction(3, 1),
    "intercept": Fraction(-1, 1),
}
assert evaluate_line(line, 4) == 11

vertical = line_through((2, -1), (2, 5))
assert vertical == {"kind": "vertical", "x": Fraction(2, 1)}

try:
    line_through((1, 1), (1, 1))
except ValueError:
    pass
else:
    raise AssertionError("Identical points must be rejected.")

try:
    evaluate_line(vertical, 2)
except ValueError:
    pass
else:
    raise AssertionError("A vertical line cannot be evaluated as y=f(x).")

print("Exact line construction checks passed.")
```

### 11.1 What the program does and does not establish

The program calculates exact slopes and intercepts for rational input coordinates and distinguishes vertical lines from nonvertical lines. Its tests check selected cases and implementation behavior. They do not prove the slope formula or the general theorem that two points with different $x$-coordinates determine a unique nonvertical line. Those results follow from the algebraic definitions and the fact that a nonzero real number has a multiplicative inverse.

## 12. Common errors and how to avoid them

1. **Reversing only one difference in the slope formula.** Use the same point order in numerator and denominator.
2. **Calling a vertical slope infinite.** The slope is undefined because its denominator would be zero.
3. **Treating two identical points as enough to determine a line.** They leave infinitely many possible lines.
4. **Assuming every line is a function of $x$.** Vertical lines fail the vertical-line test.
5. **Using $b$ as the $x$-intercept in $y=mx+b$.** It is the $y$-intercept; set $y=0$ to find the $x$-intercept.
6. **Using the negative-reciprocal rule for a horizontal or vertical line.** Handle the horizontal-vertical pair separately.
7. **Forgetting units in a model.** Slope units are output per input; intercept units are output units.
8. **Extending a model beyond its meaningful domain.** State where the model is valid and be cautious with extrapolation.
9. **Treating a trend line as an exact law.** Measured data may only be approximately linear.
10. **Interpreting correlation as causation.** A line summarizing data does not by itself identify a causal mechanism.

## 13. Worked examples

### Example 17 — Find a line from two points and verify it

Find the line through $(0,-2)$ and $(4,0)$.

The slope is

$$
m=\frac{0-(-2)}{4-0}=\frac12.
$$

The point $(0,-2)$ gives the intercept immediately, so the equation is

$$
y=\frac12x-2.
$$

Check $(4,0)$: $\frac12(4)-2=0$. Both points satisfy the equation.

### Example 18 — Convert standard form and interpret the slope

For $3x+2y=8$, solve for $y$:

$$
2y=-3x+8,
\qquad y=-\frac32x+4.
$$

The slope is $-3/2$ and the $y$-intercept is $(0,4)$. The $x$-intercept is found by setting $y=0$: $3x=8$, so it is $(8/3,0)$.

### Example 19 — Compare two lines

Consider $L_1:y=\frac34x-2$ and $L_2:y=-\frac43x+5$. Their slope product is

$$
\frac34\left(-\frac43\right)=-1.
$$

They are perpendicular. Their slopes are not equal, so they are not parallel.

### Example 20 — Interpret a contextual domain

A small account starts with 40 units and increases by 6 units per week. The formula is $B(w)=40+6w$. If $w$ counts completed weeks, a suitable domain is $w\in\mathbb{N}$, with $\mathbb{N}=\{0,1,2,\ldots\}$ under Math-Atlas conventions. The formula can be evaluated at noninteger real inputs algebraically, but those inputs do not describe completed-week observations in this context.

## 14. Exercises

Unless otherwise stated, coordinates and variables are real. For contextual models, state reasonable domain restrictions and units.

### A. Coordinate plane and slope

1. State the quadrant or axis containing each point: $(4,3)$, $(-2,5)$, $(-3,-1)$, $(5,-4)$, $(0,6)$, and $(-2,0)$.
2. Find the slope through $(1,4)$ and $(3,10)$.
3. Find the slope through $(-2,5)$ and $(4,-1)$.
4. What is the equation of the line through $(5,-2)$ and $(5,7)$? Explain why its slope is undefined.
5. Do the points $(2,3)$ and $(2,3)$ determine a unique line? Explain.
6. A line rises 7 units while moving 4 units to the right. Find its slope and interpret its sign.

### B. Equations and intercepts

7. Find the equation of the line with slope $1/2$ through $(0,-2)$.
8. Find the equation of the line through $(1,2)$ and $(3,8)$ in slope-intercept form.
9. Find the line through $(-1,4)$ with slope $-3$ in point-slope and slope-intercept forms.
10. Convert $2x+3y=12$ to slope-intercept form and find both intercepts.
11. Find the intercepts of $5x-2y=20$.
12. Convert $y=-\frac25x+3$ to standard form with integer coefficients.
13. Write the equation of the horizontal line through $(4,-7)$ and the vertical line through the same point.

### C. Parallel and perpendicular lines

14. Find the line parallel to $y=4x-6$ through $(1,2)$.
15. Find the line perpendicular to $y=2x+1$ through $(4,0)$.
16. Give the equation of the line perpendicular to $x=-3$ through $(2,5)$.
17. Are $3x-2y=8$ and $6x-4y=1$ parallel, identical, or neither? Justify using slopes and intercepts.

### D. Linear models and interpretation

18. A car's distance from a starting point increases from 12 km to 72 km over 1.5 hours at a constant rate. Find the rate and write a distance model, assuming the initial time is $t=0$.
19. A phone plan costs 9 currency units per month plus 0.04 currency units per text message. Write a cost model and interpret its slope and intercept. State a suitable domain.
20. A water tank contains 8 litres at time 0 and 26 litres at time 6 minutes. Assuming a constant filling rate, find a linear model and state its slope units.
21. A model predicts $\hat y=3x-2$. At $x=5$ an observed value is 16. Find the residual and interpret its sign.
22. Explain the difference between interpolation and extrapolation. Why is extrapolation often more uncertain?
23. A data set has three points with distinct $x$-values, and the points are not collinear. Can one exact line pass through all three? What kind of model might summarize the trend?
24. A student says that two nonvertical lines with slopes 2 and $-1/2$ must intersect. Is the claim correct? Explain the role of intercepts.

## 15. Selected answers and solution outlines

1. Quadrant I; Quadrant II; Quadrant III; Quadrant IV; positive $y$-axis; negative $x$-axis.
2. $m=(10-4)/(3-1)=3$.
3. $m=(-1-5)/(4-(-2))=-1$.
4. $x=5$. The change in $x$ between the points is zero, so the slope formula would divide by zero.
5. No. Infinitely many lines pass through one point.
6. $m=7/4$, positive because $y$ increases as $x$ increases.
7. $y=\frac12x-2$.
8. $m=3$, so $y=3x-1$.
9. Point-slope: $y-4=-3(x+1)$; slope-intercept: $y=-3x+1$.
10. $y=-\frac23x+4$; intercepts $(6,0)$ and $(0,4)$.
11. $x$-intercept $(4,0)$; $y$-intercept $(0,-10)$.
12. $5y=-2x+15$, hence $2x+5y=15$.
13. Horizontal: $y=-7$; vertical: $x=4$.
14. $y=4x-2$.
15. $y=-\frac12x+2$.
16. $y=5$.
17. Both have slope $3/2$ but different $y$-intercepts ($-4$ and $-1/4$); they are distinct parallel lines.
18. The rate is $(72-12)/1.5=40$ km/h. The model is $d(t)=12+40t$ km for the relevant travel interval.
19. $C(n)=0.04n+9$. The slope is currency units per message; the intercept is the fixed monthly fee. A suitable domain is nonnegative integers if messages are counted individually.
20. Rate $(26-8)/6=3$ litres per minute; $V(t)=8+3t$ litres while the fill rate remains constant and capacity is not exceeded.
21. Predicted value is $3(5)-2=13$, so residual $16-13=3$, meaning the observation is 3 units above the prediction.
22. Interpolation is within the observed input range; extrapolation is outside it and depends on the relationship continuing beyond observed data.
23. No. Three distinct noncollinear points cannot all lie on one line; a trend line or another model may summarize the pattern.
24. Yes. Their slopes are different, so the lines are not parallel and intersect at exactly one point; the product $2(-1/2)=-1$ also shows they are perpendicular. The slopes establish the relationship, while the intercepts (or full equations) are needed to calculate the intersection point.

## 16. Chapter summary

- A point $(x,y)$ records horizontal and vertical coordinates in the Cartesian plane.
- The slope of a nonvertical line is $m=(y_2-y_1)/(x_2-x_1)$ for two points with different $x$-coordinates.
- Positive, negative, and zero slopes describe rising, falling, and horizontal lines; vertical lines have undefined slope.
- A point and slope determine a nonvertical line through point-slope form; two distinct points determine exactly one line.
- Slope-intercept form is $y=mx+b$; point-slope form is $y-y_1=m(x-x_1)$; standard form is $Ax+By=C$ with $A$ and $B$ not both zero.
- Intercepts are found by setting the other coordinate equal to zero, while checking for zero coefficients and axis-coincident lines.
- Distinct nonvertical parallel lines have equal slopes; perpendicular nonvertical lines have slope product $-1$. A horizontal line is perpendicular to a vertical line.
- A linear model has constant rate of change. Its slope and intercept require contextual meanings, units, and a valid input domain.
- Residuals measure observed minus predicted values. A trend line is not necessarily an exact law or evidence of causation.
- Interpolation stays within the observed input range; extrapolation extends beyond it and is usually less secure.

## 17. References and connections

- Math-Atlas, [**Foundations 03 — Relations and Functions**](../Foundations/03_Relations_and_Functions.MD): relations, function graphs, domains, and the vertical-line test.
- Math-Atlas, [**Foundations 04 — Number Systems and Mathematical Structures**](../Foundations/04_Number_Systems_and_Mathematical_Structures.MD): real-number properties used in slope and line calculations.
- Math-Atlas, [**Foundations 05 — Mathematical Proof Techniques**](../Foundations/05_Mathematical_Proof_Techniques.MD): reasoning behind formulas and geometric conditions.
- Math-Atlas, [**Foundations 07 — Mathematical Notation and Symbols**](../Foundations/07_Mathematical_Notation_and_Symbols.MD): notation and symbol conventions.
- Math-Atlas, [**Algebra 01 — Algebraic Language and Expressions**](01_Algebraic_Language_and_Expressions.MD): variables, expressions, and formula evaluation.
- Math-Atlas, [**Algebra 02 — Real-Number Properties and Algebraic Simplification**](02_Real_Number_Properties_and_Algebraic_Simplification.MD): exact rational arithmetic and ordered-field properties.
- Math-Atlas, [**Algebra 03 — Linear Equations and Literal Equations**](03_Linear_Equations_and_Literal_Equations.MD): equation transformations and rearranging formulas.
- Math-Atlas, [**Algebra 04 — Linear Inequalities and Absolute Value**](04_Linear_Inequalities_and_Absolute_Value.MD): intervals and absolute-value language.

**Next chapter:** Chapter 06 — Systems of Linear Equations.
