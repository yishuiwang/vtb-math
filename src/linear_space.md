# 线性空间

线性空间（linear space）或称向量空间（vector space）是线性代数中研究的重要对象，是一种代数系统，这种对象是由解析几何中直观的向量几何抽象而来。线性空间中的元素被叫做向量，在公理化中定义的向量不仅局限于空间几何。

---
transition: slide-up
---

## 判断线性空间的三个条件



$\text{要判断给定的矩阵或向量集合是否构成线性空间，需要验证以下三个条件：}$

$1. \textbf{非空性}：\text{零矩阵是否属于该集合；}$

$2. \textbf{加法封闭性}：\text{集合中的任意两个矩阵的和仍在该集合中；}$

$3. \textbf{数乘封闭性}：\text{集合中的任意矩阵乘以数域 } P \text{ 中的任意标量后，结果矩阵仍在该集合中。}$

---

## 问题一

$\text{在 } n \text{ 维线性空间 } P^n \text{ 中，下列 } n \text{ 维向量的集合 } V\text{，是否构成 } P \text{ 上的线性空间}$
$$
\begin{align*}
&(1)\quad V=\{(a,b,a,b,\cdots,a,b)\mid a,b\in P\}\\
&(2)\quad V=\{(a_1,a_2,\cdots,a_n)\mid \sum_{i = 1}^{n}a_i = 1\}\\
&(3)\quad V=\{x = (\xi_1,\xi_2,\cdots,\xi_n)^T\mid Ax=\theta,A\in P^{n\times n}\}
\end{align*} 
$$


---
transition: slide-up
---

**(1)** $V = \{ (a,b,a,b,\cdots,a,b) \mid a,b \in P \}$。

零向量对应于$a = 0, b = 0$，即$(0,0,0,0,\cdots,0,0) \in V$。

取$u = (a_1,b_1,a_1,b_1,\cdots,a_1,b_1)$，$v = (a_2,b_2,a_2,b_2,\cdots,a_2,b_2)$，则
$$u + v = (a_1 + a_2, b_1 + b_2, a_1 + a_2, b_1 + b_2, \cdots, a_1 + a_2, b_1 + b_2) \in V$$
因为$a_1 + a_2, b_1 + b_2 \in P$。

对于标量$k \in P$，
$$k u = (k a_1, k b_1, k a_1, k b_1, \cdots, k a_1, k b_1) \in V$$
因为$k a_1, k b_1 \in P$。


因此，$V$满足线性空间的封闭性和包含零向量，所以$V$构成$P^n$的线性子空间。

---
transition: slide-up
---

**(2)** $V = \{ (a_1,a_2,\cdots,a_n) \mid \sum_{i = 1}^{n} a_i = 1 \}$。


首先，零向量$(0,0,\cdots,0)$的各分量之和为$0$，不等于$1$，因此零向量不在$V$中。

此外，取$u, v \in V$，则$\sum_{i=1}^n u_i = 1$，$\sum_{i=1}^n v_i = 1$。但是
$$\sum_{i=1}^n (u_i + v_i) = \sum_{i=1}^n u_i + \sum_{i=1}^n v_i = 1 + 1 = 2 \ne 1$$
因此，$u + v \notin V$。

同样地，对于标量$k \in P$，$\sum_{i=1}^n (k u_i) = k \sum_{i=1}^n u_i = k \cdot 1 \ne 1$（除非$k = 1$）。

因此，$V$不满足线性空间的封闭性，不构成线性空间。

---
transition: slide-up
---

**(3)** $V = \{ x = (\xi_1,\xi_2,\cdots,\xi_n)^T \mid Ax = \theta, A \in P^{n\times n} \}$。

集合$V$实际上是矩阵$A$的解齐次线性方程$Ax = 0$的解集，即$A$的零空间（核）。线性方程组的解空间构成线性空间，因为：

