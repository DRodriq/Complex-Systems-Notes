by [[Steven Strogatz]]
## Contents
### Overview
### Part I: One-Dimensional Flows
#### Chapter 2: Flows on the Line
##### Introduction
##### A Geometric Way of Thinking
##### Fixed Points and Stability
##### Population Growth
##### Linear Stability Analysis
##### Existence and Uniqueness
##### Impossbility of Oscillations
##### Potentials
##### Solving Equations on the Computer
##### [[Problem Set for Chapter 2 of Nonlinear Dynamics and Chaos (1994) - Flows on the Line]]

#### Chapter 3: Bifurcations
##### Introduction
##### Saddle-Node Bifurcations
##### Transcritical Bifurcation
##### Laser Threshold
See also: [[Hermann Haken]]: [[Laser Theory (1983)]] and [[Synergetics: An Introduction (1983)]]
##### Pitchfork Bifurcation
##### Overdamped Bead on a Rotating Hoop
##### Imperfect Bifurcations and Catastrophes
##### Insect Outbreak
#### Chapter 4: Flows on the Circle
##### Introduction
##### Examples and Definitions
##### Nonuniform Oscillator
##### Overdamped Pendulum
##### Fireflies
##### Superconducting Josephson Junctions
### Part II: Two-Dimensional Flows

