subject:: [[subject/math]]
sources:: [[3Blue1Brown]]
status:: active

- TODO Add notes on complex numbers to SRS.
  :LOGBOOK:
  CLOCK: [2024-08-03 Sat 13:19:24]--[2024-08-03 Sat 13:19:24] =>  00:00:00
  CLOCK: [2024-08-03 Sat 13:19:25]--[2024-08-03 Sat 13:19:25] =>  00:00:00
  :END:
- #+BEGIN_QUERY
  {:title "Identities"
   :query [
         :find (pull ?b [*])
         :in $ ?current-page
         :where
         [?p :block/name ?current-page]
         [?b :block/page ?p]
         [?t :block/name "math-identities"]
         [?b :block/refs ?t]
         ]
   :inputs [:current-page]}
  #+END_QUERY
- #+BEGIN_QUERY
  {:title "Identities"
   :query [
         :find (pull ?b [*])
         :in $ ?current-page
         :where
         [?p :block/name ?current-page]
         [?b :block/page ?p]
         [?t :block/name "foo"]
         [?b :block/refs ?t]
         ]
   :inputs [:current-page]}
  #+END_QUERY
-
- Complex numbers are of the form $a + bi$, where $a$ is the real and $b$ is the *imaginary* component. The complex number plane has two dimensional "vectors" where the first dimension is the real number line, and the second dimension is orthogonal to the number line and has the property that a unit in the second dimension squared is equal to negative one on the real number line. Mathematically, $i$ is the unit of the second dimension, and it is defined to have the property that $i^2 = -1$.
- Complex numbers are commonly used for transforms involving rotations.
- Multiplying a complex number $z$ by $i$ rotates $z$ by 90 degrees.
	- Mathematically, $z \cdot i. =Rot90(z)$.
	- A visual way of thinking about this is that $i$ is the transformation that takes the number 1 to $i$ and the number $i$ to $-1$ on the complex number plane, which preserves magnitude while moving the points counter clockwise by 90 degrees.
- Multiplying one complex number by another gives a linear combination of the original complex number and its Rot90.
	- $$
	  z \cdot (c + di) = c \cdot z + d \cdot zi = c \cdot z + d \cdot Rot90(z)
	  $$ #foo
	- #confused Not sure I understand the visual intuition behind this.
- Multiplication of complex numbers is rotating (and stretching/shrinking) one complex number by the other.
- When considering the complex numbers that lie on the unit circle, the real (i.e. horizontal) component is equal to $cos(\theta)$ and the imaginary (i.e. vertical) component is equal to $sin(\theta)$ where $\theta$ is the angle between the number line and the vector representation of the complex number.
- Notation: $cis(\theta) = cos(\theta) + i \cdot sin(\theta)$.
	- #confused I'm assuming this represents complex numbers that lie only on the unit circle?
- $cis(\alpha + \beta) = cis(\alpha) \cdot cis(\beta)$
	- Geometrically, this makes sense because the right side first takes the vector on the unit circle that is formed by $\alpha$, and then multiples (i.e. *rotates*) it by $\beta$ degrees, which is equivalent to simply taking the unit vector on the unit circle that is formed by the sum of both the angles.
- What is the [[fundamental theorem of algebra]]?
	- A polynomial of degree $n$ has $n$ solutions in the complex number plane. #superficial-understanding
- What does division represent for complex numbers?
	- Rotation and stretching in the opposite direction.
	-