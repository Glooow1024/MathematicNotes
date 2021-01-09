
我们前面讲了距离空间、赋范空间，距离空间赋予了两个点之间的距离度量，范数赋予了每个点自身的长度度量，而范数则可以导出距离。本章要讲的内积可以看成是更加统一的定义，因为从内积我们可以导出范数，进而导出距离。因此内积空间是一个“更小”的空间，在此基础上结合完备性我们引出了 Hilbert 空间，后续我们的研究也大多集中在 Hilbert 空间上。

## 1. 内积空间

**定义**：$$X$$ 为 $$\mathbb{K}$$ 上的线性空间，$$\langle \cdot,\cdot\rangle :X\times X\to \mathbb{K}$$，若满足如下条件

1. $$\langle \lambda x+\mu y, z\rangle  = \lambda\langle x,z\rangle +\mu\langle y,z\rangle $$
2. $$\overline{\langle x,y\rangle }=\langle y,z\rangle $$
3. $$\forall x\in X, \langle x,x\rangle  \ge 0$$
4. $$\langle x,x\rangle =0 \iff x=0$$

则称 $$(X,\langle \cdot,\cdot\rangle )$$ 为**内积空间**。可以用内积定义范数 $$\Vert x\Vert = \langle x,x\rangle ^{1/2}$$。若得到的 $$(X,\Vert\cdot\Vert)$$ 为 Banach 空间，那么 $$(X,\langle \cdot,\cdot\rangle )$$ 为 **Hilbert 空间**。

<!--more-->

**定理**：$$(X,\langle \cdot,\cdot\rangle ),\forall x,y\in X$$ 有

- $$|\langle x,y\rangle |\le \Vert x\Vert \cdot\Vert y\Vert$$（Schwartz 不等式）等号成立 $$\iff x,y$$ 线性相关 $$\iff y=0$$ 或 $$x=cy$$
- $$\Vert x+y\Vert\le\Vert x\Vert+\Vert y\Vert$$ 等号成立 $$\iff x,y$$ 线性相关 $$\iff y=0$$ 或 $$x=cy$$

**定理**：$$(X,\langle \cdot,\cdot\rangle )$$，设 $$x_n\to x,y_n\to y$$，则 $$\langle x_n,y_n\rangle  \to \langle x,y\rangle $$（此定理说明**内积为连续映射**）。

证明：略。

**命题**：若 $$\Vert\cdot\Vert$$ 为 $$X$$ 上的范数，若 $$\forall x,y\in X$$ 都满足平行四边形等式 $$\Vert x+y\Vert^2 + \Vert x-y\Vert^2=2(\Vert x\Vert^2 + \Vert y\Vert^2)$$，则存在 $$X$$ 上的内积 $$\langle \cdot,\cdot\rangle $$，使得 $$\Vert x\Vert=\langle \cdot,\cdot\rangle ^{1/2}.$$

证明：较复杂，略。

*例子 1*：$$X=\mathbb{K}^2,\Vert(x,y)\Vert_\infty$$ 不是内积空间，反例比如 $$x=(1,1),y=(1,-1)$$，验证平行四边形等式不成立即可。

*例子 2*：$$(\ell^\infty,\Vert\cdot\Vert_\infty)$$ 不是内积空间，反例如 $$x=(1,0,0,...),y=(0,-1,0,...)$$。

实际上对于空间 $$X=\mathbb{K}^n,n>0$$，$$\Vert x\Vert_p$$ **只有在 $$p=2$$ 的时候才是内积空间**，其余情况均不是内积空间。

对于空间 $$(\ell^p,\Vert\cdot\Vert_p)$$ 也**只有在 $$p=2$$ 的时候才是内积空间**。

*例子 3*：$$C[0,1],\Vert x\Vert_\infty$$ 不是内积空间，反例比如 $$x(t)=1+t,y(t)=1-t$$，验证平行四边形等式不成立即可(说明找不到合适的内积定义来导出无穷范数)。

类比上面的例子，我们也可以对连续函数定义 $$2$$ 范数($$p$$ 范数)。首先定义内积
$$
\langle x,y\rangle =\int_a^b x(t)\overline{y(t)} dt \quad\Rightarrow\quad \Vert x\Vert=\langle x,x\rangle ^{1/2} \\
\Vert x\Vert_p = \left(\int_a^b |x(t)|^p dt\right)^{1/p}
$$
同样地，**只有在 $$p=2$$ 的时候 $$(C[a,b],\Vert x\Vert_p)$$ 才是内积空间。**

到这里大家基本了解了内积空间的特点，他比一般的赋范空间更严格，度量空间就更不用说了。根据初中的知识，有了内积我们就能计算夹角了，不过这里我们不讲夹角，而是考虑**正交**和**正交补**的概念。

> **小结**：这一部分讲了内积运算的定义，并且由内积可以导出范数的定义，但是内积比范数的要求更严格，因此对于某个范数，可以通过验证平行四边形等式来验证其是否可以由内积运算来导出。



## 2. 正交补与正交投影

