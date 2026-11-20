# Algebra Conventions for Math-Atlas

This document supplements the repository-wide rules in `../Foundations/MATHEMATICAL_CONVENTIONS.MD`. It does not replace them. If a later chapter needs a special convention, it must state the convention locally and explain why it is needed.

## Domains and variables

- Unless stated otherwise, lowercase Latin letters such as $x$, $y$, and $t$ denote real variables in elementary algebra.
- A variable's domain must be stated whenever it affects admissible values, equivalence, or the solution set.
- Parameters are fixed quantities within a stated problem, even if their values are not specified. Distinguish parameters from variables when discussing a family of equations.
- Use $\mathbb{R}$ for the real numbers, $\mathbb{Z}$ for the integers, $\mathbb{Q}$ for the rationals, and $\mathbb{C}$ for the complex numbers, consistent with Foundations.

## Expressions, equations, and identities

- An **expression** denotes a value once its variables are assigned admissible values; it does not assert equality to another expression.
- An **equation** asserts that two expressions are equal and is solved for values satisfying the stated domain restrictions.
- An **identity** is an equality that holds for every admissible value of its variables.
- An **inequality** compares two quantities using an order relation.
- Use $\equiv$ only when its meaning is explicitly stated. Prefer “is an identity” in prose when there is risk of confusing identity with congruence.

## Equality-preserving transformations

- Adding the same quantity to both sides of an equation preserves its solution set.
- Multiplying both sides by a nonzero quantity preserves its solution set. If the multiplier may be zero, split cases or justify the operation.
- Dividing by an expression requires proving that the expression is nonzero on the solutions under consideration.
- Squaring both sides, taking even powers, or applying a non-injective function can introduce extraneous candidates. Check candidates in the original equation.
- Clearing denominators requires retaining all restrictions that made the original denominators nonzero.

## Fractions, powers, and radicals

- Write a fraction with explicit grouping when numerator or denominator contains more than one term: `\frac{a+b}{c+d}`.
- Use parentheses for negative bases when exponentiation is intended: $(-a)^2$ differs from $-a^2$.
- For real-valued even roots, the radicand must be nonnegative. For real-valued odd roots, negative radicands are allowed.
- For $a>0$ and rational $r=p/q$, Chapter 11 defines $a^r$ using the unique positive $q$th root after reducing $p/q$. General irrational real exponents require an exponential/logarithmic definition and are outside the radical rules of Chapter 11.
- For a rational exponent $p/q$, first reduce $p/q$ to lowest terms with $q>0$. For a negative real base, a real value exists under the convention in Chapter 11 only when the reduced denominator $q$ is odd; negative exponents also require a nonzero base.
- For zero as a base, positive rational exponents give zero, while zero and negative exponents are undefined under this volume's convention.
- The principal square root is nonnegative, so $\sqrt{x^2}=\lvert x\rvert$ for real $x$. Do not replace this with $x$ unless $x\geq0$ is known.
- The principal square root $\sqrt{x}$ is nonnegative for $x\geq0$; it is not a two-valued symbol.

## Rational expressions

- A rational expression $P(x)/Q(x)$ has the natural real domain $Q(x)\ne0$.
- Record restrictions from every original denominator before cancelling common factors. Cancellation simplifies a formula; it does not restore excluded inputs to the original domain.
- Dividing by a rational expression requires that the divisor be defined and nonzero; its numerator must therefore also be nonzero on the domain of the division.
- Clearing denominators in an equation is justified only on the domain where the original denominators are nonzero. Check every resulting candidate in the original equation.

## Rational functions

- A rational function is represented by a quotient $P(x)/Q(x)$ of real polynomials with $Q$ not the zero polynomial. Its natural real domain excludes every real zero of the original denominator.
- This volume uses a domain-sensitive real-function convention: cancellation simplifies the formula but does not restore any input excluded by the original denominator. Two formulas that agree on their common domain can still represent different real functions if their domains differ.
- After full cancellation, an excluded real input is a removable discontinuity (hole) when the reduced denominator is nonzero there. It is a vertical asymptote when the reduced denominator remains zero there; the reduced numerator is then nonzero.
- Find horizontal or polynomial asymptotes from the reduced numerator and denominator. If the numerator degree is lower, the horizontal asymptote is $y=0$; if the degrees are equal, it is the ratio of leading coefficients. If the numerator degree is higher, use polynomial division; the quotient is the polynomial asymptote.
- A real zero of a rational function must be a zero of the numerator that also belongs to the original domain. An excluded input is not an intercept, even when cancellation makes the reduced formula zero there.
- For rational inequalities, partition the real line at numerator zeros and denominator zeros. Include admissible numerator zeros only for non-strict inequalities; never include poles or holes. Do not multiply an inequality by a denominator of unknown sign.
- The companion the corresponding chapter implementation performs exact calculations over rational coefficients and classifies caller-supplied rational inputs. It does not automatically find every irrational real root or solve arbitrary rational inequalities.

