
## 3. 标准正交基

内积空间 $$(X,\langle \rangle )$$ 中，$$M\subset X$$ 为**正交集**，若 $$\forall x,y\in M,x\ne y,\Rightarrow x\perp y.$$ 进一步若 $$M$$ 中任意元素 $$\Vert x\Vert=1$$，则称 $$M$$ 为**标准正交集**。

对于一个标准正交序列 $$M=\{e_n,n\ge1\}$$，有 **Bessel 不等式**
$$
\sum_{i=1}^\infty |\langle x,e_i\rangle |^2 \le \Vert x\Vert^2.
$$

有了标准正交集的概念，我们很容易联想到正交基。下面列出的正交集的性质都可以类比基，但是随便取一个标准正交集，其并不一定完备，因此二者又有细微的差别。

**定理**：$$H$$ 为 Hilbert 空间，$$\{e_1,e_2,...\}$$ 为 $$H$$ 的标准正交集，那么有

- $$\forall \lambda_n\in\mathbb{K}, \sum^\infty_n \lambda_ne_n$$ 收敛 $$\iff \sum_n^\infty |\lambda_n|^2<\infty$$
- 若 $$x=\sum^\infty_n \lambda_n e_n$$，则 $$\lambda_n=\langle x,e_n\rangle $$
- $$\forall x\in H, \sum^\infty_n\langle x,e_n\rangle e_n$$ 收敛

证明：由于涉及到无穷级数，因此证明过程中需要首先考虑 $$S_N=\sum_{n=1}^N \lambda_n e_n$$ 的情况，再证明 $$N\to\infty$$ 的时候极限成立。细节略。

如果对于标准正交集 $$M$$ 我们有 $$\overline{\text{span}M}=H$$，那么称 $$M$$ 在 $$H$$ 中为**完全的**。实际上这里很容易联想到完备正交基，我们知道空间中任意一点都可以用基的线性组合来表示，如果 $$M$$ 是完全的，那么我们可以有相似的结论。

**命题**：首先定义 $$\forall x\in X, M_x=\{e\in M, \langle x,e\rangle \ne0\}$$，那么一定有 $$M_x$$ 是至多可数的。

证明：定义 $$M_{x,n}=\{e\in M, |\langle x,e\rangle |\ge \frac{1}{n}\}$$，$$M_x=\cup^\infty_{n=1} M_{x,n}$$，只需证明 $$\forall n\ge1, M_{x,n}$$ 为至多可数集。

假设 $$M_{x,n}$$ 中两两不等的元素可以表示为 $$e_1,...,e_N$$，那么 $$\frac{N}{n^2}\le\sum_{n=1}^N|\langle x,e_i\rangle |^2\le\Vert x\Vert^2 \Rightarrow N\le n^2\Vert x\Vert^2$$，说明 $$M_{x,n}$$ 中的元素个数是有限的。证毕。

**定理**：$$H$$ 为 Hilbert 空间，$$M$$ 为 $$H$$ 的标准正交集，则下述命题等价：

1. $$M$$ 为完全的；
2. $$\forall x\in H,x=\sum_{e\in M}\langle x,e\rangle e$$；
3. $$\forall x\in H, \Vert x\Vert^2=\sum_{e\in M}|\langle x,e\rangle |^2.$$
4. $$\forall x,y\in H,\langle x,y\rangle =\sum_{e\in M}\langle x,e\rangle \langle e,y\rangle $$

证明：首先用反证法证明 $$2\Rightarrow1,3\Rightarrow1.$$ 然后考虑 $$\forall x\in H, M_x=\{e_1,e_2,...\}$$，令 $$y=\sum^\infty_{i=1} \langle x,e_i\rangle e_i$$， $$z=y-x$$，容易证明 $$\langle z,e_i\rangle =0,\forall i\ge1$$，那么就有 $$z\in M^{\perp}=\{0\}$$，从而 $$x=y=\sum^\infty_{i=1} \langle x,e_i\rangle e_i$$，$$1\Rightarrow2$$。其余证明可以参考课本。此处省略。

对于内积空间 $$X$$ 的一列线性无关元素 $$\{x_1,...,x_n\}$$，那么存在一组标准正交序列 $$e_1,...,e_n$$ 使得
$$
\text{span}\{x_1,...,x_n\} = \text{span}\{e_1,...,e_n\}
$$
其中一种获取方法为 **Gram-Schmidt 标准正交化方法**，即

