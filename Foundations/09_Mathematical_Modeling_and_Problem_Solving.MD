# Foundations 09 — Mathematical Modeling and Problem Solving

## 1. Introduction

Mathematics provides tools for understanding, describing, and solving problems in the real world.

However, real-world problems are rarely presented as ready-made equations. They usually involve incomplete information, practical constraints, uncertainty, and assumptions.

Mathematical modeling (مدل‌سازی ریاضی) is the process of translating a real-world situation into mathematical language so that it can be analyzed and studied.

A mathematical model may consist of:

- Variables and parameters.
- Equations and inequalities.
- Functions and relationships.
- Constraints and assumptions.
- Probability distributions.
- Algorithms and computational procedures.

The purpose of a model is not necessarily to reproduce every detail of reality. It is to capture the aspects that matter for a particular question.

---

## 2. The Mathematical Modeling Process

A typical modeling process consists of the following stages.

### Stage 1: Understand the Problem

Identify:

- What needs to be predicted, explained, optimized, or measured.
- What information is available.
- What information is missing.
- What restrictions apply.

The problem should be stated clearly before mathematical expressions are introduced.

### Stage 2: Define Variables and Parameters

Choose symbols for the quantities involved.

For example, suppose we want to model the distance traveled by an object moving at constant speed.

Let:

- \(d\): distance.
- \(v\): constant speed.
- \(t\): elapsed time.

### Stage 3: State Assumptions

A model simplifies reality by making assumptions.

For the constant-speed example, we assume:

1. Speed remains constant.
2. Motion occurs along a straight path.
3. Time and distance are measured consistently.

Assumptions define the conditions under which the model is meaningful.

### Stage 4: Formulate the Mathematical Model

The relationship between distance, speed, and time is

\[
d=vt.
\]

This equation is the mathematical model.

### Stage 5: Solve or Analyze the Model

If an object moves at \(5\) meters per second for \(8\) seconds,

\[
d=5\times8=40.
\]

The predicted distance is 40 meters.

### Stage 6: Interpret the Result

The result must be interpreted in the original context.

A mathematical answer is not automatically a meaningful real-world answer. Units, assumptions, and practical limitations must be considered.

### Stage 7: Validate and Refine

Compare the model's predictions with observations or known results.

If the model performs poorly, reconsider:

- The assumptions.
- The selected variables.
- The mathematical relationships.
- The available data.
- The numerical methods.

The model may need to be revised.

---

## 3. Variables, Parameters, and Constraints

A mathematical model often contains three important types of quantities.

### 3.1 Decision Variables

Decision variables represent quantities that can be chosen or controlled.

For example, a company deciding how many units of two products to manufacture may use

\[
x=\text{number of units of product A}
\]

\[
y=\text{number of units of product B}.
\]

### 3.2 Parameters

Parameters represent known or assumed values that influence the model.

For example:

- Production cost per unit.
- Available working hours.
- Selling price.
- Maximum available resources.

### 3.3 Constraints

Constraints (محدودیت‌ها) describe conditions that possible solutions must satisfy.

For example,

\[
x\geq0,\qquad y\geq0
\]

means that negative production quantities are not allowed.

If production capacity is limited to 100 units,

\[
x+y\leq100.
\]

A complete mathematical model must distinguish between quantities that can change and quantities that are fixed.

---

## 4. Types of Mathematical Models

Mathematical models can be classified in several ways.

### 4.1 Deterministic Models

A deterministic model produces the same output whenever its inputs are the same.

For example,

\[
y=3x+2.
\]

For \(x=4\),

\[
y=14.
\]

There is no randomness in this relationship.

### 4.2 Stochastic Models

A stochastic model (مدل تصادفی) incorporates randomness or uncertainty.

For example, the number of customers arriving at a service station during a fixed time interval might be modeled using a probability distribution.

A Poisson model is one possible choice:

\[
P(X=k)=\frac{\lambda^k e^{-\lambda}}{k!},
\]

where:

- \(X\) is the number of arrivals.
- \(\lambda\) is the expected number of arrivals during the interval.
- \(k\) is a nonnegative integer.

The appropriateness of this model depends on assumptions about arrival behavior.

### 4.3 Static Models

A static model describes a system without explicitly representing its evolution over time.

Example:

\[
C=100+5q,
\]