## Functions and graphs

- The general language of domain, codomain, image, composition, and inverse functions is established in Foundations, Chapter 03.
- Algebra chapters focus on specific function families and their formulas, graphs, restrictions, and models.
- Do not assume a graph is a function unless it passes the vertical-line test or its defining relation establishes uniqueness of output for each input.

## Polynomials

- Unless stated otherwise, a polynomial in one variable in this volume has real coefficients and nonnegative integer exponents.
- The zero polynomial has no degree in this volume; degrees are stated for nonzero polynomials unless a text explicitly says otherwise.
- A polynomial expression is written in standard form only after like powers have been combined and zero coefficients removed.

## Quadratic equations and models

- A quadratic polynomial in one variable has the form $ax^2+bx+c$ with real coefficients and $a\ne0$. If $a=0$, classify the resulting expression as linear or constant rather than quadratic.
- The discriminant is $D=b^2-4ac$. Over the reals, $D>0$ gives two distinct real roots, $D=0$ gives one distinct repeated real root, and $D<0$ gives no real roots. This does not classify complex roots; Chapter 13 introduces them.
- The vertex of $f(x)=ax^2+bx+c$ is $(h,k)$ with $h=-b/(2a)$ and $k=-D/(4a)$. On the full real domain, it is a minimum when $a>0$ and a maximum when $a<0$.
- For a contextual quadratic model, state the feasible input domain and units. A vertex outside that domain is not an attainable optimum; compare endpoints when the domain is a closed interval.
- When solving a quadratic by isolating a square, include both real square-root branches when the right-hand side is positive. The principal square-root symbol itself is nonnegative.
- Exact roots containing irrational radicals should remain exact until an approximation is requested. Numerical approximations must state their precision or tolerance.

## Polynomial functions, zeros, and multiplicity

- Unless stated otherwise, a real polynomial function maps $\mathbb R$ to $\mathbb R$; the same polynomial may also be evaluated over $\mathbb C$ when solving for complex roots.
- A zero of a polynomial function is an input $r$ satisfying $P(r)=0$. It is a real-graph x-intercept only when $r$ is real.
- For a nonzero polynomial, the multiplicity of a root $r$ is the largest positive integer $m$ such that $(x-r)^m$ divides the polynomial over the stated coefficient field.
- For a real root of a real polynomial, odd multiplicity gives a local sign change and axis crossing; even multiplicity gives no local sign change and axis touching.
- A nonzero degree-$n$ polynomial has at most $n$ distinct roots over a field and exactly $n$ complex roots counted with multiplicity over $\mathbb C$, by the Fundamental Theorem of Algebra.
- The Rational Root Theorem applies to integer-coefficient polynomials and provides candidates only. Test each candidate using substitution, the Remainder Theorem, or synthetic division.
- The leading term controls polynomial end behavior. It does not determine the complete graph between the two ends.

## Complex numbers

- Chapter 13 introduces $\mathbb C=\{a+bi:a,b\in\mathbb R,\ i^2=-1\}$. Every complex number has a unique standard form $a+bi$.
- For $z=a+bi$, use $\mathrm{Re}(z)=a$ and $\mathrm{Im}(z)=b$; the imaginary part is the real coefficient of $i$, not the term $bi$.
- The conjugate is $\overline z=a-bi$, and the modulus is $\lvert z\rvert=\sqrt{a^2+b^2}$. Thus $z\overline z=\lvert z\rvert^2$.
- Division by $w=c+di$ is allowed only when $w\ne0$, equivalently $c^2+d^2>0$.
- Complex numbers are not ordered by an order compatible with the field operations. Use modulus for size and distance, not an inequality such as $z_1<z_2$.
- A polynomial with real coefficients has nonreal roots in conjugate pairs. For a real quadratic with negative discriminant $D$, its complex roots are $(-b\pm i\sqrt{-D})/(2a)$.
- Exact helper code in this volume represents only rational real and imaginary components; irrational components should remain in symbolic mathematical form unless an approximation is explicitly requested.

