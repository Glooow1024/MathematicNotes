
## 3. 一般有界线性算子收敛性

实际上一致收敛、强收敛、弱收敛的概念可以扩展到任意的有界线性算子定义。

设 $$X,Y$$ 为赋范空间，$$T_n\in B(X,Y),T:X\to Y$$ 为线性算子，有三种收敛性：

- $$\{T_n\}$$ **一致收敛**到 $$T$$，若 $$\Vert T_n-T\Vert \to 0$$；
- $$\{T_n\}$$ **强收敛**到 $$T$$，若 $$\forall x\in X,T_n x\to Tx$$；
- $$\{T_n\}$$ **弱收敛**到 $$T$$，若任取 $$x\in X, f\in Y'$$，$$f(T_nx)\to f(Tx)$$。

容易看出来一致收敛 $$\Longrightarrow$$ 强收敛 $$\Longrightarrow$$ 弱收敛，但是反向则不成立，可以举出对应的反例。

***例子 4***(强收敛 $$\nRightarrow$$ 一致收敛)：$$X=Y=\ell^2$$，$$T_n:\ell^2\to\ell^2$$ 有
$$
T_n: (x_1,x_2,\cdots) \mapsto (0,\cdots,0,x_{n+1},x_{n+2},\cdots)
$$
容易验证 $$T_n$$ 为有界线性算子，$$\Vert T_n\Vert=1$$。可以验证 $$T_n$$ 强收敛到 $$0$$ 算子，即 $$T_0x\equiv 0$$。但是 $$\Vert T_n-T_0\Vert=1\nrightarrow 0$$，即不满足一致收敛。

***例子 5***(弱收敛 $$\nRightarrow$$ 强收敛)：$$X=Y=\ell^2$$，$$T_n:\ell^2\to\ell^2$$ 有
$$
T_n:(x_1,x_2,\cdots)\mapsto(0_1,\cdots,0_n,x_1,x_2,\cdots)
$$
可以验证 $$T_n$$ 为有界线性算子，并且 $$\Vert T_n\Vert=1$$。是否有 $$T_n$$ 弱收敛到某个 $$T$$ 呢？考虑任意 $$f\in(\ell^2)'$$，都存在唯一的 $$z\in\ell^2$$，$$f(x)=\langle x,z\rangle$$，所以 $$f(T_nx)=x_1\overline{z_{n+1}}+x_2\overline{z_{n+2}}+\cdots$$，因此 
$$
|f(T_nx)|\le\sum_{k=1}^\infty |x_k|\cdot|z_{n+k}| \le \Vert x\Vert\left(\sum_{k=n+1}^\infty |z_k|^2\right)^{1/2} \to 0
$$
所以有 $$f(T_nx) \to 0$$ 对任意 $$f\in (\ell^2)'$$ 成立，因此 $$f(T_nx)\to f(T_0x)\equiv f(0)=0$$。所以 $$T_n$$ 弱收敛到 $$T_0=0$$ 算子，但是总有 $$\Vert T_nx\Vert=\Vert x\Vert\nrightarrow 0$$，因此 $$T_nx\nrightarrow T_0x$$，即不满足强收敛。

**命题**：对于一般有界线性算子，若 $$T_n$$ **一致收敛**到 $$T$$，则 $$T$$ 也是有界的，这是因为 $$\Vert T\Vert\le \Vert T-T_n\Vert+\Vert T_n\Vert \le \infty$$；若只能得到 $$T_n$$ **强收敛**到 $$T$$，那么 $$T$$ **不一定是有界**的。

***例子 6***(强收敛极限未必有界)：$$X=Y=\{(x_n),\exists N,\forall n\ge N, x_n=0 \}$$，考虑 $$T_n:X\to Y$$ 有
$$
\begin{aligned}
T_n:& (x_1,x_2,\cdots)\mapsto (x_1,2x_2,\cdots,nx_n,x_{n+1},x_{n+2},\cdots) \\
T:& (x_1,x_2,\cdots)\mapsto (x_1,2x_2,\cdots)
\end{aligned}
$$
那么 $$\Vert T_n\Vert=n$$，取可以验证对于 $$\forall x\in X$$，$$T_nx\to Tx$$，即 $$T_n$$ 强收敛到 $$T$$，但是 $$T$$ 不是有界算子。

那么什么情况下可以保证强/弱收敛极限也是有界算子呢？

> **定理**：设 $$X$$ 为 **Banach 空间**，$$Y$$ 为赋范空间，$$T_n\in B(X,Y),T:X\to Y$$ 为线性算子。设 $$T_n$$ **弱收敛**到 $$T$$，则 $$\sup_{n\ge1}\Vert T_n\Vert < \infty, T\in B(X,Y)$$ 并且 $$\Vert T\Vert \le \sup_{n\ge1}\Vert T_n\Vert <\infty.$$

**证明**：由于 $$T_n$$ 弱收敛到 $$T$$，即 $$\forall x\in X,f\in Y'$$ 都有 $$f(T_nx)\to f(Tx)$$，因此有 $$T_nx \stackrel{w}{\longrightarrow} Tx$$。那么根据序列弱收敛的性质，存在 $$c_x$$ 满足 $$\sup_n \Vert T_nx\Vert \le c_x$$，再由一致有界性原理，有 $$\sup_n \Vert T_n\Vert < \infty$$。

