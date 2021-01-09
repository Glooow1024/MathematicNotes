
一致有界性原理的一个应用就是序列和算子的收敛性分析。

## 1. 序列收敛性

$$(X,\Vert\cdot\Vert)$$，有 $$x_n,x\in X$$，称 $$x_n$$ **强收敛**到 $$x$$，若 $$\Vert x_n-x\Vert \to 0$$；称 $$x_n$$ **弱收敛**到 $$x$$ 若 $$\forall f\in X'$$ 都有 $$f(x_n)\to f(x)$$，记为 $$x_n \stackrel{w}{\longrightarrow} x.$$

关于弱收敛有以下几条性质：

- 若 $$x_n \stackrel{w}{\longrightarrow} x, x_n \stackrel{w}{\longrightarrow} y$$，则 $$x=y$$；
- 若 $$x_n \stackrel{w}{\longrightarrow} x$$，则存在 $$c\ge0, \Vert x_n\Vert \le c.$$

<!--more-->

证明：仅证第二条。这个性质说明 $$x_n$$ 有界，因此容易想到需要用一致有界性原理证明，但是该原理说明的是算子的一致有界，这里是元素 $$x_n$$ 有界，因此又可以想到上一篇讲到的典范映射 $$J:X\to X''$$ 从元素映射到算子。因此这里考虑 $$X'$$ 上的线性泛函 $$g_n= J(x_n):X'\to \mathbb{R}$$，有 $$g_n(f)=f(x_n),\forall f\in X'.$$ 于是有 $$f(x_n)\to f(x)$$，因而固定任一 $$f$$，都有 $$\sup_n g_n(f) < \infty$$，同时由于 $$X'$$ 总为 Banach 空间，利用一致有界性原理有 $$\sup_n \Vert g_n\Vert =\sup_n \Vert x_n\Vert < \infty$$。证毕。

> **定理**：$$(X,\Vert\cdot\Vert)$$，有 $$x_n,x\in X$$，则 $$x_n \stackrel{w}{\longrightarrow} x$$ **当且仅当**：
>
> 1. 存在 $$c\ge0,\Vert x_n\Vert\le c$$；
> 2. 并且存在 $$M\subset X',\overline{\text{span}M}=X'$$，对 $$\forall f\in M, f(x_n)\to f(x).$$（此时 $$M$$ 称为**完全集**）
>
> **NOTE**：该定理简化了弱收敛的判断条件，只需要在 $$X'$$ 的一个子集上判断函数值是否收敛。

证明：$$"\Longrightarrow"$$ 易证；

$$"\Longleftarrow"$$，首先考虑 $$\forall f\in \text{span}M$$，容易得到 $$f(x_n)\to f(x)$$。然后对 $$\forall g\in X'$$，那么存在 $$f_m\in\text{span}M$$ 使得 $$\Vert f_m-g\Vert \le 1/m$$，因此
$$
\begin{align}
|g(x_n)-g(x)|&\le |g(x_n)-f_m(x_n)|+|f_m(x_n)-f_m(x)|+|f_m(x)-g(x)| \\
&\le \frac{1}{m}(\Vert x_n\Vert+\Vert x\Vert)+|f_m(x_n)-f_m(x)| \to 0(m,n\to\infty)
\end{align}
$$
证毕。

***例子 1***：考虑 $$X=\ell^p(1<p<\infty)$$，有 $$(\ell^p)'=\ell^q, 1/p+1/q=1.$$ 考虑线性泛函 $$f_y(x)=\sum_i y_ix_i,y\in \ell^q$$，有 $$\Vert f_y\Vert=\Vert y\Vert_q$$。我们考虑 $$X'$$ 的子空间 $$M=\{e_n,n\ge1\}$$，其中 $$e_n=(...,0,1,0,...)$$ 表示只有第 $$n$$ 个分量为 1，其余为 0。那么 $$\overline{\text{span}M}=X'$$，因此要想验证 $$x_n$$ 是否弱收敛到 $$x$$ 就只需要验证：1）其有界性；2）对每个 $$f_{e_k},k\ge1$$ 是否有 $$f_{e_k}(x_n)\to f_{e_k}(x)(n\to\infty).$$

强收敛与弱收敛之间有如下关系：

- $$x_n\to x \Longrightarrow x_n \stackrel{w}{\longrightarrow} x$$(即强收敛可以导出弱收敛)；
- 若 $$\text{dim}X<\infty$$，则 $$x_n \stackrel{w}{\longrightarrow} x\Longrightarrow x_n\to x$$(**有限维**赋范空间中，强收敛与弱收敛等价)；

证明：仅证第二条。设 $$\text{dim}X=n<\infty$$，有限维赋范空间中我们可以找到一组基，$$x_k=\lambda_{k,1}e_1+\cdots+\lambda_{k,n}e_n$$，$$x=\lambda_1 e_1+\cdots+\lambda_n e_n$$。那么
$$
\lambda_{k,1}f(e_1)+\cdots+\lambda_{k,n}f(e_n) \to \lambda_{1}f(e_1)+\cdots+\lambda_{n}f(e_n), \quad\forall f\in X'
$$
由于 $$f\in X'$$ 任取，那么我们可以取 $$f_i(y)=\mu_i$$，其中 $$y=\mu_1 e_1+\cdots+\mu_n e_n$$，即 $$f_i$$ 取出来第 $$i$$ 个坐标系数。由此可以得到 $$\lambda_{k,i}\to\lambda_i(k\to\infty)$$，然后就容易得到 $$x_n\to x.$$ 证毕。

