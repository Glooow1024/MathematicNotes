
在度量空间中，我们重点关注的是两个元素之间的距离，而这一部分要引出来的赋范空间中，则对每个元素本身也赋予了“范数”，也就是“长度”。

## 1. 线性空间

线性空间，可以简单理解为对线性运算封闭的集合。那么线性运算的形式是什么呢？常见的线性运算可以写为 $$T(x;a)=\sum_i a_ix_i$$，因此可以看出来包含了**数乘**和**加法**两种基本运算，因此线性空间必然需要对数乘和加法封闭，除此之外，为了保证运算体系的自洽性，我们还需要规定一些其他的运算规则。最后，给出来线性空间的定义：

考虑 $$\mathbb{K=C\ or\ R}, X\ne \varnothing,\forall x,y\in X,\forall \lambda\in\mathbb{K}$$，可以定义 $$x+y\in X,\lambda x\in X$$，如果满足

1. $$x+y=y+x$$
2. $$(x+y)+z=x+(y+z)$$
3. $$\exists 0\in X,\forall x\in X, x+0=0+x=x$$
4. $$\forall x,\exists! y\in X,x+y=0,y=-x$$
5. $$\alpha(\beta x)=(\alpha\beta)x$$
6. $$1x=x$$
7. $$(\alpha+\beta)x=\alpha x+\beta x$$
8. $$\alpha(x+y)=\alpha x+\alpha y$$

则称 $$X$$ 为 $$\mathbb{K}$$ 上的**线性空间**。

***例子 1***：$$S=\{(x_n)_{n\ge1},x_n\in\mathbb{K} \}$$，定义加法 $$(x_n)_{n\ge1}+(y_n)_{n\ge1}=(x_n+y_n)_{n\ge1}\in S$$，定义数乘 $$\lambda(x_n)_{n\ge1}=(\lambda x_n)_{n\ge1}\in S$$，那么可以验证 $$S$$ 为线性空间。

***例子 2***：$$C[a,b]$$，定义 $$(f+g)(t)=f(t)+g(t), (\lambda f)(t)=\lambda f(t)$$，可以验证 $$C[a,b]$$ 为线性空间。

**定义**：$$X$$ 为 $$\mathbb{K}$$ 上的线性空间，$$Y\subset X$$，称 $$Y$$ 为 $$X$$ 的线性子空间，若 $$\forall x,y\in Y,\forall \lambda\in\mathbb{K}$$，有 $$x+y\in Y,\lambda x\in Y$$，并且 $$Y$$ 本身也是线性空间。

***例子 3***：$$\ell^\infty \subset S$$ 是线性空间。

***例子 4***：$$\ell^p \subset S,1\le p < \infty$$ 是线性空间。

***例子 5***：$$\ell^p \subset c_0(x_n\to0的序列\{(x_n)\}) \subset c(x_n收敛的序列) \subset \ell^\infty\subset S(无穷维序列)$$，每一个都是线性空间。

***例子 6***：$$P$$ 所有多项式的集合，$$P\subset C[a,b]$$ 也是线性空间。

**命题**：若 $$X$$ 为线性空间，$$(Y_i)_{i\in I}$$ 为 $$X$$ 的一族线性子空间，则 $$Y=\bigcap_{i\in I}Y_i$$ 仍然是 $$X$$ 的线性子空间。

**定义**：$$X$$ 为线性空间，$$M\subset X$$ 非空，令 $$\mathcal{E}$$ 为所有包含 $$M$$ 的线性子空间，那么一定有 $$X\in\mathcal{E}$$，因此 $$\mathcal{E}$$ 一定非空。令 $$Z=\bigcap_{Y\in\mathcal{E}}Y$$ 也一定是 $$X$$ 的线性子空间，记 $$Z=\text{span}(M)$$ 称为 $$M$$ **生成的线性子空间**。