where \(C\) is total cost and \(q\) is production quantity.

### 4.4 Dynamic Models

A dynamic model describes how a system changes over time.

For example,

\[
x_{t+1}=1.05x_t.
\]

This represents a quantity that increases by 5% per time step.

### 4.5 Continuous Models

Continuous models use variables that can take values from continuous domains, such as the real numbers.

Example:

\[
f(t)=10e^{-0.2t}.
\]

### 4.6 Discrete Models

Discrete models use countable or finite states.

Example:

\[
a_{n+1}=2a_n+1.
\]

This recurrence defines a sequence indexed by integers.

### 4.7 Linear and Nonlinear Models

A linear relationship in one variable has the form

\[
y=ax+b.
\]

A nonlinear relationship may contain powers, products of variables, exponentials, or other nonlinear expressions.

For example,

\[
y=x^2+3x+1
\]

is nonlinear in \(x\).

---

## 5. Formulating Equations from Real-World Statements

One of the most important modeling skills is translating words into mathematical expressions.

### Example 1: Fixed and Variable Cost

Suppose a production process has:

- Fixed cost: 200 units of currency.
- Variable cost: 15 units per product.

Let \(q\) be the number of products.

The total cost is

\[
C(q)=200+15q.
\]

For \(q=30\),

\[
C(30)=200+15(30)=650.
\]

### Example 2: Distance and Time

Suppose a vehicle moves at constant speed \(v\).

The distance after time \(t\) is

\[
d(t)=vt.
\]

If the vehicle starts at position \(d_0\), the model becomes

\[
d(t)=d_0+vt.
\]

### Example 3: Population Growth

Suppose a population grows by a constant percentage \(r\) per year.

A discrete model is

\[
P_{n+1}=(1+r)P_n.
\]

Starting from \(P_0\), the solution is

\[
P_n=P_0(1+r)^n.
\]

This model assumes the same proportional growth rate in every time period.

---

## 6. Optimization Models

Optimization (بهینه‌سازی) is the process of finding the best solution according to a specified objective.

A basic optimization model contains:

1. Decision variables.
2. An objective function.
3. Constraints.

### Example: Maximizing Production Value

Suppose a workshop produces two products.

Let:

\[
x=\text{units of product A}
\]

\[
y=\text{units of product B}.
\]

Assume the profit per unit is 30 for A and 20 for B.

The objective is

\[
\max Z=30x+20y.
\]

Suppose the resource constraints are

\[
2x+y\leq100,
\]

\[
x+2y\leq80,
\]

\[
x\geq0,\qquad y\geq0.
\]

This is a linear programming model.

### 6.1 Python Formulation

The model can be represented as data:

```python
objective = {
    "product_A": 30,
    "product_B": 20,
}

constraints = [
    {"A": 2, "B": 1, "limit": 100},
    {"A": 1, "B": 2, "limit": 80},
]
```

The mathematical model and its computational representation should remain consistent.

A later chapter in the Optimization branch will study systematic solution methods.

---

## 7. Mathematical Modeling with Functions

Functions provide a natural way to describe dependencies between quantities.

A function

\[
f:X\to Y
\]

maps an input from domain \(X\) to an output in codomain \(Y\).

### 7.1 Linear Model

\[
f(x)=ax+b.
\]

This model describes a constant rate of change.

### 7.2 Quadratic Model

\[
f(x)=ax^2+bx+c.
\]

Quadratic models can describe curved relationships, such as idealized projectile trajectories under simplified physical assumptions.

### 7.3 Exponential Model

\[
f(t)=Ae^{kt}.
\]

This model describes proportional continuous growth or decay.

### 7.4 Logarithmic Model

\[
f(x)=a\ln(x)+b,\qquad x>0.
\]

Logarithmic models appear in several areas, including information theory, scientific measurements, and statistical modeling.

The choice of function should be justified by the problem and available evidence.

---

## 8. Dimensional Analysis

Dimensional analysis (تحلیل ابعادی) checks whether mathematical equations are consistent with the physical dimensions of their quantities.

Common dimensions include:

- Length: \(L\).
- Time: \(T\).
- Mass: \(M\).
- Temperature: \(\Theta\).

For example, speed has dimension

\[
[v]=LT^{-1}.
\]

Distance has dimension

\[
[d]=L.
\]

Time has dimension

