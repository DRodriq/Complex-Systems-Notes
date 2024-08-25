by [[Stephen Lynch]]
## Preface
### Contents Overview
#### Chapter 1: Review of Python
#### Chapter 2-12: Continous Dynamical Systems
- C2: Existence and Uniqueness
- C3: Phase Plane in 2D
- C4: Modeling Populations of Interacting Species, Domains of Stability
- C5: Limit Cycles, or Isolated Periodic Solutions
- C6: Hamiltonian, or Conservative, Systems and Stability
- C7: How Planar Systems Vary Depending Upon Parameters. Bifurcation, Bistability, Multistability, Normal Forms
- C8: Chaos - 3D Systems and Poincare Maps
- C9: Poincare First Return Maps
- C10: Local and Global Bifurcations
- C11: Main Results and Statement of David Hilbert's Sixteenth Problem
- C12: Introduction to Delay Differential Equations
#### Chapter 13-17: Discrete Dynamical Systems
- C13: General Introduction to Iteration and Linear Recurrence (Difference) Equations
- C14: Nonlinear Discrete Dynamical Systems: Bifurcations, Chaos, Intermittency, Lyapunov Exponents, Periodicity, Quasiperiodicity, and Universality
- C15: Complex Iterative Maps in the Argand Plane (Julia and Mandlebrot Sets)
- C16: Optics, Electromagnetic Waves, and Maxwell's Equations - Complex Iterative Equations are used to Model the Propogation of Light Waves through Nonlinear Optical Fibers
- C17: Fractal Dimension and Multifractal Theory
- C18: Image PRocessing, FFT
- C19: Chaos Control and Synchronization
- C20: Neural Networks
- C21: Binary Oscillator Computing
- C22: Courswork and Exam-Type Papers
#### Recommended Texts
[[Random Dynamical Systems in Finance (2013)]]
[[A First Course in Fuzzy Logic, Fuzzy Dynamical Systems, and Biomathematics - Theory and Applications (2016)]]
[[Infinite Dimensional Dynamical Systems (2013)]]
[[Stochastic and Infinite Dimensional Analysis]]
## Chapter 1: Python
- Libraries used: 
	- Turtle (graphics, drawing)
	- Symby (Diffeq)
	- matplotlib pyplot, animation
	- mpl_toolkits.mplot3d
	- numpy
