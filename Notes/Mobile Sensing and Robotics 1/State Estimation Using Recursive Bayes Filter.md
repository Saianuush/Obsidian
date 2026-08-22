## Autonomous Mobile System
# Recurring Terms in this Course [[Terms#Recurring Terms in this Course|#]]
- [[Terms#^State-Estimation|Support Estimation]]
- [[Terms#^localization|Localization]]
- [[Terms#^mapping|Mapping]]
- [[Terms#^SLAM|SLAM]]
- [[Terms#^navigation|Navigation]]
- [[Terms#^motion-planning|Motion Planning]]
- [[Terms#^robot-control|Robot Control]]

# State Estimation in Robotics
- ![[Pasted image 20260819223348.png]]
- State Estimation Result:
	- ![[Pasted image 20260819223437.png]]

# Probabilistic Approaches
- **Core Definition:** The foundation paradigm in robotics that uses probability theory to explicitly model and manage uncertainty in both robot motion (actuation) and environment perception (sensing).
- **Real-World vs Simulation:**
	- **Simulation:** Idealized environment operate deterministically under perfect assumptions.
	- **Reality:** Physical robots continuously encounter noise, calibration errors, and unpredictable environment disturbances.
	- **Example:** Commanding a robot to move at 30 km/h may result in actual speeds of 30,31 or 32 km/h due to wheel slip, friction and motor noise.
- **Belief Representation:** Instead of relying on single, deterministic values, system states are represented as probability distributions to reflect varying degrees of confidence.
- **Robustness & Fault Tolerance:** Probabilistic models allow robots to degrade gracefully during partial failures, preventing complete system stops and enabling principled decision-making despite noisy or incomplete data.
- ![[Pasted image 20260820201707.png]]
	- **Figure 1:** Just says robot is here in the 1D space
	- **Figure 2:** sags the graph of probability that the robot may be more likely here than their.

# Why Probability?
- Probability theory is the key tool robust state estimation and robotics.
- Probability theory allows to explicitly model uncertainties.

# Axioms of Probability Theory
Pr(A) denotes probability that proposition A is true.
![[Pasted image 20260820203022.png]]
	![[Pasted image 20260820203226.png]]
![[Pasted image 20260820203701.png]]

# Discrete Random Variables
- X denotes a [[Terms#^random-variable|random variable]].
- X can take on a countable number of values in {$x_1$,$x_2$, . . ., $x_n$}
- P(X=$x_i$) = P($x_i$) is the **probability** that the random variable X takes the value $x_i$.
- P() is called [[Terms#^probability-mass-function|probability mass function]].
# Continuous Random Variable
- X takes an values in the continuum.
- $p(X=x) = p(x)$ is a [[Terms#^probability-density-function|probability density function]].
- ![[Pasted image 20260821172546.png]]
# Probability Sums up to One

![[Pasted image 20260821172632.png]]

# Joint and Conditional Probability [[Law of Total Probability|#]]
- $P(X=x \text{ and }Y=y) = P(x,y)$
- if X and Y are **independent** then
	- $P(x,y) = P(x)P(y)$
- $P(x|y)$ is the probability of **X given Y**
	- $P(x,y) = P(x|y)P(y)$ 
	- $P(x|y) = \dfrac{P(x,y)}{P(y)}$
- if X and Y are **independent** then
	- $P(x|y) = P(x)$
# Law of Total Probability
| Discrete case                                 | Continuous case                                     |
| --------------------------------------------- | --------------------------------------------------- |
| $P(x) = \displaystyle\sum_{y}^{} P(x\|y)P(y)$ | $P(x) = \displaystyle \int_{}^{} p(x\|y)p(y) \, dy$ |
