**Formula:**
$$\boxed{P(A|B,C)=\dfrac{P(B|A,C)P(A|C)}{P(B|C)}}$$
# Derivation using Standard definition
The standard definition of conditional probability is:
$$P(X|Y)=\dfrac{P(X,Y)}{P(Y)}$$
Let $X=A$ and $Y=(B,C)$:
$$P(A|B,C)=\dfrac{P(A,B,C)}{P(B,C)}$$
using the product rule on the numerator $P(A,B,C)=P(B|A,C)P(A,C)$ and denominator $P(B,C)=P(B|C)P(C)$:
$$P(A|B,C)=\dfrac{P(B|A,C)P(A|C)P(C)}{P(B|C)P(C)}$$
Canceling out $P(C)$ leaves:
$$P(A|B,C)=\dfrac{P(B|A,C)P(A|C)}{P(B|C)}$$