1. 首先取 $$e_1=\frac{x_1}{\Vert x_1\Vert}$$
2. 然后 $$v_2=x_2-\langle x_2,e_1\rangle e_1, e_2 = \frac{v_1}{\Vert v_2\Vert}$$
3. 上述过程重复进行。

**定理**：$$H$$ 为 Hilbert 空间，$$M$$ 为 $$H$$ 的标准正交集，则存在 $$N$$ 为完全标准正交集，$$M\subset N.$$

**推论**：任意 Hilbert 空间均有完全标准正交集。

证明：可以根据有限维空间、无限维可分空间进行讨论，应用 Gram-Schmidt 标准正交化方法即可获得完全标准正交集。

实际上如果我们能构造出来  Hilbert 空间的一组标准正交基，那么对于有限维空间 $$\text{dim}H=n$$，其与 $$\mathbb{K}^n$$ 等距同构；对于无穷维可分空间，其与 $$\ell^2$$ 等距同构。

> **小结**：
>
> 1. 本小节讲到的标准正交集可以用于向量的线性分解表示。
> 2. 当标准正交集是完全的，那么它实际上就是 Hilbert 空间 $$H$$ 的一组标准正交基。这又可以看作是线性空间中 Hamel 基/Schauder 基的更特殊的情况，因为完备的标准正交集要求相互正交，而 Hamel 基和 Schauder 基只要求线性无关。
> 3. 实际上根据 Gram-Schmidt 标准正交化方法可以由两种基构造出标准正交基。



## 4. Hilbert 空间上有界线性泛函表示

对于内积空间 $$X$$，取 $$z_0\in X$$，那么我们可以定义一个线性泛函 $$f_{z_0}(x)=\langle x,z_0\rangle $$，可以验证 $$f_{z_0}\in X^{\star}$$，并且有 $$\Vert f_{z_0}\Vert = \Vert z_0\Vert$$，因此 $$f_{z_0}\in X'$$。

那么如果反过来，任取 $$f\in X'$$，我们是否能够断言 $$f$$ 都可以表示为 $$f(x)=\langle x,z_0\rangle $$ 的形式呢？可以！这个表示形式如此简洁，以后你会发现这个性质非常有用！但并不是任意赋范空间都可以如此表示，只有 Hilbert 空间有这个良好的性质。

> **定理(F.Riesz)**：$$H$$ 为 Hilbert 空间，则 $$\forall f\in H',\exists! z_0\in H,f(x)=\langle x,z_0\rangle .$$
>
> **证明**：若 $$f=0$$，取 $$z_0=0.$$
>
> 若$$f\ne0,f\in H'$$，那么 $$N(f)=\{x\in H,f(x)=0\}$$ 为 $$H$$ 的闭线性子空间，因此有 $$H=N(f)\oplus N(f)^{\perp}$$，且 $$N(f)^{\perp}\ne\{0\}$$。接下来的问题就是如何构造一个函数 $$\langle x,z\rangle $$ 让其等于 $$f(x)$$？
>
> 首先固定 $$z_0\in N(f)^{\perp},z_0\ne0$$。任给 $$x\in H$$，考虑 $$v=f(x)z_0-f(z_0)x \in H$$，显然有 $$f(v)=0$$，故 $$v\in N(f)$$，从而有
> $$
> \langle v,z_0\rangle  = f(x)\langle z_0,z_0\rangle -f(z_0)\langle x,z_0\rangle =0 \\
> \Longrightarrow f(x)=\langle x,\frac{\overline{f(z_0)}z_0}{\Vert z_0\Vert^2}\rangle =\langle x,y_0\rangle .
> $$
> 下面证明 $$y_0$$ 的唯一性。略。
>
> 证毕。
>
> **NOTE**：实际上 $$N(f)^{\perp}$$ 是一维空间，也就是 $$\text{span}\{z_0\}$$，因此我们随便从 $$N(f)^{\perp}$$ 中取一个向量 $$z_0$$ 乘以一个线性系数就能得到 $$f(x)$$。
>
> >  显然 $$g(x)=\langle x,z_0\rangle $$ 并不一定等于 $$f(x)$$，那么我们怎么让他变化一下变成 $$f$$ 呢？看来需要对 $$g$$ 做一些映射，最简单的做一个线性变换，考虑 $$g'(x)=cg(x)$$，要想让 $$g'(x)=f(x)$$，至少应该满足 $$g'(z_0)=c\langle z_0,z_0\rangle =f(z_0)\Rightarrow g'(x)=\langle x,\frac{\overline{f(z_0)}z_0}{\Vert z_0\Vert^2}\rangle =\langle x,y_0\rangle .$$ 那么我们来验证一下是否任意的 $$x\in H$$ 都有 $$g(x)=f(x)$$？
> >
> >  $$z_0\in N(f)^{\perp},\forall x\in N(f),g'(x)=0$$ 没毛病，

