## 4. 有界线性算子

### 4.1 线性算子

**定义**：$$X,Y$$ 为 $$\mathbb{K}$$ 上的线性子空间，$$D(T)\subset X$$ 为线性子空间，$$T:D(T)\to Y$$ 为**线性算子**，若 $$\forall x,y\in D(T),\forall \lambda \in \mathbb{K}$$，都有
$$
T(x+y)=Tx+Ty,\quad T(\lambda x)=\lambda Tx \\
\iff T(\lambda x+\mu y) = \lambda Tx + \mu Ty.
$$
**定义**：零空间 $$N(T)=\text{ker}(T)=\{x\in D(T), Tx=0\}=T^{-1}(0),$$ 像空间 $$R(T)=\{Tx, x\in D(T)\}.$$

**命题**：$$N(T)$$ 为 $$D(T)$$ 的线性子空间，$$R(T)$$ 为 $$Y$$ 的线性子空间。

**命题**：$$T$$ 为单射 $$N(T)=\{0\}$$。

**命题**：$$M\subset D(T)$$ 为 $$n$$ 维线性子空间，则 $$\text{dim} T(M) \le n$$。

证明：略。

### 4.2 算子范数

**定义**：对于线性算子，若 $$\exists c\ge 0,\forall x\in D(T), \Vert Tx\Vert_Y \le c\Vert x\Vert_X$$，则称 $$T$$ 是**有界的**。使该式成立的最小 $$c$$ 称为 $$T$$ 的**范数**，等价于
$$
\Vert T\Vert = \sup_{x\in D(T),x\ne 0} \frac{\Vert Tx\Vert}{\Vert x\Vert} = \sup_{x\in D(T),\Vert x\Vert \le 1} \frac{\Vert Tx\Vert}{\Vert x\Vert} = \sup_{x\in D(T),\Vert x\Vert < 1} \frac{\Vert Tx\Vert}{\Vert x\Vert}
$$
***例子 1***：$$X=Y=C[0,1],(Tx)(t)=\int_0^t x(\tau)d\tau$$，则 $$\Vert T\Vert = 1, x(t)\equiv1$$ 时取到。

***例子 2***：$$X=C[-1,1],f(x)=\int_{-1}^0x(t)dt - \in_0^1x(t)dt,|f(x)|\le 2\Vert x\Vert_\infty$$，但是 $$2$$ 取不到。

***例子 3***：$$T:C^1[0,1]\to C[0,1],T(x)=x'$$，那么 $$T$$ 为线性**无界**算子。令 $$x_n(t)=t^n,t\in[0,1]$$，则 $$(Tx_n)(t)=nt^{n-1}.$$

***例子 4***：$$A=(a_{ij})_{n\times n},a_{ij}\in\mathbb{K},Tx=Ax.\Vert T\Vert=?$$

**定理**：$$X,Y$$ 为 $$\mathbb{K}$$ 上的赋范空间，假设 $$\text{dim}X=n<\infty$$，$$T:X\to Y$$ 是线性算子，那么 $$T$$ 一定是有界的。

证明：用基来表示 $$X$$ 中的元素，并利用性质 $$\Vert\lambda_1 e_1+\cdots+\lambda_n e_n\Vert \ge c(|\lambda_1|+\cdots+|\lambda_n|)$$ 即可得证。证毕。

**定理**：$$X,Y$$ 为 $$\mathbb{K}$$ 上的赋范空间，$$T:X\to Y$$ 是线性算子，那么以下命题等价

1. $$T$$ 有界
2. $$T$$ 处处连续
3. $$T$$ 在 $$X$$ 上某一点连续

**证明**：$$(1)\to(2),(2)\to(3)$$ 易证；

$$(2)\to(1)$$：由于 $$T$$ 连续，在 $$x=0$$ 点附近，存在 $$\delta>0, \forall x \in B(0,\delta)$$，有 $$\Vert Tx\Vert\le1$$，因而 $$\Vert Tx\Vert \le \frac{2}{\delta}\Vert x\Vert$$；

$$(3)\to(2)$$：由于 $$T$$ 为线性算子，那么只要在任一 $$x_0$$ 点处连续，经过平移可以得到 $$T$$ 在任意一点处都连续。

证毕。

