
## 1. 共轭算子

赋范空间 $$X,Y$$，$$T\in B(X,Y)$$，对于任意的 $$f\in Y'$$，$$X \stackrel{T}{\longrightarrow}Y\stackrel{f}{\longrightarrow}\mathbb{K}$$，可以得到 $$f\circ T\in X'$$。因此我们可以定义映射
$$
\begin{aligned}
T^{\times}:Y' &\to X' \\
f &\mapsto f\circ T
\end{aligned}
$$
称其为**共轭算子**。他有如下性质（容易验证，不再证明）：

<!--more-->

- $$T^{\times}\in B(Y',X')$$
- $$\Vert T^{\times}\Vert=\Vert T\Vert$$（证明过程用到了 Hahn-Banach定理）
- $$(S+T)^{\times}=S^\times + T^\times,\ S,T\in B(X,Y)$$
- $$(\lambda T)^\times=\lambda T^\times$$
- $$(AB)^\times=B^\times A^\times,\ A\in B(X,Y),B\in B(Y,Z)$$

*例子 1*：设 $$X=Y=\mathbb{C}^n,T\in B(\mathbb{C}^n,\mathbb{C}^n)$$，则 $$\exists!A$$ 为 $$n$$ 阶方阵使得 $$Tx=Ax$$，而 $$T^\times\in B((\mathbb{C}^n)',(\mathbb{C}^n)')$$。实际上 $$f\in(\mathbb{C}^n)'$$ 可以表示为 $$f(x)=\sum_i^n \alpha_i x_i=\alpha^T x$$，$$T^\times f(x)=\sum_i^n\beta_i x_i=\beta^T x$$。容易验证 $$\beta=A^T\alpha.$$

在这里，我们可以联想到**伴随算子**，$$T\in B(H_1,H_2)$$，其伴随算子 $$T^\star\in B(H_2,H_1)$$ 满足 $$\langle Tx,y\rangle=\langle x,T^\star y\rangle.$$ 而这里的共轭算子则是 $$T^\times\in B(H_2', H_1').$$ 

回忆第二章我们讲等距同构概念的时候，提到了 $$(\mathbb{K}^n,\Vert\cdot\Vert_2)' = (\mathbb{K}^n,\Vert\cdot\Vert_2)$$，也就是说实际上我们可以找到某个映射 $$A:H'\to H$$。如果能找到这样的一个双射，就可以认为 $$T^\star$$ 与 $$T^\times$$ 是等价的。

一般的空间未必有如此良好的性质，但对于 **Hilbert 空间**来说，任意 $$f\in H'$$ 都可以唯一地表示为 $$f(x)=\langle x,z\rangle, z\in H$$，那么我们就可以定义映射
$$
\begin{aligned}
A:H' &\to H \\
f &\mapsto z
\end{aligned}
$$
容易证明 $$A$$ 时**共轭线性**的（并且是**双射**），即 $$A(\lambda f+\mu g)=\bar{\lambda}Af+\bar{\mu}Ag$$。

此时我们可以得到如下图所示的映射关系，可以看到实际上 $$T^\times = A_1^{-1}T^\star A_2$$

![conjugate operator](https://raw.githubusercontent.com/Glooow1024/ImgHosting/master/hexo/2020/ch4-1-conjugate-operator.png)

*例子 2*：考虑 Hilbert 空间 $$H_1,H_2$$，$$g\in H_2'$$ 可以表示为 $$g(y)=\langle y,y_0\rangle$$，因此实际上有 $$A_2g=y_0\in H_2$$，令 $$f=T^\times g\in H_1'$$，因此可以表示为 $$f(x)=\langle x,x_0\rangle$$，这可以表示为 $$A_1f=x_0\in H_1$$，因此有 $$A_1T^\times g=x_0$$，结合 $$A_1T^\times = T^\star A_2$$ 就有 $$x_0=T^\star y_0.$$