\[
[t]=T.
\]

In the equation

\[
d=vt,
\]

the right-hand side has dimension

\[
[v][t]=LT^{-1}\cdot T=L.
\]

This agrees with the dimension of distance.

Therefore, the equation is dimensionally consistent.

Dimensional consistency is necessary for a physically meaningful equation, although it does not prove that the equation correctly models the phenomenon.

### 8.1 Python Unit Check

```python
def distance(speed, time):
    return speed * time


speed_mps = 5
time_seconds = 8

distance_meters = distance(speed_mps, time_seconds)

print(distance_meters)  # 40
```

The numerical calculation alone does not enforce units. The programmer must ensure that speed is measured in meters per second and time in seconds.

---

## 9. Model Validation and Error

A model should be evaluated by comparing its predictions with observations.

Let:

- \(y_i\) be an observed value.
- \(\hat{y}_i\) be the model's predicted value.

The prediction error is

\[
e_i=y_i-\hat{y}_i.
\]

### 9.1 Absolute Error

\[
AE_i=|y_i-\hat{y}_i|.
\]

### 9.2 Squared Error

\[
SE_i=(y_i-\hat{y}_i)^2.
\]

### 9.3 Mean Absolute Error

For \(n\) observations,

\[
MAE=\frac1n\sum_{i=1}^{n}|y_i-\hat{y}_i|.
\]

### 9.4 Mean Squared Error

\[
MSE=\frac1n\sum_{i=1}^{n}(y_i-\hat{y}_i)^2.
\]

These metrics are common in predictive modeling.

The appropriate metric depends on the application and the consequences of different prediction errors.

### 9.5 Python Implementation

```python
def mean_absolute_error(actual, predicted):
    if len(actual) != len(predicted):
        raise ValueError("Input lengths must match")

    if not actual:
        raise ValueError("Inputs must not be empty")

    errors = [
        abs(a - p)
        for a, p in zip(actual, predicted)
    ]

    return sum(errors) / len(errors)


def mean_squared_error(actual, predicted):
    if len(actual) != len(predicted):
        raise ValueError("Input lengths must match")

    if not actual:
        raise ValueError("Inputs must not be empty")

    errors = [
        (a - p) ** 2
        for a, p in zip(actual, predicted)
    ]

    return sum(errors) / len(errors)


actual = [10, 20, 30, 40]
predicted = [12, 18, 29, 43]

print(mean_absolute_error(actual, predicted))
print(mean_squared_error(actual, predicted))
```

---

## 10. Numerical Models and Computational Approximation

Many mathematical problems cannot be solved conveniently using exact symbolic expressions.

Numerical methods approximate solutions using finite computational procedures.

### Example: Approximating a Root

Consider the equation

\[
x^2-2=0.
\]

Its positive solution is

\[
x=\sqrt2.
\]

Newton's method generates approximations using