**命题**：若 $$M\subset X$$ 非空，那么 $$Z=\text{span}(M) = \{\sum_i^n \lambda_i x_i,n\ge1,x_i\in M,\lambda_i\in\mathbb{K}\}$$ 为包含 $$M$$ 的 $$X$$ 的**最小线性子空间**。

证明：略。

***例子 1***：$$X=S,e_n=(0,\cdots,0,1,0,\cdots)\in S, M=\{e_n,n\ge1\}\subset S$$，则 $$\text{span}(M)=c_{00}$$(只有有限个元素非零的无穷维序列)。

**定义**：$$M\subset X$$ 为**线性无关**的，若 $$\forall x_1,...,x_n\in M$$ 两两不等，都有 $$x_1,...,x_n$$ 都线性无关(也即任意有限个元素都线性无关)。

***例子 2***：$$X=C[a,b],\alpha_1<\alpha_2<\cdots<\alpha_n\le\cdots, f_n=e^{\alpha_n t}\in C[a,b]$$，那么取 $$M=\{f_1,f_2,\cdots\}$$ 是线性无关的 $$\iff \forall n\ge1, f_1,...,f_n$$ 线性无关。

*证明*：利用线性相关的定义，重复求导、相减的过程，细节略。

**定义**： $$X$$ 为线性空间，若 $$X$$ 中存在 $$n$$ 个元素线性无关，但任意 $$n+1$$ 个元素都线性相关，则称 $$X$$ 为 $$n$$ **维**的，记为 $$\text{dim}X=n$$。若 $$\forall n\ge1,\exists x_!,...,x_n$$ 线性无关，则称 $$X$$ 为**无穷维**的。

**命题**：$$\text{dim}X=n,\forall x\in X$$ 都存在唯一的系数 $$a_1,...,a_n$$ 使得 $$x=a_1x_1+\cdots+a_nx_n$$。

证明：略。

对于复空间 $$\mathbb{C}^n$$，认为 $$\text{dim}\mathbb{C}^n=2n$$。

**定义**：$$X$$ 为线性空间，$$M\subset X$$ 线性无关，若 $$\text{span}(M)=X$$，则称 $$M$$ 为 $$X$$ 的 **Hamel 基**。

> **命题**：$$\forall x\in X$$，则 $$\exists x_1,...,x_n\in M$$ 两两不等，$$\exists \lambda_1,...,\lambda_n\in\mathbb{K}$$ 均不为 0，使得 $$x=\lambda_1 x_1+...+\lambda_n x_n$$，并且上述**表示唯一**。
>
> 证明：略。

***例子 1***：$$\{e_1,e_1,...\}$$ 为 $$c_{00}$$ 的 Hamel 基。

**定理**：$$X$$ 为线性空间，$$M\subset X$$ 线性无关，则 $$\exists N$$ 为 $$X$$ 的 Hamel 基，使得 $$M\subset N$$。

> **小结**：这一部分主要是讲解了线性空间的定义，最关键的概念就在于
>
> 1. 对于加法和数乘封闭；
> 2. 可以找到一组基，任意向量都可以用基的线性组合来表示，并且表示方法唯一。



## 2. 赋范空间与Banach空间

假设 $$X$$ 为 $$\mathbb{K}$$ 上的线性空间，定义范数运算 $$\Vert\cdot\Vert:X\to \mathbb{R}$$，满足如下条件：

1. $$\Vert x\Vert \ge 0$$
2. $$\Vert x\Vert =0\iff x=0$$
3. $$\Vert\lambda x\Vert=|\lambda|\cdot\Vert x\Vert$$
4. $$\forall x,y\in X, \Vert x+y\Vert\le \Vert x\Vert + \Vert y\Vert$$

则称 $$\Vert\cdot\Vert$$ 为 $$X$$ 上的范数，$$(X,\Vert\cdot\Vert)$$ 为**赋范空间**。