内积空间 $$(X,\langle \rangle )$$ 中，称 $$x,y$$ **正交**，若 $$\langle x,y\rangle =0$$，记为 $$x\perp y$$。$$M\subset X$$ 非空，定义其**正交补** $$M^{\perp}=\{x\in X:x\perp y,\forall y\in M\}.$$

**命题**：$$M^{\perp}$$ 为 $$X$$ 的**闭集线性子空间**。

证明：易证 $$M^{\perp}$$ 为线性子空间，然后再用内积的是连续映射证明 $$M^{\perp}$$ 为闭集。

这里插入一个**最佳逼近元**的概念。定义 $$\xi(x_0,M)=\inf_{y\in M}d(x_0,y)$$，若存在 $$y_0\in M$$ 使得 $$d(x_0,y_0)=\xi(x_0,M)$$，那么就称 $$y_0$$ 为最佳逼近元。什么情况下最佳逼近元存在呢？

1. 当 $$M$$ 为非空紧集的时候，$$y_0$$ 存在（因为紧集一定是有界闭集）。
2. 若 $$X$$ 为赋范空间，$$M$$ 为 $$X$$ 的有限维线性子空间，则 $$y_0$$ 存在（因为有限维赋范空间都完备，$$M$$ 为闭集）。

**定理**：$$(X,\langle \rangle )$$，$$M$$ 为 $$X$$ 非空凸子集，且 $$M$$ 完备，则 $$\forall x_0\in X$$，$$\exists!y_0\in M$$ 为最佳逼近元，并且有 $$x_0-y_0\in M^{\perp}$$。

证明：先找到 $$y_n\in M,d(x_0,y_n)\le\xi(x_0,M)+\frac{1}{n}$$，证明其为柯西列，由于 $$M$$ 完备，得到最佳逼近元的存在性。再由 $$M$$ 的凸性质证明唯一性。证毕。

对于线性空间 $$X$$，$$M,N$$ 为 $$X$$ 的线性子空间，称 $$X$$ 为 $$M,N$$ 的**直和**，若 $$\forall x\in X,\exists! m\in M,n\in N,x=m+n$$，记为 $$X=M\oplus N.$$

很容易验证 $$X=M\oplus N \iff X=\text{span}(M\cup N), M\cap N=\{0\}.$$

**定理**：设 $$H$$ 为 Hilbert 空间，$$M$$ 为 $$H$$ 的闭线性子空间，则 $$H=M\oplus M^{\perp}.$$

证明：$$M$$ 完备，对 $$\forall x\in H$$，$$\exists!y\in M$$，使得 $$\Vert x-y\Vert=\xi(x,M)$$，并且 $$x-y\in M^{\perp}$$。证毕。

**定理**：设 $$H$$ 为 Hilbert 空间，$$M$$ 为 $$H$$ 的闭线性子空间，则 $$(M^{\perp})^{\perp}=M.$$

证明：略。

上面两条定理当中，只有 $$M$$ 是 $$H$$ 的闭线性子空间才有如此良好的性质！因为只有闭线性子空间才能认为 $$M$$ 是尽可能“丰满”的。举个例子，$$\mathbb{R}^3$$ 中，令 $$M=\{e_1=(1,0,0)\}$$，那么 $$M^{\perp}$$ 为 $$y-z$$ 平面，$$(M^{\perp})^{\perp}$$ 为 $$x$$ 轴，相比于原始的 $$M$$ 扩展到无穷远处了。

**推论**：设 $$H$$ 为 Hilbert 空间，$$M\subset H$$ 非空，则 $$\overline{\text{span}M}=H \iff M^{\perp}=\{0\}.$$

**引理**：$$M^{\perp}=(\bar{M})^\perp,\quad (\text{span}M)^{\perp}=M^{\perp}.$$

证明：略。

**NOTE**：这个引理实际上说明了正交补空间在定义的时候已经是“最大化的”，即使原空间 $$M$$ 稍微扩张一点点，其正交补空间仍然保持不变。

设 $$H$$ 为 Hilbert 空间，$$M$$ 为 $$H$$ 的闭线性子空间，那么对于 $$\forall x\in H$$，存在唯一的分解 $$x=y+z,y\in M,z\in M^\perp.$$ 记 $$P_Mx=y$$，称 $$P_M$$ 为从 $$H$$ 到 $$M$$ 上的**正交投影**，其有如下性质：

1. $$P_M$$ 为线性算子；
2. $$P_M$$ 有界，并且 $$P_M=1, M\ne\{0\}$$，$$P_M=0,M=\{0\}$$；
3. $$P_M^2=P_M$$；
4. $$R(P_M)=M, N(P_M)=M^{\perp}$$。

> **小结**：本小节给出了正交补的定义
>
> 1. 不论原空间 $$M$$ 如何，正交补空间 $$M^{\perp}$$ 总是有一些良好的性质：1）闭线性子空间；2）“最大化的”；
> 2. 如果原空间 $$M$$ 同时有良好的性质（闭线性子空间），那么他们两个就是对整个空间 $$H$$ 的良好分割。
