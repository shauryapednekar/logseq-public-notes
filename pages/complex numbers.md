subject:: math
source:: [[3Blue1Brown]]

- Complex numbers are of the form $a + bi$, where $a$ is the real and $b$ is the *imaginary* component. The complex number plan has two dimensional "vectors" where the first dimension is the real number line, and the second dimension is orthogonal to the number line and has the property that a unit in the second dimension squared is equal to negative one on the real number line. Mathematically, $i$ is the unit of the second dimension, and it is defined to have the property that $i^2 = -1$
- Multiplying a complex number $z$ by $i$ rotates $z$ by 90 degrees.
	- Mathematically, $z \cdot i. =Rot90(z)$.
	- A visual way of thinking about this is that $i$ is the transformation that takes the number 1 to $i$ and the number $i$ to $-1$ on the complex number plane, which preserves magnitude while moving the points counter clockwise by 90 degrees.
- Multiplying one complex number by another gives a linear combination of the original complex number and its Rot90.
	- $$
	  z \cdot (c + di) = c \cdot z + d \cdot zi = c \cdot z + d \cdot Rot90(z)
	  $$
	- #confused Not sure I understand the visual intuition behind this.
- What does the complex number plane offer that the "regular" Cartesian/Euclidean plane does not?
	- The complex number plane has a strong intuitive notion of multiplication of two complex numbers, whereas