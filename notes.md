# Lecture 1

## DE

A DE is an equation for an unknown function, for which contains its derivatives (and may contain itself)

## ODE:

A ODE is a DE without partial derivative (the contrary being PDE).

## Linear ODE:

Say for unknown y(t), a linear ODE is in this form:

<y, y’’ ,y’’, y’’’, y’’’’, y’’’’ ….> ^T <a_1(t), a_2(t)..... > = g(t)

for which a_1(t), a_2(t).... are some KNOWN function of t.

Autonomous ODE definition: An ODE that does not explicitly contain an input variable.

y^{(k)} is a shorthand notation for kth derivative.

## Solution of ODE: 
a function that satisfies the ODE (well… okay definition i guess)

## Initial Value Problem: 

An ODE but with initial condition, which is the value of y(t) and its derivatives given for certain ts (independent var).

## Independent Variable:

in y(t), y is dependent, t is independent.

Lecture 2:
Integral as solution:
A special case for which the solution is “easily obtainable”. Looks like:

y’ = g(t)

We merely need to integrate g(t) to get y.

Separable Equation:

for equations in the form:

y’ = f(x)g(y)

we can solve it by:

y’/g(y) = f(x)

int y’/g(y) dx = int f(x) dx

for LHS use u sub: u = y(x), du = y’(x)dx

int 1/g(y) dy = int f(x) dx

hence we can integrate both sides then solve for i.

## I.V.P Interval of Existence/Validity:

If the resulting function is a piecewise function (more specifically separated by vertical asymptotes), and we have the initial condition. only include the piece that contains initial condition point, as the DE relationship is broken at discontinuity (hence DE not satisfied in the other part)

Reason: In real life we can only extrapolate our understanding of dependent variables through the DE (slope relationship) and initial condition. However at the big bang singularity we cannot tell what is beyond.

Therefore for DE it is actually defined that the solution needs to be C^1. 

## Lecture 3:

## Picard’s Theorem (Existence & Uniqueness)

for ODEs in the form:

y’ = f(t, y(t))

y(t0) = y0 (for known t0, y0)

then a solution defined in the range t0 - e, t0 + e exists & is unique (for some e) when:

f(x,y) is continous

partial f/ partial y (x,y) exists and is continuous near t0, y0 (note continuity implies boundedness)

Also, the instructor says it is difficult to actually predict the exact interval without solving ODE first. (guess slope field can help?). Although we can tell existence & uniqueness relatively easily.

## Slope Field

A slope field can be defined for ODE in the form:

y’ = f(t, y(t))

and then can be graphed out (by hand or MATLAB)

all solutions (for different initial conditions) are encoded on the slope field

optional (not in 215, but back in IB): isocline is a line in slope field for which every point in the line has the same slope


# Lecture 4
## Integrating Factor:

Integrating factor is a method that is applicable to all first order linear ODEs (instead of separable, which only applies to factorable ODE)

Integrating factor solves equation in this form:

y’ + P(x)y = Q(x)

### Derivation:
<img src="https://lh6.googleusercontent.com/kujR_LjvB2PIT3KvGIIlEI9Z1AWH9BjniRLTx_6f6CrPDZZLLH2mTq5cNcWnXjbFGqkgJETmHdcgrQcP9Ecz2MqyXqU_WdwPyfBD-pzi2qz2ztuEh6jag6qL_-QNSgR1JUBIKqSz=s1600" width="602" height="803" />
Basically the gist is to:

Brute Force Product Rule
Using separable to assist with finding the desired M(x) for brute forcing

## Lecture 5:

## Autonomous ODE (Review):

an autonomous ODE can be written in this form:

y’ = f(y)

## Critical Point

For y’ = f(y), if f(c) = 0 then c is called the critical point of the autonomous ODE. And, y(x) = c is a solution to the ODE.

It is also called equilibrium solution

### Proof:

y’ = f(y)

d/dx c = f(c) since we state y = c is a solution

0 = f(c)

0 = 0 (since by def of c, f(c) = 0)

hence QED

## Phase Line:

We can sketch y’ = f(y) in a 1D graph, for which y’ is the y axis and y is the x axis. That line is a phase line.

## Stability:

My rough notion: say if f(2)= 0 is a stable point for an autonomous ODE, then if we change 2 to 2.1 (choose the solution curve that contains y = 2.1, then it should look pretty close (converging back) to y = 2 at least in its neighborhood. 

I still have no clue about radius of convergence yet, but at least for some non-zero radius the two solutions will converge.

- Stable: both “side” converges to config of that point
- Un-stable: both “side” diverges from configs of that point
- Semi-stable: one side converges and one side doesn’t
**![](https://lh6.googleusercontent.com/Fl5GQruRx7RmyZaQw5d0UTQgU3HPhYotnAtXOZCKORa8BrL2wckPXEfvAv1_NHXeOc7QW9A1Cuwo1QjGJsaw60UYser2Cq0AbUzB1hb3KAhRo7YF6E50gZMqq5xRdjbA3Zs6UU1u=s1600)**
Example of stable point. 

When y decreases, the slope is positive. When y increases, the slope is negative. hence “converges” to that specific config in the phase space (the phase space is basically the graph itself, containing y’ as y axis and y as x axis).

Or, if we represent trend of increase of y (aka positive y’) with ->  and trend of decrease of y (aka negative y’) with <-, then:

Stable:

-> point <-

Unstable:

<- point ->

Semi Stable:

-> point ->
or:
<- point <-

Critical Points in Slope Field:

**![](https://lh3.googleusercontent.com/Suk8HEGP-4xFB_6OviGvSVpHlNyFs4GdKIopkBZXV0f85DTajJLDZlEiqN-2rouCgMqh9nYE8bMEdx8vF55crr6rTDzW2Zu8JJhiKOpEzntggKvKJJ3yNg_LHW063hlsGOY6yg4K=s1600)**

Critical Points is also reflected in the slope field.

# Lecture 7:

## Euler’s method:

for a first order ODE with initial value (in the form y’(t) = f(t,y)
we approximate y(t) at any given t with the iterative process:

y0, t0 = initial value:
t[i + 1] = t[i] + h
y[i + 1] = y[i] + hf(t[i] ,y[i])

The “global truncation error” E_m < O(h) (first order)

the smaller the h, the more accurate it gets, however the more steps it takes to approximate the desired y value.

(h is the step size)

euler’s method is basically repeated linear approximation.
Improved Euler’s method:

we maintain 3 arrays

y[]

y*[]

t[]

iterative process:

y[i + 1] = y[i] + h (R1 + R2)/2

t[i + 1] = t[i] + h

R1 = f(t[i], y[i])
R2 = f(t[i + 1], y*[i + 1])

y*[i + 1] = y*[i] + h * f(t[1], y[i])

basically we approximate the next point slope (*) and take the average between current point slope and next point slope (*) to get a more accurate next point.

The “global truncation error” E_m < O(h^2) (second order). However, we also perform twice as many operations as the non-optimized euler’s method.

## Runge–Kutta methods

**![](https://lh6.googleusercontent.com/bRIWzT1XHBkni3jF29D0kc79o143DEUcfez_gY0dbX-gVFJ6Y2GqwSxkCfWpBVpOL-R2aAbxy4TMHkmHB1TBXMARwYFv5m5tXb10fRSASdBoeUUsoPajjT_GURsXsGjXEYdr9gXJ=s1600)**

Basically choosing 4 points, compute their slope and take their weighted average to be used in the euler’s method… 

guess euler-like approximation is basically choosing the right slope. better slope choice yields better approximation.

Total truncation error: O(h^4) (well guess the more points used to compute the slope the more “order” it has…)

## Exact Equation:

Widely appearing in physics, we aim to investigate equations that is similar to potentials in physics.

It is in the form:

M(x,y) + N(x,y) y’ = 0

Can find F(x,y) such that partial F/partial X is M and partial F/partial Y is N.

## Condition for Exactness:

we can find F(x,y) that satisfied the above condition if and only if:

parital M/ parital Y = partial N / partial X
Solution:

Define Ψ(x,y) such that Ψx(x,y) = M(x,y) and Ψy(x,y) = N(x,y), then:

can rewrite equation to:
Ψx + Ψy * y’ = 0

d/dx Ψ(x,y) = 0 (multivariable chain rule)

Ψ(x,y)  = c

hence we can solve for Ψ(x,y) via integrating M(x,y) with respect to x and N(x,y) with respect to y to arrive at implicit solution Ψ(x,y)  = c, then if applicable we can substitute in IV and/or solve for y.

Reason for parital M/ parital Y = partial N / partial X

note Ψxy(x,y) = Ψyx(x,y) (not always true, but true for most Ψ)

Then:
(Ψx)y= (Ψy)x
My = Nx

# Lecture 8

## Integrating Factor (Exact equation).

For M(x,y) + N(x,y) y’ = 0

if the equation is not exact

we can find a integrating factor u(x,y) such that

 u(x,y) M(x,y) +  u(x,y) N(x,y) y’ = 0 is exact

Two paths:

1: Assume u(x,y) = u(x)

2: Assume u(x,y) = u(y)

then we can solve for u(x), u(y) as solution to diff equation.

Path 1:

partial / partial y  u(x) M(x,y)  = partial / partial x u(x)N(x,y) 

u My = u Nx + Ux N
ux = u (My - Nx) / N (separable, in the form of f(u) g(x) (and y is constant since u(x) only depend on x)

Path 2:

partial / partial y  u(y) M(x,y)  = partial / partial x u(y)N(x,y) 

uy M + u My = u Nx

uy = u (Nx - My) / M (again separable, in the form of u(y)g(y) (and x is constant since u(y) only depend on y.

## Second order ODE:

in the form y’’ + p(x) y’ + q(x) y = f(x)

## Homogenous ODE

For y’’ + p(x) y’ + q(x) y = f(x), if f(x) = 0, then the equation is homogeneous.

We claim that such ODE’s solution is a vector space with e^{rx}: r in C being the basis vectors. n-th order has n dimensions (n basis vectors).

# Lecture 12

## Hooke’s law & Simple Harmonic Motion:

F = -kx

Note F = ma

a = - k/m x

x’’ = -k/m x

denote w^2 = k/m, for which w is the “natural frequency” (we will see the meaning later), then:

x’’ = -w^2 x

x’’ + w^2 x = 0

lamdba^2 + w^2 = 0

lamdba += iw

x = c1 cos(wt) + c2sin(wt)
= A cos(wt - B) (thank you trig identities)

w is natural/angular frequency (angular displacement per unit time)
A is the amplitude (usually in meter)
B is the angular displacement (depending on IV of SHM) (other name is INITIAL phase)

# Lecture 14
General Procedure of Solving mechanical vibration problem

Solve for spring constant
List out ODE (note up = negative, down = positive), and IVs
Solve!
If sum of sine waves, use R-method:
	
## R-method:

Acos(t) + Bsin(t) = Ccos(t - w)

For which C = sqrt(A^2 + B^2)

and w = arctan2(B, A)

## Lecture 15
Non-homogeneous 2nd order diff equation

In the form of y’’ + ay’ + by = f(x)

Solution:

y(x) = y_general + y_particular

For which general solution facilitates from:

y’’ + ay’ + by = 0

And particular solution births form:

For particular solution, we memorize a set of f(x) and find the corresponding particular solution with undetermined coefficients.

(The table in Lecture 14/15 note, we need to know f(x) = P(x), P(x)e^{ax}, P(x)cos{bx} and P(x)sin{bx}.

We finally add both solutions together and solve for the undetermined coefficient.

Sum of particular solutons:

Say for y’’ + ay’ + by = f(x) for which f(x) is a sum of different f(x) in the table

then the particular solution is simply the sum of all of these

Example:

TODO

## Lecture 16

## Undamped Forced Oscillation:

Basically, when we are applying a periodic external force (sine wave) to a spring mass system without damping, we are doing forced oscillation.

The ODE corresponding to forced oscillation is:

$$
mx'' + kx = F(t)
$$

For which $F(t)$ is a sine wave (in course it is represented with 
$F_{0}cos(wt)$ for which $F_{0}$ represents the amplitude. (Note at $t = 0$, $F(t)$ has opposite direction compared to spring force and is exerting maximal force, we might need to offset t for certain question to satisfy the constraint.)

w represents external frequency (to be more specific $\frac{w}{2 \pi}$ represents frequency in hertz, $w$ is angular frequency)

w0 represents the angular frequency of complementary solution.
### Case 1: $w \neq w_{0}$ (beats)

$x(t) = x_{c}(t) + x_{p}(t)$, and $x_{c}(t)$ is transient (gradually wears off as time goes)

xp = 

### Case 2: $w = w_{0}$ (resonance)

## Damped Forced Oscillation

$$mx'' + cx' + kx = F_{0}cos(wt)$$

x(t) = xc(t) + xp(t), and xc(t) is transient (gradually wears off as time goes)

The specific/complementary solution is relatively easy to find. (via char equation). We denote w0 as the frequency of the complementary solution.

The particular solution is algebraic hell, for which i shall not try to derive

**![](https://lh6.googleusercontent.com/MslwuPXhR2iEDdZkwRTo3eoXWAIVv2Q4LSVuVoclWY8K61iLc6zUAeg5dTfl8QXj0CgxUH6loRdpQQ1psPUXY53VOHca_2-jdNbw_JvMfG4I6QwWhwAXMPUqS8JMdw5HOJ_uFwg1=s1600)**

“Practical” Resonance (for damped forced oscillation):

We can take the above expression for c, and compute c(w) (c with respect to external frequency)

With some algebra it can be shown $c’(w) = 0$ is analogous to $w = \sqrt{w_{0}^2 - 2p^2}$ or $w = 0$. For that $w$, the amplitude $c$ is maximized, hence “practical” resonance as complementary solution is transient (fade away over time).

And, if both conditions cannot be met, there’s no practical resonance.

## Laplace Transform

### Definition:

$$\mathcal{L}\{f\}(s) = \int_0^\infty f(t)e^{-st} \, dt$$

### Existence & Uniqueness:

Existence Condition: The absolute value of function f(t) has to be O(e^t)

Uniqueness Condition: 

Optional (Extended Research on Laplace, Fourier and Frequency Space):

Definition of frequency space:

In using the Laplace, Z-, or Fourier transforms, a signal is described by a complex function of frequency: the component of the signal at any given frequency is given by a complex number. The modulus of the number is the amplitude of that component, and the argument is the relative phase of the wave.

# Appendix

## Fourier Transform

To represent a function in the frequency space, we need to change the coordinate system of the function (from time-domain to frequency domain).

### What is domain (from the view of Linear Algebra)
In Linear Algebra, a function is a infinitely dimensional vector in an abstract vector space. To represent the function (as a vector), we need to choose a basis and find the scalars (weights for each basis vector as component).

For instance, $f$ in time domain would be:

$$
f \approx [f(0), f(0.0001), f(0,0002), f(0.0003)...]^T
$$

To get the exact expression, we simply need to reduce step size to
from $0.0001$ infinitesimally small. The above would be
scalars, or weights for each basis vector.

We can also represent each time in the form of basis vector, for example,

$$
t = 0.0001 \rightarrow \vec{t} \approx [0,1,0,0...]
$$

Under the same step size as the $f$ example shown above. Again, to get
the exact $\vec{t}$, the step size needs to be $0$. The only non-zero entry is
1 as basis needs to be orthonormal.

We can then also define $f(t)$. $f(t)$ is the dot product between $f$ and the basis vector corresponding to the value of $t$, therefore:

$$
	f(t) = \langle f, \vec{t} \rangle
$$

Taking the fact that $\vec{t}$'s components is are all $0$ except for the entry corresponding to $t$ (that being 1), we can expand the dot product
as infinite sum and write it out in integral form.

$$
f(t) = \int_{-\infty}^{\infty} f(x) \delta(t- x)dx
$$

For which $\delta(t- x)$ is the dirac delta function. In fact, the above
integral is called inner product, for which it is actually defined as dot product for functions.

### Frequency Domain in Linear Algebra

Similar to how we project $f$ on time domain $t$, we can also project $f$ on frequency domain. We merely need to find:

- Basis vectors
- Scalars

For the sake of simplicity, let's say that the frequency is $1$ Hertz. And, we wish to find the basis vector for it.

TODO: write down an example basis vector
