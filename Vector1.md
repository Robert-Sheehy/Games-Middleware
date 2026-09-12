# 📐 Vector Mathematics Reference Sheet

This summary sheet covers the essential foundations of vector mathematics, including operations, geometric interpretations, and key formulas.

---

## 🔹 1. Vector Basics & Notation

A vector represents a quantity with both **magnitude (length)** and **direction**. 

* **Component Form (2D):** $\mathbf{v} = \langle v_1, v_2 \rangle = v_1\mathbf{i} + v_2\mathbf{j}$
* **Component Form (3D):** $\mathbf{v} = \langle v_1, v_2, v_3 \rangle = v_1\mathbf{i} + v_2\mathbf{j} + v_3\mathbf{k}$

### Magnitude (Length)
The magnitude of a vector $\mathbf{v}$ is calculated using the Pythagorean theorem:
$$\|\mathbf{v}\| = \sqrt{v_1^2 + v_2^2 + v_3^2}$$

### Unit Vectors
A unit vector has a magnitude of exactly $1$. To find the unit vector $\mathbf{u}$ in the direction of $\mathbf{v}$:
$$\mathbf{u} = \frac{\mathbf{v}}{\|\mathbf{v}\|}$$

---

## 🔹 2. Basic Vector Operations

Given two vectors $\mathbf{a} = \langle a_1, a_2, a_3 \rangle$ and $\mathbf{b} = \langle b_1, b_2, b_3 \rangle$, and a scalar $c$:

* **Vector Addition:** $\mathbf{a} + \mathbf{b} = \langle a_1 + b_1, a_2 + b_2, a_3 + b_3 \rangle$
* **Vector Subtraction:** $\mathbf{a} - \mathbf{b} = \langle a_1 - b_1, a_2 - b_2, a_3 - b_3 \rangle$
* **Scalar Multiplication:** $c\mathbf{a} = \langle ca_1, ca_2, ca_3 \rangle$

---

## 🔹 3. The Dot Product (Scalar Product)

The dot product multiplies two vectors to produce a **scalar (a single number)**. It measures how much the vectors point in the same direction.

### Algebraic Definition
$$\mathbf{a} \cdot \mathbf{b} = a_1b_1 + a_2b_2 + a_3b_3$$

### Geometric Definition
$$\mathbf{a} \cdot \mathbf{b} = \|\mathbf{a}\| \|\mathbf{b}\| \cos(\theta)$$
*Where $\theta$ is the angle between the two vectors ($0 \le \theta \le \pi$).*

### Key Properties & Applications
* **Angle Between Vectors:** $\cos(\theta) = \frac{\mathbf{a} \cdot \mathbf{b}}{\|\mathbf{a}\| \|\mathbf{b}\|}$
* **Orthogonality (Perpendicularity):** Two vectors are orthogonal if and only if $\mathbf{a} \cdot \mathbf{b} = 0$.
* **Vector Projection:** The projection of $\mathbf{a}$ onto $\mathbf{b}$ is:
  $$\text{proj}_{\mathbf{b}}\mathbf{a} = \left( \frac{\mathbf{a} \cdot \mathbf{b}}{\|\mathbf{b}\|^2} \right) \mathbf{b}$$

---

## 🔹 4. The Cross Product (Vector Product)

*Note: The cross product is exclusively defined in **3D space**. It produces a **new vector** that is strictly perpendicular to both original vectors.*

### Algebraic Definition (Determinant Form)
$$
\mathbf{a} \times \mathbf{b} = 
\begin{vmatrix} 
\mathbf{i} & \mathbf{j} & \mathbf{k} \\ 
a_1 & a_2 & a_3 \\ 
b_1 & b_2 & b_3 
\end{vmatrix}
$$


Expanding the determinant gives:
$$\mathbf{a} \times \mathbf{b} = (a_2b_3 - a_3b_2)\mathbf{i} - (a_1b_3 - a_3b_1)\mathbf{j} + (a_1b_2 - a_2b_1)\mathbf{k}$$

### Geometric Definition (Magnitude)
$$\|\mathbf{a} \times \mathbf{b}\| = \|\mathbf{a}\| \|\mathbf{b}\| \sin(\theta)$$

### Key Properties & Applications
* **Direction:** Determined by the **Right-Hand Rule**.
* **Parallel Vectors:** Two vectors are parallel if and only if $\mathbf{a} \times \mathbf{b} = \mathbf{0}$.
* **Area of a Parallelogram:** The magnitude $\|\mathbf{a} \times \mathbf{b}\|$ equals the area of the parallelogram formed by $\mathbf{a}$ and $\mathbf{b}$.
* **Area of a Triangle:** Half of the parallelogram's area: $\text{Area} = \frac{1}{2}\|\mathbf{a} \times \mathbf{b}\|$.

---

## 🔹 5. Summary Cheat Sheet Table

| Operation | Syntax | Output Type | Primary Geometric Meaning |
| :--- | :--- | :--- | :--- |
| **Magnitude** | $\|\mathbf{v}\|$ | Scalar | Length of the vector |
| **Dot Product** | $\mathbf{a} \cdot \mathbf{b}$ | Scalar | Projection mapping / Check for perpendicularity ($0$) |
| **Cross Product** | $\mathbf{a} \times \mathbf{b}$ | Vector | Generates a perpendicular vector / Area calculation |
