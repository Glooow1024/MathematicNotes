## 3. 有限维赋范空间

有限维赋范空间相比于一般的赋范空间有很多很好的性质，比如所有范数等价、有限维赋范空间都是 Banach 空间。

假设 $$X$$ 为 $$\mathbb{K}$$ 上的线性空间，并且存在两个范数 $$\Vert\cdot\Vert_1,\Vert\cdot\Vert_2$$，称二者等价，若
$$
\exists \alpha,\beta > 0,\forall x\in X,\quad \alpha\Vert x\Vert_1\le \Vert x\Vert_2\le \beta\Vert x\Vert_2
$$
此时 $$(X,\Vert\cdot\Vert_1),(X,\Vert\cdot\Vert_2)$$ 有：

- 相同的收敛列、柯西列；
- 相同的开集、闭集、闭包、内部；
- $$(X,\Vert\cdot\Vert_1)$$ Banach $$\iff (X,\Vert\cdot\Vert_2)$$ Banach；

> **引理**：$$(X,\Vert\cdot\Vert)$$，$$Y\subset X$$ 为有限维线性子空间，设 $$e_1,...,e_n$$ 为 $$Y$$ 的一组基，则 $$\exists c > 0,\forall \lambda_1,...,\lambda_n \in \mathbb{K}$$，有
> $$
> c(|\lambda_1|+\cdots+|\lambda_n|) \le \Vert\lambda_1 e_1+\cdots+\lambda_n e_n\Vert \le \max_i\Vert e_i\Vert (|\lambda_1|+\cdots+|\lambda_n|)
> $$
> 证明：需要用到 Bolzano-Weierstrass 定理，即**有界列存在收敛子列**。反证法，证明略。
>
> **定理**：若 $$\text{dim}X<\infty$$，则 $$X$$ 上的**范数互相等价**，且均为 Banach 空间。
>
> 证明：只需要证明所有范数与 $$\Vert\cdot\Vert_1$$ 范数等价，且 $$(X,\Vert\cdot\Vert_1)$$ 构成 Banach 空间。

**推论**：$$(X,\Vert\cdot\Vert)$$，若 $$Y\subset X$$ 为有限维线性子空间，则 $$Y$$ 为闭集。

有限维赋范空间除了这个良好的性质（一定是 Bananch 空间）之外，还有其他的好性质。下面引入紧集的概念。

**定义**：$$(X,d)$$，$$M\subset X$$ 为紧集，若 $$\forall x_n\in M,\exists n_k\uparrow \infty,\exists x\in M, x_{n_k}\to x(k\to \infty).$$

实际上，紧集的概念跟完备性的概念有点像，前者是任意序列一定存在收敛子列，后者说明柯西列一定是收敛列。他们都跟序列的收敛性有关，后面也可以看到，他们都跟闭集有一定的关系。

实际上，紧集一定是有界闭集，但是闭集不一定是紧集。不过对于有限维赋范空间来说，二者等价，后面会有定理专门证明。

**定理**：$$(X,d)$$，若 $$M\subset X$$ 为**紧集**，则 $$M$$ 一定**完备**，并且一定是**有界闭集**。

**定理**：$$(X,d)$$，$$M\subset X$$ 为紧集，$$N\subset M$$，则 $$N$$ 为紧集 $$\iff N$$ 为闭集。

证明：略。

**定理**：$$(X,\Vert\cdot\Vert)$$，$$\text{dim}X=n<\infty$$，$$M\subset X$$ 为紧集 $$\iff M$$ 为有界闭集。

**证明**：必要性易证，充分性证明的关键是首先找到 Hamel 基表示，将在 $$M$$ 中寻找收敛子列的任务分解到对每一个坐标维度上寻找收敛子列，而这可以根据 Bolzano-Weiertrass 定理得到，然后再根据每个坐标为度上的收敛子列得到 $$M$$ 中的收敛子列。证毕。

**引理**：$$(X,\Vert\cdot\Vert)$$，$$M\subsetneq X$$ 为闭集线性子空间，对于 $$\forall 0 < \theta < 1$$，$$\exists z\in X,\Vert z\Vert =1,\forall y\in M,\Vert z-y\Vert \ge \theta.$$

**证明**：固定 $$\forall v\in Y^c$$，令 $$a=\inf_{y\in Y}\Vert v-y\Vert$$，那么 $$a>0$$，否则的话与 $$Y$$ 是闭集相矛盾。因此存在 $$y_0\in Y$$ 使得 $$a\le \Vert v-y_0\Vert \le a/\varepsilon$$。那么我们就可以把这个 $$v$$ 平移到 $$0$$ 点附近，同时也把对应的 $$y_0$$ 平移到原点附近，也就是取 $$y=\frac{v-y_0}{\Vert v-y_0\Vert}$$，那么 $$\Vert y\Vert=1$$，并且可以验证 $$\forall z\in X$$，都有 $$\Vert y-z\Vert \ge \varepsilon.$$ 证毕。

**定理**(F.Riesz)：$$(X,\Vert\cdot\Vert)$$，则 $$\text{dim}X<\infty \iff \bar{B}(0,1)$$ 为紧集。

**证明**：必要性易证。充分性可以利用反证法，若维度无穷，则可以构造出特殊的序列，使得序列中任意两个元素的距离都大于 $$1/2$$（这要用到上一个引理），从而不存在收敛子列，即 $$\bar{B}(0,1)$$ 不是紧集。证毕。

**推论**：$$(X,\Vert\cdot\Vert)$$，则 $$\text{dim}X<\infty\iff S(0,1)=\{x:\Vert x\Vert=1\}$$ 为紧集。

**定义**：$$(X,d)$$，$$M\subset X$$ 非空，$$x_0\in X$$，令
$$
\rho(x_0, M) = \inf_{y\in M} d(x_0, y)
$$
称为 $$x_0$$ 到 $$M$$ 的距离。若 $$\exists y_0\in M$$，使得 $$\rho(x_0,M)=d(x_0,y_0)$$，则称 $$y_0$$ 为 $$x_0$$ 在 $$M$$ 中的最佳逼近元。

**命题**：设 $$M$$ 为非空紧集，则 $$\forall x_0 \in X$$，$$x_0$$ 在 $$M$$ 中的最佳逼近元存在。

**命题**：$$(X,d), M$$ 为 $$X$$ 的有限维线性子空间，$$\forall x_0\in X, \rho(x_0,M)=\inf_{y\in M}\{\Vert x_0-y\Vert\}$$，则 $$x_0$$ 在 $$M$$ 中的最佳逼近元一定存在。

证明：略。

> **小结**：本部分主要证明了有限维赋范空间的良好性质：
>
> 1. 有限维赋范空间**所有范数等价**，且均为 **Banach 空间**；
> 2. 有限维赋范空间**紧集**（即任意序列存在收敛子列） $$\iff$$ **有界闭集**；

