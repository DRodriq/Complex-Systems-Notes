## 2.2 Fixed Points and Stability
**Example 2.2.1:** *Find all fixed points for $\dot{x} = x^2 - 1$*
	*Solution:* To find a fixed point $x^*$, set $f(x^*)=0$ and solve for $x^*$ 
	$x^2+1=0$  
	==>  $x^*= \pm1$ 
	To determine stability of these fixed points, we plot $f(x)=x^2-1$. The flow is the right where the  $x^2-1 < 0$ and to the left where  $x^2-1 > 0$. 
	Another way is to take $f'(x) = 2x$ and see that $f'(1) = 2 > 0$ and $f'(-1) = -2 < 0$
	Recall that where $f'(x) > 0$ the fixed point is unstable (grows rapidly) and where $f'(x)<0$ the fixed point is stable (decays rapidly).
	
**Example 2.2.2:** *Consider an RC circuit with a voltage source $V_0$ and current I*
	*Solution:* Recall $-V_0 + RI + {\frac QC} =0$. Charge accumulates on the capacitor at rate $\dot{Q}=I$
	Hence $-V_0 + R\dot{Q}+{\frac QC} =0$
## 2.3 Population Growth
$\dot{N}=rN(1-{\frac NK})$
## 2.4 Linear Stability Analysis
**Example 2.4.1** *Using linear stability analysis, determine the stability of the fixed points for $\dot{x}=sinx$*
	*Solution* We know that $sin(x) =0$ for $x=0, k\pi$ and that $f'(x) = cos(x)$ which is positive for $k\pi$ when k is even, and -1 when k is odd. Therefore $x^*$ is stable for odd k and unstable for even k
**Example 2.4.2** *Classify the fixed points of the logistics equation $\dot{N}=rN(1-{\frac NK})$ using linear stability analysis, and find the characteristic time scale for each case.*
	*Solution:* $N^* = 0, K$ and $f'(N) = r-(2rn/k)$ ==> $f'(0) > 0$ and $f'(K) < 0$, therefore $N^*=0$ is unstable and $N*=K$ is stable. The characteristic timescale is $1/|f'(N^*)|=1/r$
 