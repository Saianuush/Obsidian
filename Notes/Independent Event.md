An **Independent event** is an event whose occurrence is not influenced or affected by the occurrence of another event. Specifically, event B occurring gives zero additional information about whether event A will occur.

The core definition is written mathematically as:
$$P(A|B) = P(A)$$

---
# Derivation of the Multiplication Rule
The standard formula for joint probability stems from the definition of conditional probability:
$$P(A|B) = \dfrac{P(A\cap B)}{P(B)}$$
Substitute the condition for independence, $P(A|B) = P(A)$, into the equation:
$$P(A) = \dfrac{P(A\cap B)}{P(B)}$$
Multiply both sides by $P(B)$:
$$P(A\cap B) = P(A)P(B)$$(**Note:** The conditional form $P(A|B) = P(A)$ requires $P(B)>0$, whereas $P(A\cap B) = P(A)P(B)$ applies generally.)

---
# Summary of Equivalent Definition
Two events A and B are independent if and only if any of the following statements hold:
- **Conditional Form:** $P(A|B) = P(A)$
- **Joint Probability Form:** $P(A\cap B) = P(A)P(B)$
- **Symmetric Conditional Form:** $P(B|A) = P(B)$
(**Note:** If any of one is true all of this are true.)

---
# Example:

Imagine tossing a coin and rolling a die.

Let:
- **A** = coin shows Heads
- **B** = die shows 6
Before knowing anything about the die:
$$P(A)=\dfrac{1}{2}$$
Now, the die landed on 6.
Does that give you any information about the coin? - No
The coin still has:
$$P(A|B) = \dfrac{1}{2}$$
Therefore:
$$P(A|B)=P(A)$$
So A and B are independent.