## Chapter 2: Differential Equations
- Review basic methods for solving
- Apply theory to simple mathematical models
- Existence and uniqueness
### 2.1 Simple Differential Equations and Applications
- Single independent variable diff eq is called and ODE, two or more is a PDE
#### 2.1.1 Linear Differential Equations
$dx/dt + P(t)x = Q(t)$ (1)
Multiply an integrating factor, J(t) ==>
$J(dx/dt) + JPx = JQ$ (2)
Find J; $d/dt(Jx) = J(dx/dt) + x(dJ/dt)=JQ$ ==> Set $dJ/dt = JP$
...
#### 2.1.2 Separable Differential Equations
Consider $dx/dt = f(t,x)$
and consider the function can be factored into $f(t,x) = g(t)(h(x)$ 
If f can be factored in this way, it can be solved by the method of seperation of variables

### 2.2 Applications to Chemical Kinetics
### 2.3 Applications to Electric Circuits
It was long believed there were only three fundamental passive circuit elements. Professor [[Leon Chua]] is the father of nonlinear circuit theory with his memristor. 
Capacitance: $1/C=dv/dq$, Inductance: $L=d{\phi}/di$, Resistance: $R=dv/di$
Where C is capacitance, L is inductance, R is resistance, v voltage, i current, q charge, and ${\phi}$ is flux.
Chua discovered the missing relationship between charge and flux:
$M = d{\phi}/dq$, where M is memristance. 
Incredibly, natural memristors have been around for hundreds of millions
of years, and there are memristors in plants and early life forms. Chua [4]
shows that sodium and potassium ion channel memristors are the key to gen-
erating action potentials in the Hodgkin-Huxley equations (see Chapter 21)
and he explains some unresolved anomalies with the original equations. In
terms of neurobiology, the tutorial shows that synapses are locally passive
memristors, and that neurons act as locally active memristors. Chua also
shows that the circuits used to model the Josephson junction effect should
include memristor elements to explain the workings of these devices accu-
rately. The author and Borresen believe it is possible to make super fast
low power computers using Josephson junctions acting as neurons connected
together with memristors acting as axons and synapses. More details are
provided in Chapter 21.
### 2.4 [[Existence and Uniqueness]]
A function mapping from Real -> Real is said to satisfy Lipschitz condition in a domain D (subset) Real if there exists a constant, L, such that:
$||f(x_1)-f(x_2)|| <= L ||x_1-x_2||$, where $x_1, x_2$ belong to D. If the function, f, satisfies the Lipschitz Condition, then it is said to be Lipschitz continous. 
* Note that Lipschitz continuity in x implies continuity in x, but the converse is not true
#### Existence and Uniqueness Theorem:
Suppose f is continously Lipschitz; then for an initial point $x_0$ belonging to D, the autonomous differential equation $\dot{x}$ has a unique solution, say ${\phi_t}(x_0)$ that is defined on the maximal interval of existence.
In other words, if f is continously differentiable, then two distinct solutions cannot intersect in finite time...?
**Example 13** *Solve the following linear differential equations and state the
maximal interval of existence for each solution:
(a) ẋ = x, x(0) = 1;
(b) ẋ = x2 , x(0) = 1;
(c) ẋ = x 3 , x(0) = 0*
a. $x(t) = e^t$ which exists for all t 
b. $x(t) = 1/(1-t)$, not defined for t = 1
c. This is not continously differentiable
### Bibliography
[[Memristor-missing circuit element (Chua, 1971)]]
[[Hodgkin-Huxley and the edge of chaos (Chua, 2013)]]
[[Two centuries of memristors (Chua, 2012)]]
## Chapter 3: Planar Systems
- Introduce the theory of planar autonomous linear differential equations
- To extend the theory of linear systems to that of nonlinear systems
- Goals:
	- Find and classify critical points in the plane
	- Carry out simple linear transformations
	- Construct phase-plane diagrams using nullclines, vector fields, and eigenvectors
	- Apply theory to modeling problems
Phase plane portraits are constructed using Hartman's Theorem. 
### 3.1 Canonical Forms
Consider the general form:
$dx/dt = \dot{x} = a_{11}x+a_{12}y$  , $dy/dt = \dot{y} = a_{21}x+a_{22}y$
Recall the matrix form:
$\dot{x}=Ax$ where x is a vector  and A is the matrix of constants $a_{ij}$
**Definitions**
*D1:* Every solution, ${\phi}(t)=(x(t),y(t))$ can be represented as a curve on the plane called a trajectory, or orbit. The [[Existence and Uniqueness]] theorem guarantees that trajectories do not cross. Although there are infinite number of trajectories, the qualitative behavior can be determined given the appropriate initial conditions.
*D2:* The [[Phase Portrait]] is a two-dimensional figure showing how the qualitative behavior of the system is determined as x,y vary with t.
*D3:* The direction field or vector field gives the gradients dy/dx and direction vectors of the trajectories in the phase plane. The slope of the trajectories can be determined using the chain rule: $dy/dx = \dot{x}/\dot{y}$, and the direction of the vector field is given by $\dot{x}, \dot{y}$ at each point in the xy plane.
*D4:* The contour lines for which $dy/dx$ is a constant is called isoclines
*D5:* The contour lines for which $dy/dt =0, dx/dt=0$ are called nullclines
**Canonical Forms**
Using linear algebra, the phase portrait of any linear system of the matrix form above can be transformed into a so-called canonical form $\dot{y}=Jy$ by applying a transformation $x=Py$ where P is TBD and $J=P^{-1}AP$ is of one of the following forms:
![[J_forms.png]]
with ${\lambda_{1,2}}, {\alpha}, {\beta}, {\micro}$ are real constants. 
Matrix $J_1$ has two real distinct eigenvalues, $J_2$ has complex eigenvalues, $J_3, J_4$ have repeated eigenvalues. 
#### Nonsimple Canonical Forms
The linear system is nonsimple if the matrix A is singular (det(A)=0) and at least one eigenvalue is 0. The system has a critical points other than the origin.
**Example:** $\dot{x}=x, \dot{y}=0$
#### Simple Canonical Forms
If det(A) != 0, and the origin is the only critical point. Critical points may be classified by the type of eigenvalues.
#### 3.1 Real Distinct Eigenvalues
If a system is diagonalized to obtain $\dot{x}={\lambda_1x}, \dot{y}={\lambda_2y}$ then the solutions are $x(t)=C_1e^{\lambda_1t}$
and $y(t)=C_2e^{\lambda_2t}$ where C1, C2 are constants. The solution curves may be found by solving the diff eq given by: $dy/dx = \dot{y}/\dot{x} = {\lambda_2}y/{\lambda_1}x$
**Recall**:
*If eigenvalues are distinct, real, and positive, the critical point is unstable*
*If the eigenvalues are distinct, real, and negative, the critical point is stable*
*If one is positive and the other negative, the critical point is a saddle point*
#### 3.1.2 Complex Eigenvalues ${\lambda} = {\alpha}+- i{\beta}$
We convert to polar coordinates by: x=rcos(theta), y=rsin(theta)
**Recall** 
If ${\alpha}>0$, the critical point is called an unstable focus (spiral winding outward)
If ${\alpha}=0$, the critical point is called a center (orbit)
If ${\alpha}<0$, the critical point is called an stable focus (spiral inward)
#### 3.1.3 Repeated Real Eigenvalues
Consider if the canonical matrices are of the form J3 or J4
- If there are two linearly independent eigenvectors, the critical point is called a singular node
- If there is one linearly independent eigenvector, then the critical point is called a degenerate node
### 3.2 Eigenvectors Defining Stable and Unstable Manifolds
Straight line trajectories that remain on the axes forever and exhibit exponential growth or decay along it are determined by the eigenvectors of the Matrix A and are called manifolds.
If the trajectory moves towards the critical point as t->infinity, this is a stable manifold. Otherwise, it is an unstable manifold.
### 3.3 Phase Portraits of Linear Systems in the Plane
*Definition 7:* Two systems of first-order autonomous differential equations are said to be qualitatively, or topologically equivalent if there exists  an invertible mapping that maps one phase portrait onto the other while preserving the orientation of the trajectories.
### 3.4 Hartman's Theorem
**Recall** a transformation that centers a critical point to the origin. The linearized system is then of the form P(u,v) = Q(u,v) = 0 (u, v are stable points).
Recall the Jacobian matrix given by ...
*Definition 7:* A critical point is called hyperbolic if the real part of the eigenvalues of the Jacobian J(u,v) is nonzero. If the real part of either of the eigenvalues is equal to 0, the critical point is nonhyperbolic.
**Hartman's Theorem:** Suppose (u,v) is a hyperbolic critical/stable point of the system. Then there is a neighborhood of this point on which the phase portrait for the nonlinear system resembles that of the linearized system. 
Note: Stable and unstable manifolds of the nonlinear system will be tangent to the manifolds of the linearized system near the relevant critical point. 
### 3.5 Constructing Phase Plane Diagrams
The method for plotting phase portraits for nonlinear planar systems having hyperbolic critical points can be broken down into three steps:
- Locate all critical / stable points
- Linearize and classify according the Hartman's Theorem
- Determine the nullclines and use dy/dx to obtain slops of the trajectories
### Bibliography
[[Qualitative Theory of Planar Differential Systems (2006)]]
## Chapter 4: Interacting Species
- Apply the theory of planar systems to modeling interacting species
- Goals
	- Plot solution curves to modeling problems for planar systems
	- interepret results
### 4.1 Competing Species
Two species competing for a common food source model
**Example 1:** *Sketch possible phase plane diagrams for the following system*
$\dot{x} = x({\beta}-{\delta}x-{\gamma}y)$ 
$\dot{y}=y(b-dy-cx)$
Where ${\beta}, {\delta}, {\gamma}, a, b, c$ are all positive constants with x(t) and y(t) represent the two species population
${\beta}x-{\delta}x^{2}$ and $by-dy^2$ represent the usual logistic growth of one species (Verhulst's equation). Both species suffer from competition $-{\gamma}xy$ and $-cxy$ 
### 4.2 Predator-Prey Models
Consider a two-species predator-prey model in which one species preys on another. 
**Example 2:** *Sketch a phase portrait for the Lotka-Voltera Model*
$\dot{x} = x({\alpha}-cy)$, $\dot{y}=y({\gamma}x-{\delta})$
where all are constants and x(t), y(t) representing the scaled population of prey and predator.
### 4.3 Other Characteristics Affecting Interacting Species
Parasitic interactions. Age classes, diseases, environmental effects, enrichment of prey, harvesting and culling policies, pollution, refuge, seasonal effects, three or more species interactions. 
### Bibliography
[[Systems for Biological Modeling - An Introduction (2015)]]
[[Mathematical Models in Biology (2005)]]
[[Population Biology - Concepts and Models (2005)]]
[[Selective predation and productivity jointly drive complex behavior in host-parasite systems (Hall, Duffy, Caceres) (2005)]]
[[Hopf bifurcation analysis for a predator-prey system of Holling and Leslie type (Hsu, Hwang) (1999)]]
[[Predator-prey interaction coupled by parasitic infection - limit cycles and chaotic behavior (Lenbury, Rattanamongkonkul) (1999)]]
[[Mathematics in Population Biology (2003)]]
## Chapter 5: Limit Cycles
- Aims and Objectives:
	- Historical background
	- Define features of phase plane portraits
	- Introduce theory of planar limit cycles
	- Introduce perturbation methods
- Goals 
	- Prove existence and uniqueness of limit cycle
	- Prove certain systems have no limit cycles
	- Interpret limit cycle behavior in physical terms
	- Find approximate solutions for perturbed systems
Limit cycles, or isolated periodic solutions, are the most common form of solutions observed when modeling physical systems in the plane.
### 5.1 Historical Background
**Definition 1:** *A limit cycle is an isolated periodic solution*
Example 1
Rayleigh in 1877 derived the following differential equation relating to the oscillation of a violin string:
$\dot{\dot{x}} + {\epsilon}(1/3x^2-1)\dot{x}+x=0$ rewritten as a system of first-order autonomous differential equations in the plane
$\dot{x}=y$ 
$\dot{y}=-x-{\epsilon}(y^2/3-1)y$
More examples are given.
### 5.2 Existence and Uniqueness of Limit Cycle in the Plane
### 5.3 Nonexistence of Limit Cycles in the Plane
### 5.4 Perturbation Methods
### Bibliography
[[Nonlinear Analysis - Modelling and Control (2013)]]
[[Bifurcation Theory of Limit Cycles (2016)]]
[[Singular Perturbation in the Physical Sciences (2015)]]
[[Differential Equations and Dynamical Systems (2006)]]
## Chapter 6: Hamiltonian Systems, Lyapunov Functions, and Stability
Aims and Objectives
- To study [[Hamiltonian Systems]] systems in the plane
- To investigate stability using Lyapunov functions
On completion, goals
- Prove whether a system is Hamiltonian
- Sketch phase portraits of Hamiltonian systems
- Use Lyapunov functions to determine the stability of a critical point
- Distinguish between stability and asymptotic stability
### 6.1 Hamiltonian Systems in the Plane
**Definition 1:** 
A system of differential equations on $R^2$ is said to be Hamiltonian with one defree of freedom if it can be expressed in the form:
$dx/dt = \partial{H}/\partial{y}$
$dy/dt=-\partial{H}/\partial{x}$
Where $H(x,y)$ is a twice-continously differential function. The system is said to be conservative and there is no dissipation. The Hamiltonian is defined by 
$H(x,y) = K(x,y) + V(x,y)$
Where K is kinetic energy and V is the potential energy.
*Theorem 1 (Conservation of Energy): The total energy H(x,y) is a first integral and a constant of the motion*
**Definition 2:**
A criticial point of the system $\dot{x}=f(x)$, $x {\in} R^2$
at which the Jacobian matrix has no zero eigenvalues is called a nondegenerate critical point. Otherwise, it is called a degenerate critical point.
*Theorem 2: Any nondegenerate critical point of an analytic Hamiltonian System is either a saddle point or a center.*
**Definition 3:** *Homoclinic Orbit*
Suppose that $x_0$ is a critical point of the system. If ... I don't understand this COME BACK here
**Definition 4:** *Heteroclinic Orbit*
**Definition 5:** *Separatrix*
An orbit that divides the phase plane into two distinctly different types of qualitative behavior. The homoclinic and heteroclinic orbits are examples of seperatrix cycles.
### 6.2 Lyapunov Functions and Stability
Recall that the stability of hyberbolic critical points may be determined from the eigenvalues of the Jacobian matrix. The critical point is stable if the real part of all the eigenvalues is negative. If a critical point is nonhyberbolic, we may be able to determine stability using...

Imagine a system defined by the potential function 
### Bibliography
[[Nonlinear Dynamical Systems and Control - A Lyapunov-Based Approach (2008)]]
[[Hamiltonian Chaos and Fractional Dynamics (2008)]]
[[Differential Equations, Dynamical Systems, and an Introduction to Chaos (2003)]]
## Chapter 7: Bifurcation Theory
Aims and Objectives
- Introduce bifurcation theory of continous systems in the plane
- Introduce the notion of steady-state solution and investigate multi-state stability and bistability
- Introduce the theory of normal forms
Goals
- Describe how a phase portrait changes as a parameter changes
- Animate phase portraits and plot bifurcation diagrams
- Take transformations to obtain simple normal forms
- Interepret the bifurcation diagrams in terms of physical behavior
### 7.1 Bifurcation of Nonlinear Systems in the Plane
**Peixoto's Theorem in the Plane**
#### 7.1.1 A Saddle-Node Bifurcation
#### 7.1.1 A Transcritical Bifurcation
#### 7.1.3 A Pitchfork Bifurcation
#### 7.1.4 A Hopf Bifurcation
### 7.3 Normal Forms
### 7.3 Multistability and Bistability
### Bibliography
## Chapter 8: Three-Dimensional Autonomous Systems and Chaos
### 8.1 Linear Systems and Canonical Forms
### 8.2 Nonlinear Systems and Stability
### 8.3 The Rossler System and Chaos
#### 8.3.1 The Rossler Attractor
#### 8.3.2 Chaos
### 8.4 The Lorenz Equations, Chua's Circuit, and the Belousov-Zhabotinski Reaction
#### 8.4.1 The Lorenz Equation
#### 8.4.2 Chua's Circuit
#### 8.4.3 the Belousov-Zhabotinski Reaction
### Bibliography
[[A Concise Guide to Chaotic Electronic Circuits (2014)]]
[[Chaos and Nonlinear Dynamics - An Introduction for Scientists and Engineers (2000)]]
## Chapter 9: Poincare Maps and Nonautomous Systems in the Plane
## Chapter 10: Local and Global Bifurcations
## Chapter 11: The Second Part of Hilbert's Sixteenth Problem
## Chapter 12: Delay Differential Equations
## Chapter 13: Linear Discrete Dynamical Systems
## Chapter 14: Nonlinear Discrete Dynamical Systems
## Chapter 15: Complex Iterative Maps
## Chapter 16: Electromagnetic Waves and Optical Resonators
## Chapter 17: Fractals and Multifractals
## Chapter 18: Image Processing with Python
## Chapter 19: Chaos Control and Synchronization
## Chapter 20: Neural Networks