***例子 2***：有些无穷维空间中也可以得到 $$x_n \stackrel{w}{\longrightarrow} x\iff x_n\to x$$，例如 $$\ell^1.$$

***例子 3***：无穷维 Hilbert 空间（$$\ell^2$$，注意只有 $$2-$$范数才能定义出对应的内积），考虑 $$\{e_1,e_2,\ldots\}$$ 为 $$H$$ 的标准正交集，那么有 $$e_n \stackrel{w}{\longrightarrow} 0$$ 但是 $$e_n \nrightarrow 0$$。考虑 $$\forall f\in H'$$，存在唯一的 $$z_0\in H, f(x)=\langle x,z_0\rangle$$，由Bessel方程 $$\sum_n|\langle e_n,z_0\rangle|^2\le \Vert z_0\Vert^2$$，因此 $$f(e_n)\to 0(n\to \infty),\forall f\in H'$$，但另一方面 $$\Vert e_n\Vert=1\nrightarrow0$$。



## 2. 线性泛函收敛性

对于算子的收敛性，如线性泛函 $$f_n\in X'$$ 或者有界线性算子 $$T\in B(X,Y)$$，收敛性的定义跟上面序列的收敛性是相似的，但是又略有不同。下面就先给出线性泛函收敛性的分析。

同样考虑赋范空间 $$X$$，$$f,f_n\in X'$$，称 $$f_n$$ **弱星收敛**到 $$f$$，若任取 $$x\in X$$ 都有 $$f_n(x)\to f(x)$$，记为 $$f_n \stackrel{w\star}{\longrightarrow} f.$$

**NOTE**：实际上这里的弱星收敛跟序列的弱收敛是完全对称的，因此他们的性质也是类似的。

- 弱星收敛极限 $$f$$ 唯一；
- $$\{f_n\}$$ 的任意子列均弱星收敛到 $$f$$；
- 若 $$X$$ 为 Banach 空间，则 $$\{f_n\}$$ 在 $$X'$$ 中为**有界集**。

证明：仅证第三条，对于任意 $$x\in X$$，有 $$f_n(x)\to f(x)$$，因此 $$f_n(x)$$ 有界，由一致有界性原理，$$\sup_n \Vert f_n\Vert<\infty.$$ 证毕。

> **定理**：$$X$$ 为 **Banach 空间**，$$f_n,f\in X'$$，则 $$f_n \stackrel{w\star}{\longrightarrow} f$$ **当且仅当**：
>
> 1. 存在 $$c\ge0,\Vert f_n\Vert\le c$$；
> 2. 并且存在 $$M\subset X,\overline{\text{span}M}=X$$，对 $$\forall x\in M, f_n(x)\to f(x).$$
>
> **NOTE**：该性质与序列弱收敛的性质完全对称，证明省略。



> **NOTE**：对于 $$X'$$ 中的线性算子 $$f$$，也有范数的定义，因此我们也可以按照序列的收敛性来定义算子的收敛性。这个时候就用 $$X'$$ 代替上面的 $$X$$，用 $$X''$$ 代替上面的 $$X'$$。我们可以得到什么样的强收敛和弱收敛定义呢？（下面并不是标准的数学定义，只是我为了引出之后的内容做的解释）
>
> 对于 $$f,f_n\in X'$$，若满足 $$\Vert f_n-f\Vert\to 0$$，则称 $$f_n$$ **一致收敛**到 $$f$$；若对 $$\forall g\in X''$$，都有 $$g(f_n)\to g(f)$$，那么称 $$f_n$$ **强收敛**到 $$f$$；弱收敛的定义暂且不管。
>
> 注意从这个定义的字面意思来看，这里的一致收敛对应于上面序列的强收敛；这里的强收敛对应上面序列的弱收敛，它实际上也就对应于弱星收敛。这里就有两个值得思考的问题：1）**一致收敛和强收敛的区别是什么？**2）这里的强收敛为什么对应上面的弱收敛？
>
> 先看第2个问题：讲 Hahn-Banach 定理应用的时候我们讲到了典范映射，如果 $$X$$ 为自反的，那么任意一个 $$g_0\in X''$$ 都唯一的对应于 $$X$$ 中的元素 $$x_0$$，并且满足 $$g_0(f)=f(x_0),\forall f\in X'$$。假设 $$X$$ 是自反的，那么上面的强收敛定义就可以表述为 $$\forall x\in X$$，都有 $$f_n(x)\to f(x)$$，注意看！这是不是就是线性泛函弱星收敛的定义！也对应了序列的弱收敛。不过弱星收敛的定义里面并没有要求 $$X$$ 是自反的。
>
> 那么再看第1个问题：一致收敛中要求 $$\Vert f_n-f\Vert\to0$$，线性算子的范数是针对整个源空间考虑的；而强收敛中对每个 $$x\in X$$，关注 $$f_n(x)\to f(x)$$，也就是说关注的是每一个局部点。因此一致收敛要强于强收敛。