**定义**：在赋范空间中，$$\forall x,y\in X$$，若定义 $$d(x,y)=\Vert x-y\Vert$$，那么该方法定义的 $$d(x,y)$$ 也是度量，称为 $$\Vert\cdot\Vert$$ **诱导的度量**。若此时 $$(X,d)$$ 为**完备空间**，则称 $$(X,\Vert\cdot\Vert)$$ 为 **Banach 空间**（即完备的赋范空间）。

**注**：由于范数的定义中第 3 条存在，以及诱导度量只有 $$x-y$$ 决定，使得诱导度量相比于一般定义的度量还具有一些特别性质，例如：

- 平移不变性 $$d(x+a,y+a)=d(x+y)$$
- 齐次性 $$d(\lambda x,\lambda y)=|\lambda| d(x,y)$$

***例子 1***：$$(\mathbb{K}^n,\Vert\cdot\Vert_\infty),(\mathbb{K}^n,\Vert\cdot\Vert_p),(\ell^\infty,\Vert\cdot\Vert_\infty),(\ell^p,\Vert\cdot\Vert_p),(c_{0},\Vert\cdot\Vert_\infty),(c,\Vert\cdot\Vert_\infty)$$ 均为 Banach 空间。

***例子 2***：$$S=\{(x_n)_{n\ge1},x_n\in\mathbb{K}\},d(x,y)=\sum_n \frac{1}{2^n}\frac{|x_n-y_n|}{1+|x_n-y_n|}$$，**不存在** $$S$$ 上的范数 $$\Vert\cdot\Vert$$ 使 $$d$$ 被诱导出，因为 $$d$$ 不满足齐次性。

 ***例子 3***：$$(C[a,b],\Vert\cdot\Vert_\infty)$$ 为 Banach 空间，$$(C[a,b],\Vert\cdot\Vert_p)$$ 不是 Banach 空间。

***例子 4***：离散度量不满足齐次性，因此不可能由范数诱导出。

**命题 1**：$$(X,\Vert\cdot\Vert_\infty)$$ 为赋范空间，$$Y$$ 为 $$X$$ 的线性子空间。若 $$Y$$ 为 Banach 空间，则 $$Y$$ 在 $$X$$ 中必为闭集。

**命题 2**：$$(X,\Vert\cdot\Vert_\infty)$$ 为 Banach 空间，$$Y\subset X$$ 为闭集线性子空间，则 $$Y$$ 必为 Banach 空间。

证明：赋范空间的线性子空间仍然是赋范空间，完备空间一定要是闭集。细节略。

> 只需要掌握关键点，那么上面的命题都可以由下面的关键点轻松导出：
>
> 1. 完备空间一定是闭集；完备空间的子空间也完备 $$\iff$$ 该子空间为闭集；
> 2. 赋范空间 + 完备性 = Banach 空间。

**命题**：若 $$(X,\Vert\cdot\Vert)$$ 为 Banach 空间，$$x_n\in X$$，且 $$\sum_n^\infty \Vert x_n\Vert < \infty$$，则 $$\sum^\infty x_n$$ 收敛。

证明：完备空间中，证明序列收敛可以证明序列是柯西列。

**定义**：$$(X,\Vert\cdot\Vert)$$ 为赋范空间，$$e_n\in X(n\ge 1)$$，称 $$(e_n)_{n\ge1}$$ 为 $$X$$ 的一组 **Schauder 基**，若 $$\forall x\in X, \exists ! \lambda_n,x=\sum^\infty_n \lambda_n e_n$$。

**命题**：若 $$X$$ 有 Schauder 基，那么 $$X$$ 一定是可分的。

证明：可以取 $$M=\{\sum^n_{i=1}x_ie_i \in X, n\ge1, x_i\in\mathbb{Q} \}$$，是可数个可数集的并。

> Hamel 基与 Schauder 基的区别：
>
> 1. 最主要的区别是 Hamel 基可以是有限维也可以是无穷维的，这由集合 $$X$$ 的维数决定，而 Schauder 基则只定义在无穷维上；
> 2. 前者针对线性空间，后者针对 Banach 空间。