假设 $$X,Y$$ 为 $$\mathbb{K}$$ 上的赋范空间，称 $$f:X\times Y\to \mathbb{K}$$ 为**共轭双线性泛函**，若
$$
f(\lambda_1 x_1+\lambda_2 x_2,y)=\lambda_1 f(x_1,y)+\lambda_2 f(x_2,y) \\
f(x,\lambda_1 y_1+\lambda_2 y_2)=\overline{\lambda_1} f(x,y_1)+\overline{\lambda_2} f(x,y_2)
$$
称其为有界的，若 $$\exists C\ge0$$，使
$$
|f(x,y)|\le C\Vert x\Vert \Vert y\Vert, \quad \forall x\in X, y\in Y
$$
定义其范数为
$$
\Vert f\Vert = \sup_{x\ne0,y\ne0} \frac{|f(x,y)|}{\Vert x\Vert \Vert y\Vert}.
$$
**定理(F.Riesz)**：$$H_1,H_2$$ 为 Hilbert 空间，$$f:H_1\times H_2\to \mathbb{K}$$ 为有界共轭双线性泛函，则 $$\exists! S\in B(H_1,H_2), f(x,y)=\langle Sx,y\rangle ,x\in X,y\in Y.$$

证明：首先固定 $$x\in H_1$$，只关注 $$H_2 \to \mathbb{K}$$，即 $$y\mapsto \overline{f(x,y)}$$ 为有界线性泛函，因此可以 $$\exists!S_x\in H_1$$，使得
$$
\overline{f(x,y)}=\langle y,S_x\rangle \Rightarrow f(x,y)=\langle S_x,y\rangle 
$$
现在对 $$x$$ 任取，可以得到 $$S:H_1\to H_2$$，由于 $$f$$ 是有界共轭双线性的，容易验证 $$S$$ 为有界线性算子。证毕。

下面如果我们定义 $$g(x,y)=\overline{f(y,x)}=\langle x,Sy\rangle ,x\in H_2,y\in H_1$$，那么 $$g$$ 也是有界共轭双线性算子，并且根据上面的 Riesz 表示定理，$$\exists! T\in B(H_2，H_1)$$ 使得 $$g(x,y)=\langle Tx,y\rangle =\langle x,Sy\rangle .$$ 由此我们就导出了伴随算子的定义，我们称 $$S$$ 为 $$T$$ 的**伴随算子**，记为 $$S=T^{\star}$$，并且根据上面的推导过程可以得到伴随算子是**唯一的**。

伴随算子有以下性质：

- $$\Vert T^{\star}\Vert=\Vert T \Vert$$
- $$(\lambda S+\mu T)^{\star}=\bar{\lambda}S^\star + \bar\mu T^{\star}$$
- $$(T^\star)^\star=T$$
- $$\Vert T^{\star}T\Vert=\Vert TT^{\star}\Vert=\Vert T \Vert^2$$
- $$T^{\star}T=0 \iff T=0$$
- $$(PS)^\star=S^\star P^\star$$

*例子 1*：伴随算子一个最简单的例子就是矩阵。$$H_1=H_2=\mathbb{K}^n,T\in B(H_1,H_2),\exists!A$$ 为 $$n$$ 阶方针，使得 $$Tx=Ax$$，容易验证 $$T^\star x=A^H x.$$

**定理**：$$H_1,H_2$$ 为 Hilbert 空间，$$T\in B(H_1,H_2)$$ 为一一映射，则 $$T$$ 为**等距同构**，当且仅当
$$
TT^\star=I_{H_2},\quad T^\star T=I_{H_1.}
$$
此时称 $$T$$ 为 $$H_1$$ 到 $$H_2$$ 的**酉算子**。

证明：要证明等距同构只需要验证 $$\langle Tx,Ty\rangle _2=\langle x,y\rangle _1,\forall x,y\in H_1$$ 或者 $$\langle T^\star x,T^\star y\rangle _1=\langle x,y\rangle _2,\forall x,y\in H_2$$ 成立，做一下变换即可证明。证毕。

**NOTE**：实际上这里可以联想到酉矩阵。

> **小结**：这一小节最核心的内容就是 Riesz 表示定理，即 **Hilbert 空间**上任意**有界线性泛函**都可以**唯一地**表示为
> $$
> f(x) = \langle x,z_0\rangle , \forall x\in H
> $$