#### Chapter 5: Linear Systems
#### Chapter 6: Phase Plane
#### Chapter 7: Limit Cycles
#### Chapter 8: Bifurcations Revisited
### Part III: Chaos
#### Chapter 9: Lorenz Equations
#### Chapter 10: One-Dimensional Maps
#### Chapter 11: Fractals
#### Chapter 12: Strange Attractors
### Answer Guide
[Some Solutions](file:///home/drodriq/Downloads/solution_manual_of_non_linear_dynamics.pdf)
### References
### See Also
[[Introduction to Applied Nonlinear Dynamics and Chaos (1990)]]
[[Differential Equations, Dynamical Systems, and an Introduction to Chaos (2003)]]
## Chapter 1: Overview
### History
Strogatz outlines a basic history of dynamics, starting with [[Isaac Newton]]'s solution for Kepler's Laws and moves on to [[Poincare]] and his analysis of the [[Three-Body Problem]]. Poincare developed a geometric approach that emphasized quantitative questions for the dynamics of a many-body system.
Nonlinear oscillators then make an appearance in physics and engineering - studied extensively by people like [[Balthazar van der Pol]], [[Aleksandr Andronov]], [[ML Cartwright]], [[JE Littlewood]], [[Norman Levinson]], and [[Stephen Smale]].
[[Poincare's Geometric Methods]] were extended to the understanding of classical mechanics by [[George David Birkhoff]], [[Andrey Kolmogorov]], [[Vladimir Arnold]], and [[Jurgen Moser]].
In 1963 [[Edward Norton Lorenz]] discovered chaotic motion on a strange attractor.
[[Mitchell Feigenbaum]] made some key discoveries of universal laws governing the transition from regular to chaotic behavior. 
[[Benoit Mandlebrot]] wprled pm fractals.
[[1980s]] - Widespread interest in chaos, fractals, oscillators, etc.
## Chapter 2: Flows on the Line
Introduces vector fields with the example $\dot{x}=sinx$. Where $\dot{x}=0$ we find fixed points Stable fixed points (attractors, or sinks) and unstable fixed points (repellers, or sources). Phase portraits are also introduced. 
## Chapter 3: Bifurcations
Qualitative change points depending on parameters are introduced. [[Bifurcations]]. We cover some common bifurcation types.
### 3.1 Saddle Node Bifurcation
$\dot{x}=r+x^2$
Recall $x^2$ is a simple parabola and r acts as an offset. When r<0, the parabola intersects the x axis at two points. When r = 0, the parabola is centered at the origin. When r > 0, the parabola never intersects the x axis.
Analyzing this further, we see for all cases $f'(x) = 2x$, and $\dot{x}=0$ for r, -r. 
$f'(r) > 0$ therefore r is an unstable point (grows indefinitely)
$f'(-r) < 0$ therefore -r is a stable point, perturbations will decay.
When r = 0, $f'(-r) = 0$ which is harder to analyze, but is a qualitative shift. Here we see an example of a saddle-node bifurcation at r=0.
### 3.2 Transcritical Bifurcation
$\dot{x}=rx-x^2$
This is an upside down parabola that shifts left or right depending on r, centered at the origin where r = 0. 
For r < 0, we see the right-hand side of the parabola intersects the origin (stable) and the negative x axis on the left-hand side (unstable). 
As we increase r, that left hand side will shift left until it hits the origin (negative, unstable). We say a bifurcation occurs at r = 0.
## Chapter 4: Flows on the Circle
We move from vector field on the line to a vector field and its phase space in ${\dot{\theta}}=f({\theta})$
# Part II: Two-Dimensional Flows
## Chapter 5: Linear Systems
We consider a two-dimensional linear system of the form
$\dot{x}=ax+by$
$\dot{y}=cx+dy$
where a,b,c,d are parameters. We then convert this to matrix form
$\dot{x}=Ax$ where x is the column vector $[x,y]$
**Definitions**
Consider the example:
$\dot{x} = ax$
$\dot{y} = -y$
=> $x(t)=x_0e^{at}$ , $y(t) = y_0e^{-t}$
We show the phase portraits for different values of a. In each case, y(t) decays exponentially. When a < 0, x(t) also decays exponentially. 
- For a< -1, Stable Node: x*=0
- For a = -1, Star / Symmetrical Node: special case where y(t)/x(t) = y0/x0, all trajectories are straight lines through the origin - the decay rates in the two directions are precisely equal
- $a=0, x(t)=x_0$ so there is a line of fixed points along the x-axis. 
- $a>0, x^*$ becomes unstable, due to exponential growth in the x direction. Most trajectories veer away towards infinity. The exception is for trajectories on the y-axis, which walk to the origin. Here $x^*$ is called a saddle point, and the y-axis is called the stable manifold of the saddle point $x^*$. The unstable manifold of this point is the x axis where x(t) -> inf as t->inf. 
**Stability Language**
### 5.2 Classification of Linear Systems
Recall finding the eigensolution of a matrix given by the characteristic equation:
$det(A-{\lambda}I) =0$, where I is the identity matrix.
If ${\lambda}_1, {\lambda}_2<0$ then both eigensolutions decay exponentially. The fixed point is a stable node
If ${\lambda}_1 < 0,{\lambda}_2>0$ or vice versa, the stable point is a saddle point. Its stable manifold is the line spanned by the eigenvector corresponding to the decaying eigensolution. 
If the eigenvalues are complex. the fixed point is either a center or a spiral, and a spiral is stable or unstable depending on the sign of the real component. 
## Chapter 6: Phase Plane
## 6.3 Fixed Points and Linearization
Consider the system 
$\dot{x}=f(x,y)$
$\dot{y}=g(x,y)$
and the fixed point $(x^*,y^*)$
... ... ... 
We consider the Jacobian at the fixed point. We can classify stability of fixed points coarsely as follows:
Robust Cases:
	- Repellers / Sources: Both eigenvalues have positive real components
	- Attractors / SInks: Both eigenvalues have negative real parts
	- Saddles - One eigenvalue is positive, the other negative
Marginal Cases:
	- Centers: Both eigenvalues are pure and imaginary
	- Higher-Order and non-isolated fixed points: at least one eigenvalue is 0
**Hyperbolic Fixed Points, Topological Equivalence, and Structural Stability**
If $Re({\lambda}) \not{=} 0$ for both eigenvalues, the fixed point is hyberbolic, sturdy, unaffected by small nonlinear terms.