然后考虑 $$T$$，$$\forall x\in X$$，由 Hahn-Banach 定理的推论，都存在 $$f\in Y',\Vert f\Vert=1$$ 满足 
$$
\Vert Tx\Vert=|f(Tx)| = \lim_{n\to\infty} |f(T_nx)| \le \lim_{n\to\infty}\Vert T_nx\Vert
$$
因此 $$\Vert T\Vert\le \sup_n\Vert T_n\Vert.$$ 证毕。

> **定理**：设 $$X$$ 为 **Banach 空间**，$$Y$$ 为赋范空间，$$T_n,T\in B(X,Y)$$，则 $$T_n$$ **强收敛**到 $$T$$ **当且仅当**：
>
> 1. $$\sup_n \Vert T_n\Vert < \infty$$；
> 2. 存在 $$M\subset X,\overline{\text{span}M}=X$$，对 $$\forall x\in M, T_n(x)\to T(x).$$
>
> **NOTE**：这跟线性泛函弱星收敛的等价条件是完全一样的，证明省略。



## 4. 应用举例

***例子 7***(求积分的数值方法)：考虑实值函数 $$x\in C[a,b]$$，并赋予无穷范数，那么 $$(C[a,b],\Vert\cdot\Vert)$$ 为 Banach 空间，求 $$\int_a^b x(t)dt.$$

既然是在本节举的这个例子，那就要用到算子收敛性。先定义有界线性算子 $$f(x)=\int_a^b x(t)dt$$，$$\Vert f\Vert=b-a$$。我们现在的目标就是找一列有界线性泛函 $$f_n$$ 弱收敛到 $$f$$。回忆我们在学微积分的时候，往往是用分段的矩形面积求和来逼近积分。在 $$[a,b]$$ 上取 $$n+1$$ 个结点 $$a=t_{n,0}<t_{n,1}<\cdots<t_{n,n}=b$$，再取 $$n+1$$ 个实数 $$a_{n,0},\cdots,a_{n,n}$$，令
$$
f_n(x) = \sum_{k=0}^n a_{n,k} x(t_{n,k})
$$
$$f_n$$ 是 $$C[a,b]$$ 上的线性泛函，并且 $$\Vert f_n\Vert \le \sum_{k=0}^n|a_{n,k}|$$，另外我们总能够造出一个 $$x\in C[a,b]$$ 满足 $$x(t_{n,k})=\text{sgn}(a_{n,k})$$ 并且 $$\Vert x\Vert_\infty=1$$，此时就有 $$f(x)=\sum_{k=0}^n|a_{n,k}|$$，于是可以得到 $$\Vert f_n\Vert = \sum_{k=0}^n|a_{n,k}|$$。现在的问题就是我们能否找到合适的系数 $$a_{n,k}$$ 使得 $$f_n\stackrel{w}{\longrightarrow} f$$ ？

这里我们提出一个额外的要求，就是对于次数小于 $$n$$ 的多项式 $$p$$，需要 $$f_n(p)$$ 能获得精确积分结果，即 $$f_n(p)=\int_a^b p(t)dt$$。由于 $$\{1,t,\ldots,t^n\}$$ 构成次数小于 $$n$$ 的多项式空间的 Hamel 基，所以只需要验证对每个基有 $$f_n(e_k)= f(e_k)$$ 即可。这就要求
$$
\begin{cases}
\begin{matrix}
a_{n,0} & + & a_{n,1} & + & \cdots & + & a_{n,n} & = & b-a \\
a_{n,0}t_{n,0} & + & a_{n,1}t_{n,1} & + & \cdots & + & a_{n,n}t_{n,n} & = & \frac{b^2-a^2}{2} \\
& & & & \ldots & \\
a_{n,0}t_{n,0}^n & + & a_{n,1}t_{n,1}^n & + & \cdots & + & a_{n,n}t_{n,n}^n & = & \frac{b^{n+1}-a^{n+1}}{n+1}
\end{matrix}
\end{cases}
$$
上式左侧可以用 Vandermonde 矩阵表示，因此存在唯一解 $$a_{n,k},k=1,...,n$$。

接下来对于任意的 $$x\in C[a,b]$$，能否找到 $$a_{n,k}$$ 满足的条件使得 $$f_n(x)\to f(x)$$ 呢？根据 Stone-Weierstrass 定理，多项式的集合在 $$C[a,b]$$ 中是**稠密的**，因此对于任意次数 $$N$$ 的多项式 $$p$$ 总有 $$f_n(p)\to f(p)$$。那么再应用前面的定理（即只需要判断完全集 $$M\subset X$$ 中的元素是否满足条件即可），可以有如下结论

**定理(G.Polya)**：设数值积分 $$f_n$$ 满足前面对于有限次多项式的要求（即 $$a_{n,k}$$ 为 Vandermonde 矩阵方程的解）则任取 $$x\in C[a,b],f_n(x)\to f(x)$$ 当且仅当存在常数 $$C\ge0$$，使得任取 $$n\ge1$$，有 $$\sum_{k=1}^na_{n,k}\le C.$$