- 零向量满足$A 0 = 0$，因此$0 \in V$。
- 如果$x_1, x_2 \in V$，则$A(x_1 + x_2) = A x_1 + A x_2 = 0 + 0 = 0$，因此$x_1 + x_2 \in V$。
- 对于标量$k \in P$，$A(k x_1) = k A x_1 = k \cdot 0 = 0$，因此$k x_1 \in V$。

因此，$V$是$P^n$的线性子空间。

---
transition: slide-up
---


## 问题二

$\text{按通常矩阵的加法及数与矩阵的乘法，下列的数域 } P \text{ 上方阵集合是否构成 } P \text{ 上的线性空间：}$

$(1) \ \text{全体形如 } \begin{pmatrix} 0 & a \\ -a & b \end{pmatrix} \text{ 的二阶方阵的集合；}$

$(2) \ \text{全体 } n \text{ 阶对称（或反对称，上三角）矩阵的集合。}$

---
transition: slide-up
---

**(1) 全体形如 $\begin{pmatrix} 0 & a \\ -a & b \end{pmatrix}$ 的二阶方阵的集合**

令集合 $V = \left\{ \begin{pmatrix} 0 & a \\ -a & b \end{pmatrix} \middle| a, b \in P \right\}$。

**(a) 零矩阵是否属于 $V$：**

当 $a = 0, b = 0$ 时，  
$$
\begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix} \in V
$$  
因此，零矩阵属于 $V$。

---
transition: slide-up
---

**（b）加法封闭性：**

取任意 $M_1, M_2 \in V$，
$$  
M_1 = \begin{pmatrix} 0 & a_1 \\ -a_1 & b_1 \end{pmatrix}, \quad M_2 = \begin{pmatrix} 0 & a_2 \\ -a_2 & b_2 \end{pmatrix}。
$$
$M_1 + M_2 = \begin{pmatrix} 0 + 0 & a_1 + a_2 \\ -a_1 - a_2 & b_1 + b_2 \end{pmatrix} = \begin{pmatrix} 0 & a_1 + a_2 \\ -(a_1 + a_2) & b_1 + b_2 \end{pmatrix}。$

由于 $a_1 + a_2, b_1 + b_2 \in P$，所以 $M_1 + M_2 \in V$。因此，加法封闭性成立。


**（c）数乘封闭性：**

对任意 $k \in P$ 和 $M \in V$，  
$M = \begin{pmatrix} 0 & a \\ -a & b \end{pmatrix}, \quad k M = \begin{pmatrix} 0 & k a \\ -k a & k b \end{pmatrix}。$

由于 $k a, k b \in P$，所以 $k M \in V$。因此，数乘封闭性成立。

---
transition: slide-up
---


$(2) \ \text{全体 } n \text{ 阶对称（或反对称，上三角）矩阵的集合。}$

<table style="width: 100%; table-layout: fixed; border-collapse: collapse;">
<tr>
<td style="width: 50%; vertical-align: top; padding: 10px;">

1. **对称矩阵**  
   - **定义**：$A^T = A$  
   - **示例**：矩阵 $A = \begin{pmatrix}1 & 2 & 3 \\ 2 & 4 & 5 \\ 3 & 5 & 6\end{pmatrix}$

</td>
<td style="width: 50%; vertical-align: top; padding: 10px;">

2. **反对称矩阵**  
   - **定义**：$B^T = -B$  
   - **示例**：矩阵 $B = \begin{pmatrix}0 & -2 & 3 \\ 2 & 0 & -5 \\ -3 & 5 & 0\end{pmatrix}$

</td>
</tr>


<tr>
<td style="width: 100%; vertical-align: top; padding: 10px;">

3. **上三角矩阵**  
   - **定义**：当 $i > j$ 时，$a_{ij} = 0$，即矩阵的主对角线下方的元素全为零。  
   - **示例**：矩阵 $C = \begin{pmatrix}1 & 2 & 3 \\ 0 & 4 & 5 \\ 0 & 0 & 6\end{pmatrix}$。

</td>
<td style="width: 100%; vertical-align: top; padding: 10px;">

<!-- 可以在这里添加更多内容，或者保持为空 -->
&nbsp;

</td>
</tr>
</table>

