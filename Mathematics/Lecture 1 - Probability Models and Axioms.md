**Text:** Introduction to Probability, 2nd Edition D.P. Bertsekas and J.N Tsitsiklis, Athena Scientific, 2008

---
# Lecture 1: Outline
- Probability as a mathematical framework for reasoning about uncertainity.
- Probabilistic models
	- Sample Space
	- Probability law
- Axioms of probability
- Simple examples
---
# Sample Space (Ω)
- "List" (set) of possible outcomes.
- List must be:
	- **Mutually exclusive:** Events cannot happen at the same time (if one occurs, the others cannot). ^mutually-exlusive
	- **Collectively Exhaustive:** The set of events covers all possible outcomes, ensuring at least one must occur. ^mutually-exclusive
- **Example:**
	- **Discrete Example:**
		- Two rolls of a tetrahedral die (4 faces)
		- Sample space vs sequential description
			- ![[Pasted image 20260820232153.png|750]]
	- **Continuous Example:**
		- $Ω = \{(x,y)|0<=x,y<=1\}$
		- ![[Pasted image 20260820232733.png|250]]

---
# Probability Axioms
- **Event:** a subset of the sample space.
- Probability is assigned to events.

- **Axioms:**
	1. **Nonnegativity:** $P(A)>=0$
	2. **Normalization:** $P(\Omega) = 1$
	3. **Additivity:** if $A\cap B = \varnothing$, then $P(A\cup B) = P(A)+P(B)$

- $\begin{align}P({s_{1},s_{2},\dots,s_{n}})&=P(\{s_{1}\})+\dots+P(\{s_{k}\}) \\  &=P(s_{1})+\dots+P(s_{k})\end{align}$

> $A\cap B = A \text{ and } B$
> $A\cup B = A\text{ or }B = P(A) + P(B)$ 

> **Proving $1\geq P()\geq 0$**
> ![[WhatsApp Image 2026-08-22 at 12.48.14 AM.jpeg|479]]

> ![[WhatsApp Image 2026-08-22 at 12.53.14 AM.jpeg|480]]

---
 ![[WhatsApp Image 2026-08-22 at 1.05.37 AM.jpeg]]

---
 