\[
x_{n+1}
=
x_n-\frac{f(x_n)}{f'(x_n)}.
\]

For

\[
f(x)=x^2-2,
\]

we have

\[
f'(x)=2x.
\]

Therefore,

\[
x_{n+1}
=
\frac12\left(x_n+\frac2{x_n}\right).
\]

Python implementation:

```python
def newton_sqrt_2(initial=1.0, iterations=6):
    x = initial

    for _ in range(iterations):
        x = 0.5 * (x + 2 / x)

    return x


print(newton_sqrt_2())
```

This method illustrates how a mathematical model can be translated into an iterative computational procedure.

A full treatment of convergence, numerical stability, and error analysis belongs to Numerical Methods.

---

## 11. A Complete Modeling Example

### Problem: Estimating Monthly Electricity Cost

Suppose an electricity customer pays:

- A fixed monthly charge \(F\).
- A variable charge \(r\) per unit of energy consumed.

Let:

- \(E\) be monthly energy consumption.
- \(C\) be total monthly cost.

The model is

\[
C(E)=F+rE.
\]

Assume:

\[
F=12,\qquad r=0.25.
\]

For consumption of 160 units,

\[
C(160)=12+0.25(160)=52.
\]

### Python Implementation

```python
def electricity_cost(consumption, fixed_charge, rate):
    if consumption < 0:
        raise ValueError("Consumption cannot be negative")

    if fixed_charge < 0 or rate < 0:
        raise ValueError("Charges cannot be negative")

    return fixed_charge + rate * consumption


cost = electricity_cost(
    consumption=160,
    fixed_charge=12,
    rate=0.25
)

print(cost)  # 52.0
```

### Model Limitations

This model assumes:

- A constant rate per unit.
- No additional taxes or fees.
- No consumption tiers.
- No time-dependent pricing.

If actual billing rules contain these features, the model must be extended.

The example illustrates an important principle: a model is only as appropriate as its assumptions and scope.

---

## 12. Common Modeling Mistakes

1. **Undefined variables:** Symbols are introduced without specifying what they represent.
2. **Hidden assumptions:** Important simplifications are not stated.
3. **Incorrect units:** Quantities with incompatible dimensions are combined.
4. **Overcomplicated models:** Unnecessary details make a model difficult to analyze.
5. **Oversimplified models:** Important relationships are ignored.
6. **Confusing correlation with causation:** An observed association does not automatically establish a causal relationship.
7. **Ignoring uncertainty:** Predictions may be presented as exact when the inputs or model are uncertain.
8. **Overfitting:** A model may describe existing observations very well but perform poorly on new data.
9. **Ignoring validation:** Mathematical elegance does not guarantee real-world accuracy.
10. **Misinterpreting results:** A mathematically valid answer may violate practical constraints.

---

## 13. Exercises

### Exercise 1 — Formulating Models

Translate each situation into a mathematical model.

1. A taxi charges a fixed fee plus a constant amount per kilometer.
2. A savings account grows by a fixed percentage every year.
3. A factory has limited raw materials and produces two products.
4. A tank loses water at a constant rate.
5. A population changes by a fixed percentage each year.

### Exercise 2 — Variables and Constraints

A company produces two products, A and B.

Each unit of A requires 2 hours of labor, and each unit of B requires 3 hours.

The company has 120 labor hours available.

1. Define the decision variables.
2. Write the labor constraint.
3. Add nonnegativity constraints.
4. If profits are 40 and 50 units of currency, write the objective function.

### Exercise 3 — Dimensional Analysis

Determine whether the following equations are dimensionally consistent:

1. \(d=vt\)
2. \(v=at\)
3. \(d=v+t\)
4. \(A=lw\), where \(l\) and \(w\) are lengths.

### Exercise 4 — Model Validation

Given

\[
y=[10,20,30,40]
\]

and

\[
\hat y=[12,18,29,43],
\]

calculate:

1. The absolute errors.
2. The squared errors.
3. The MAE.
4. The MSE.

Verify your results using Python.

### Exercise 5 — Model Limitations

Consider the model

\[
P(t)=P_0(1+r)^t.
\]

Explain:

1. What each parameter represents.
2. What assumptions are required.
3. Why the model may become inaccurate over long periods.
4. How changing the growth rate over time might be represented.

### Exercise 6 — Independent Modeling Project

Choose a simple real-world problem and develop a mathematical model.

Your submission should contain:

1. Problem description.
2. Variables and parameters.
3. Assumptions.
4. Mathematical formulation.
5. Solution or computational implementation.
6. Interpretation.
7. Limitations and possible improvements.

---

## 14. References

1. Giordano, Fox, and Horton, *A First Course in Mathematical Modeling*. Cengage Learning.
2. Edward A. Bender, *An Introduction to Mathematical Modeling*. Dover Publications.
3. Mark M. Meerschaert, *Mathematical Modeling*. Academic Press.
4. Steven C. Chapra and Raymond P. Canale, *Numerical Methods for Engineers*. McGraw-Hill.
5. Sheldon M. Ross, *Introduction to Probability Models*. Academic Press.

---

## 15. Summary

Mathematical modeling connects abstract mathematical concepts to practical problems.

The central process is:

\[
\text{Real Problem}
\rightarrow
\text{Assumptions}
\rightarrow
\text{Mathematical Model}
\rightarrow
\text{Analysis}
\rightarrow
\text{Interpretation}
\rightarrow
\text{Validation}.
\]

A good mathematical model should be:

- Clearly defined.
- Mathematically consistent.
- Appropriate for its purpose.
- Computationally manageable when implemented.
- Validated against relevant evidence.
- Honest about its assumptions and limitations.

Mathematical modeling is a central skill in science, engineering, economics, statistics, optimization, and machine learning.