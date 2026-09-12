# 📝 Vector Mathematics Exercise Sheet

Use the foundational definitions from the summary sheet to solve the following vector problems. Show all intermediate work.

---

## 🔹 Part 1: Given Vectors
For all questions below, use these four predefined vectors:
* $\mathbf{a} = \langle 2, -1, 4 \rangle$
* $\mathbf{b} = \langle 3,  2, 1 \rangle$
* $\mathbf{c} = \langle -1, 3, 0 \rangle$
* $\mathbf{d} = \langle 2, -3, -1 \rangle$

---

## 🔹 Part 2: Problems

### 1. Basic Vector Operations
Compute the resulting vector in component form:
* **(a)** $2\mathbf{a} + \mathbf{b}$
* **(b)** $\mathbf{b} - 3\mathbf{c}$

### 2. Magnitude & Unit Vectors
* **(a)** Calculate the exact magnitude $\|\mathbf{c}\|$ (leave your answer in radical form).
* **(b)** Find the unit vector $\mathbf{u}$ in the direction of $\mathbf{d}$.

### 3. The Dot Product & Orthogonality
* **(a)** Calculate the dot product $\mathbf{a} \cdot \mathbf{b}$.
* **(b)** Determine if the vectors $\mathbf{a}$ and $\mathbf{d}$ are **orthogonal (perpendicular)**. Prove your answer mathematically.

### 4. The Cross Product
* **(a)** Compute the cross product $\mathbf{c} \times \mathbf{b}$ using a $3 \times 3$ determinant grid layout.
* **(b)** Find the area of the parallelogram formed by the vectors $\mathbf{c}$ and $\mathbf{b}$.

---

## 🔹 Part 3: Answer Key & Step-by-Step Solutions

<details>
<summary><b>Click to expand full solutions</b></summary>

### Solution 1: Basic Operations
* **(a)** $2\mathbf{a} + \mathbf{b} = 2\langle 2, -1, 4 \rangle + \langle 3, 2, 1 \rangle = \langle 4, -2, 8 \rangle + \langle 3, 2, 1 \rangle = \mathbf{\langle 7, 0, 9 \rangle}$
* **(b)** $\mathbf{b} - 3\mathbf{c} = \langle 3, 2, 1 \rangle - 3\langle -1, 3, 0 \rangle = \langle 3, 2, 1 \rangle - \langle -3, 9, 0 \rangle = \mathbf{\langle 6, -7, 1 \rangle}$

### Solution 2: Magnitude & Unit Vectors
* **(a)** $\|\mathbf{c}\| = \sqrt{(-1)^2 + (3)^2 + (0)^2} = \sqrt{1 + 9 + 0} = \mathbf{\sqrt{10}}$
* **(b)** First, find the magnitude of $\mathbf{d}$:
  $$\|\mathbf{d}\| = \sqrt{2^2 + (-3)^2 + (-1)^2} = \sqrt{4 + 9 + 1} = \sqrt{14}$$
  Divide the components of $\mathbf{d}$ by its magnitude to get the unit vector:
  $$\mathbf{u} = \mathbf{\left\langle \frac{2}{\sqrt{14}}, \frac{-3}{\sqrt{14}}, \frac{-1}{\sqrt{14}} \right\rangle}$$

### Solution 3: Dot Product & Orthogonality
* **(a)** $\mathbf{a} \cdot \mathbf{b} = (2)(3) + (-1)(2) + (4)(1) = 6 - 2 + 4 = \mathbf{8}$
* **(b)** Check orthogonality by calculating $\mathbf{a} \cdot \mathbf{d}$:
  $$\mathbf{a} \cdot \mathbf{d} = (2)(2) + (-1)(-3) + (4)(-1) = 4 + 3 - 4 = 3$$
  Because $\mathbf{a} \cdot \mathbf{d} = 3 \neq 0$, the vectors are **not orthogonal**.

### Solution 4: Cross Product & Area
* **(a)** Set up the matrix with row physical separation for clean GitHub rendering:
  $$
  \mathbf{c} \times \mathbf{b} = 
  \begin{vmatrix} 
  \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 
  -1 & 3 & 0 \\ 
  3 & 2 & 1 
  \end{vmatrix}
  $$
  Expand along the top row:
  $$\mathbf{c} \times \mathbf{b} = \mathbf{i}\begin{vmatrix} 3 & 0 \\ 2 & 1 \end{vmatrix} - \mathbf{j}\begin{vmatrix} -1 & 0 \\ 3 & 1 \end{vmatrix} + \mathbf{k}\begin{vmatrix} -1 & 3 \\ 3 & 2 \end{vmatrix}$$
  $$\mathbf{c} \times \mathbf{b} = \mathbf{i}(3\cdot1 - 0\cdot2) - \mathbf{j}((-1)\cdot1 - 0\cdot3) + \mathbf{k}((-1)\cdot2 - 3\cdot3)$$
  $$\mathbf{c} \times \mathbf{b} = 3\mathbf{i} - (-1)\mathbf{j} + (-11)\mathbf{k} = \mathbf{\langle 3, 1, -11 \rangle}$$

* **(b)** The area of the parallelogram is the magnitude of the cross product vector:
  $$\text{Area} = \|\mathbf{c} \times \mathbf{b}\| = \sqrt{3^2 + 1^2 + (-11)^2} = \sqrt{9 + 1 + 121} = \mathbf{\sqrt{131}}$$

</details>