**推论**：$$X,Y$$ 为 $$\mathbb{K}$$ 上的赋范空间，$$T:X\to Y$$ 线性有界，那么 $$N(T)$$ 为 $$X$$ 的闭集线性子空间。

用符号 $$B(X,Y)$$ 来表示 $$X\to Y$$ 的有界线性算子。

**定理**：假设 $$X$$ 为赋范空间，$$Y$$ 为 Banach 空间，那么 $$B(X,Y)$$ 为 Banach 空间。

证明：略。

> **小结**：本部分定义了线性算子，以及有界线性算子的范数。由于**有界线性算子等价于连续算子**，今后主要研究的也是有界线性算子。



## 5. 有界线性泛函

从赋范空间 $$X$$ 到 $$\mathbb{K}$$ 的线性算子称为 $$X$$ 上的**线性泛函**。

**定义**：$$(X,\Vert\cdot\Vert)$$，用 $$X'$$ 表示 $$X$$ 上所有有界线性泛函全体，称之为 $$X$$ 的**拓扑对偶空间**。

若 $$X$$ 上的一组基为 $$\{e_1,e_2,\cdots\}$$（有限维或者无限维均可），那么 $$f:X\to\mathbb{K}$$ 由 $$f(e_1),f(e_2),\cdots$$ 唯一确定。

**定义**：$$(X,Y)$$ 赋范空间，若存在线性算子 $$T:X\to Y$$，并且 $$\Vert Tx\Vert_Y = \Vert x\Vert_X,\forall x\in X$$，则称 $$X,Y$$ 为**等距同构**的，因此可以视 $$X,Y$$ 为同一空间。

**命题**：$$(\mathbb{K}^n,\Vert\cdot\Vert_2)' = (\mathbb{K}^n,\Vert\cdot\Vert_2)$$（此命题的含义为 $$(\mathbb{K}^n,\Vert\cdot\Vert_2)$$ 的对偶空间等价于 $$n$$ 维空间，也就是说每一个有界线性泛函都可以映射为 $$\mathbb{K}^n$$ 上的一个点/向量）

证明：略。

对于形如 $$(X,\Vert\cdot\Vert_1)' = (Y,\Vert\cdot\Vert_2)$$ 的命题，证明思路如下。

**证明**：要想证明两个空间等价，那么只需要找到一个线性映射  $$T:(X,\Vert\cdot\Vert_1)' \to (Y,\Vert\cdot\Vert_2)$$，使得映射前后在两个空间的范数相等。考虑对 $$\forall f\in (X,\Vert\cdot\Vert_1)'$$，取 $$f\mapsto (f(e_1),f(e_2),\cdots,f(e_n))$$，那么按照以下步骤证明：

1. 证明对于任意 $$\forall f\in (X,\Vert\cdot\Vert_1)'$$，的确有 $$(f(e_1),f(e_2),\cdots,f(e_n))\in Y$$，即映射的源空间和像空间的确是 $$X,Y$$；
2. 证明 $$T$$ 为单射（即证明若 $$Tf=Tg$$，那么有 $$f=g$$）；
3. 证明 $$T$$ 为满射，此时 $$T$$ 为双射（即证明 $$\forall \alpha \in Y$$，存在 $$f \in (X,\Vert\cdot\Vert_1)'$$ 使得 $$Tf=\alpha$$，一般需要构造线性算子 $$f$$）；
4. 证明 $$\Vert Tf\Vert = \Vert f\Vert$$。

证毕。

因此按照上面的方法，还可以证明如下几个命题。

- $$(\mathbb{K}^n,\Vert\cdot\Vert_p)' = (\mathbb{K}^n,\Vert\cdot\Vert_q),\frac{1}{p}+\frac{1}{q}=1$$
- $$(c_0, \Vert \cdot\Vert_\infty)'=(\ell^1,\Vert \cdot\Vert_1)$$
- $$(\ell^1,\Vert \cdot\Vert_1)'=(\ell^\infty,\Vert \cdot\Vert_\infty)$$
- $$(\ell^p,\Vert \cdot\Vert_p)'=(\ell^q,\Vert \cdot\Vert_q)$$

> **小结**：有界线性泛函可以映射到某个我们熟悉的空间，对于后面的处理很有用。