## Notation and rendering

- Use `$...$` for inline mathematics and `$$...$$` on separate lines for display mathematics.
- Avoid `\operatorname` in GitHub-facing Markdown where the renderer may fail; prefer constructions such as `\mathop{\text{...}}` when a named operator is required.
- In Markdown table cells, avoid a raw `|` as mathematical content. Use `\lvert x\rvert` for absolute value or move the formula outside the table.
- Escape literal dollar signs that are not math delimiters, or write currency in prose to avoid ambiguity.

## Computation

- State whether a result is exact or approximate.
- Use integer or rational arithmetic when exactness matters; use floating-point arithmetic only with a stated tolerance or approximation context.
- A computer algebra system can verify or explore an identity, but a general proof still requires mathematical reasoning.

## Exponential functions and models

- A real exponential function $f(x)=ab^x$ uses $b>0$ and $b\ne1$; for the standard positive-quantity model, $a>0$. A negative base does not define a real-valued function for every real input.
- The basic function $b^x$ has domain $\mathbb R$, range $(0,\infty)$, $y$-intercept $(0,1)$, and horizontal asymptote $y=0$.
- In a discrete model $A_n=A_0b^n$, $b$ is the multiplier per complete period. If the per-period relative rate is $r$, then $b=1+r$; a decrease by $d$ uses $b=1-d$. State the time unit of each rate.
- In a continuous model $A(t)=A_0e^{kt}$, the constant $k$ has units of inverse time. Positive $k$ gives growth; negative $k$ gives decay.
- Compound interest $A=P(1+r/m)^{mt}$ uses nominal annual rate $r$, compounding frequency $m$, and time $t$ in years. Distinguish the nominal rate from the effective annual rate, and state any convention for incomplete compounding periods.
- A real logarithm may be applied only to a positive argument. Before solving an exponential equation with logarithms, isolate the exponential expression and verify that its target value is positive. Full logarithmic laws are developed in Chapter 17.
- For exponential inequalities, $b^x$ is increasing when $b>1$ and decreasing when $0<b<1$; the latter reverses the order when exponents are compared.
- Exact rational arithmetic is preferred for discrete models with rational data. Continuous exponential values and logarithmic solutions are generally approximations and should state their precision or tolerance.


## Logarithms and logarithmic functions

- A real logarithm $\log_b x$ is defined exactly when $b>0$, $b\ne1$, and $x>0$. The argument must be positive; zero and negative arguments are outside the real logarithm's domain.
- The defining equivalence is $\log_bx=y$ if and only if $b^y=x$. For a fixed admissible base, the logarithm and exponential functions are inverses.
- The basic function $f(x)=\log_bx$ has domain $(0,\infty)$ and range $\mathbb R$. It is increasing when $b>1$ and decreasing when $0<b<1$.
- Product, quotient, and power laws require positive real arguments: $\log_b(MN)=\log_bM+\log_bN$, $\log_b(M/N)=\log_bM-\log_bN$, and $\log_b(M^r)=r\log_bM$ for $M,N>0$ and real $r$. Do not distribute logarithms over addition or subtraction.
- For real $x\ne0$, $\log_b(x^2)=2\log_b\lvert x\rvert$; the expression $2\log_bx$ is not defined for negative $x$.
- Change of base is $\log_bx=\ln x/\ln b=\log_{10}x/\log_{10}b$, with $x>0$, $b>0$, and $b\ne1$.
- In a logarithmic equation, state the positivity restrictions for every original argument before applying logarithm laws. Check all algebraic candidates in the original equation.
- Logarithmic inequalities preserve order for bases greater than $1$ and reverse order for bases between $0$ and $1$.
- the corresponding chapter implementation computes Decimal approximations at a requested precision and recognizes only bounded integer exponents for exact rational inputs; it is not a general symbolic logarithm solver.


## Sequences, series, and binomial expansion

