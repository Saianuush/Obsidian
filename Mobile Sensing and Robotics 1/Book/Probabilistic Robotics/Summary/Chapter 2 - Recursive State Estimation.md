# 2.1: Introduction to State Estimation
## 1. What is State Estimation?
- **Definition:** The process of estimating quantities that are **not directly observable** from sensor data, but can be inferred.
- **The Core Challenges:**
	- Executing robotic task (e.g., navigation, obstacle avoidance) is simple if the exact world state (robot position, obstacle coordinates) is known.
	- However, these key variables are **not directly measurable.**
- **The Role of Sensors:** Robots must rely on sensors, which only carry **partial information** and are corrupted by **noise**.
## 2. The Probabilistic Approach
- **Belief Distributions:** Probabilistic state estimation algorithm compute probability distributions over possible world states rather than relying on single "best guess".
- **Goal:** Recover true state variables from noisy, partial sensor measurements.
## 3. Chapter 2 Road Map
- **Section 2.2:** Basic probabilistic concepts and notations used throughout the book.
- **Section 2.3:** Formal model of robot-environment interaction and key terminology.
- **Section 2.4:** **Bayes Filters** - the foundational recursive algorithm for state estimation.
- **Section 2.5:** Representation and computational issues in implementing Bayes filters.