- Unless a problem states otherwise, sequence indexing begins at $n=1$. State explicitly when an index begins at $n=0$ or another integer.
- A sequence lists terms; a series sums terms. Use $a_n$ for a term and $S_N=\sum_{n=1}^{N}a_n$ for the $N$th partial sum.
- An arithmetic sequence has constant difference $d$ and $a_n=a_1+(n-1)d$. A geometric sequence has recurrence $a_{n+1}=ra_n$ and, with first term $a_1$, $a_n=a_1r^{n-1}$.
- A ratio test for identifying a geometric pattern must not divide by a zero term. Prefer the recurrence definition when zero terms occur.
- The arithmetic-series sum is $S_N=N(a_1+a_N)/2$. The finite geometric-series formula $a_1(1-r^N)/(1-r)$ requires $r\ne1$; for $r=1$, use $S_N=Na_1$.
- A nonzero infinite geometric series converges exactly when $|r|<1$ and then sums to $a_1/(1-r)$. If its first term is zero, every term is zero and the series converges to zero for any finite ratio.
- Sigma notation uses integer bounds and a dummy index. Reindexing must change the summand and bounds consistently. A sum with no indices in its range is the empty sum, equal to zero.
- The finite Binomial Theorem $(a+b)^n=\sum_{k=0}^{n}\binom nk a^{n-k}b^k$ is stated for nonnegative integer $n$. Do not apply this finite expansion to negative or noninteger exponents without a separate theorem and convergence conditions.
- the corresponding chapter implementation provides exact arithmetic for selected arithmetic/geometric sequence and series operations and finite binomial coefficients with integer or `Fraction` inputs. It is not a general sequence recognizer, symbolic engine, or infinite-series convergence tester for arbitrary series.


## Nonlinear systems and inequalities in the plane

- A solution of a system of equations in two variables is an ordered pair satisfying every equation. The system's solution set is the intersection of the individual equation-solution sets.
- A nonlinear system may have no real intersections, one, or several. Do not infer the number of intersections from the word "system" alone; use the reduced equations and the geometry of the specific curves.
- Substitution is valid when it replaces a variable by an expression equal to it on the original system. Elimination may derive necessary conditions; recover all variables from an original equation and verify every candidate in the original system.
- Squaring an equation or making another non-reversible transformation can add candidates. Always check the original equations and their domain restrictions.
- When a system reduces to a quadratic equation $Ax^2+Bx+C=0$ with $A\ne0$, its discriminant classifies the real values of the reduced variable. A repeated root gives one distinct intersection point when the other coordinate is uniquely determined by a line; a positive nonsquare discriminant may give real irrational points.
- An inequality in two variables describes a region. The equality curve is its boundary; $\leq$ and $\geq$ include the boundary, while $<$ and $>$ exclude it.
- A system of inequalities means logical AND: its solution region is the intersection of all individual regions. A logical OR describes a union and is a different condition.
- For a quadratic inequality, a point test evaluates the defining polynomial at a point not on the boundary. For a boundary with several components, test each relevant connected region rather than assuming one test point determines every region.
- the corresponding chapter implementation classifies selected line-parabola and line-circle intersections over rational coefficients, and checks rational points against specified linear/quadratic inequalities exactly. It is not a general nonlinear solver, graphing tool, or arbitrary algebraic-number engine.


## Algebraic modeling and optimization

- Distinguish decision variables from parameters. Parameters are held fixed within one model unless a sensitivity analysis explicitly varies them.
- State units for variables, parameters, rates, and outputs. Every term added in an equation must have compatible units.
- A feasible set is the set satisfying every constraint. An objective function is a separate function to maximize or minimize; feasibility alone does not establish optimality.
- For an affine model on a finite closed interval, extrema occur at endpoints. For a quadratic on a finite closed interval, compare endpoints and any vertex lying in the interval. This rule does not automatically apply to open or unbounded intervals or to arbitrary functions.
- On an open interval an objective may have a supremum or infimum that is not attained. Use “maximum” or “minimum” only when the value is attained by a feasible input.
- If a decision variable must be an integer, a continuous optimum is only a guide. Compare feasible integer candidates, including endpoints and the nearest integers to a quadratic vertex.
- Sensitivity statements must identify what changes and what is held fixed. For affine and quadratic models, finite-difference formulas in Chapter 20 are exact.
- A mathematically optimal solution must be checked against the context, units, constraints, assumptions, and data range. Do not confuse model output with a guaranteed real-world outcome.
