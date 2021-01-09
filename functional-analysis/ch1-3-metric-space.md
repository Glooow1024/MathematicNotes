## 5. Banach 不动点定理

不动点想必大家在别的地方都或多或少听说过或者用过，应该是解决很多问题的重要工具。在这一部分的内容里面则可以看到，前面讲的序列收敛性、映射在不动点定理当中的应用。

**定义**：考虑 $$X\ne\varnothing, T:X\to X$$，若 $$x_0\in X,Tx_0=x_0$$，则称 $$x_0$$ 为 $$T$$ 的**不动点**。

**定义**：$$T:X\to X$$，假设 $$\exists 0\le \alpha < 1$$，使得 $$\forall x,y\in X$$，都有 $$d(Tx,Ty) \le \alpha d(x,y)$$，则称 $$T$$ 为**压缩映射**。

**定理(Banach不动点定理)**：假设 $$(X,d)$$ 为**非空、完备**度量空间，$$T:X\to X$$ 为压缩映射，则 $$T$$ **存在唯一**的不动点。

**证明**：考虑 $$x_0\in X,x_1=Tx_0,\cdots,x_n=Tx_{n-1},\cdots$$，那么可以首先证明 $$x_n$$ 为柯西列，进而存在收敛值 $$x$$。 由于 $$d(x_n,x_{n+1})=d(x_n,Tx_n)\to 0$$，从而趋向于 $$x=Tx$$。之后再证明唯一性。证毕。

**定理**：假设 $$(X,d)$$ **非空完备**，$$T:X\to X$$，设 $$\exists m\ge1$$，$$T^m$$ 为压缩映射，则 $$\exists! x\in X$$ 使得 $$Tx=x$$。

**证明**：只需要证明 $$S=T^m$$ 的不动点都是 $$T$$ 的不动点，反之 $$T$$ 的不动点也都是 $$S$$ 的不动点即可。

由不动点定理可知，$$S$$ 存在唯一一个不动点，记为 $$y_0$$，即 $$Sy_0=y_0$$，那么 $$STy_0=T^{m+1}y_0=TSy_0=Ty_0$$，即 $$Ty_0$$ 也是 $$S$$ 的不动点，因此一定有 $$Ty_0=y_0$$，即 $$y_0$$ 也是 $$T$$ 的不动点。假设 $$z_0$$ 是 $$T$$ 的不动点，那么很容易证明他也是 $$S$$ 的不动点。因此 $$T$$ 存在唯一不动点。证毕。

***例子 1***：$$c>0$$，求 $$\sqrt{c}$$ 的数值解。可以用数值迭代，取 $$f(x)=(x+\frac{c}{x})/2,D=[\sqrt{c},+\infty)$$，求不动点即可。

***例子 2***：$$(X=\mathbb{K}^n,d_\infty),C\in\mathbb{K}^{n\times n},b\in\mathbb{K}^n$$，映射 $$Tx=Cx+b$$。容易证明若 $$\forall i,\sum_j|a_{ij}|<1$$，则 $$T$$ 为压缩映射。

***例子 3***：考虑 $$(t_0,x_0)\in \mathbb{R}^2,a,b>0$$，考虑矩形 $$R=[t_0-a,t_0+a]\times[x_0-b,x_0+b]$$，连续函数 $$f:R\to\mathbb{R}$$，假设存在 $$k\ge0,|f(t,u)-f(t,v)|\le k|u-v|,\forall (t,u),(t,v)\in R$$。考虑初值问题
$$
(P):\begin{cases}
x'(t)=f(t,x(t)) \\
x(t_0)=x_0
\end{cases}
$$
求上述初值问题的解 $$x(t)\in C[t_0-\beta,t_0+\beta],0<\beta\le a$$。

***解***：首先给出结论：如果给定 $$c=\max_{(t,x)\in R}|f(t,x)|,0<\beta<\min\{a,\frac{b}{c},\frac{1}{k}\}$$，那么存在唯一的 $$x\in C^1[t_0-\beta,t_0+\beta]$$，使得当 $$t\in[t_0-\beta,t_0+\beta]$$ 时，有 $$x(t)\in[x_0-b,x_0+b]$$ 且 $$x$$ 满足方程 $$(P)$$。下面给出证明。

由于 $$x'(t)=f(t,x(t)) \Longrightarrow \int_{t_0}^t x'(\tau)d\tau=\int_{t_0}^t f(\tau,x(\tau))d\tau \Longrightarrow  x(t)=x_0+\int_{t_0}^t f(\tau,x(\tau))d\tau$$，

可以证明 $$|x(t)-x_0|\le c\beta <b \Longrightarrow (t,x(t))\in R$$。

$$(X,d_\infty)$$ 完备，取 $$M=\bar{B}(x_0,c\beta)$$ 为闭集，因此 $$M$$ 为完备的，

取 $$Tx=x_0+\int_{t_0}^t f(\tau,x(\tau))d\tau$$，也可以证明 $$d_\infty(Tx,x_0)\le c\beta \Longrightarrow Tx\in M$$，即 $$T:M\to M$$，

又容易证明 $$T$$ 为压缩映射，因而存在唯一的 $$x\in M$$ 使得 $$Tx=x$$，只需要迭代即可获得 $$x(t)$$。

***例子 4(隐函数存在定理)***：略。



## 6. 小结

这一章当中讲解了度量空间、开集闭集、序列收敛性、柯西列、集合完备性、映射与连续性，以及最后的Banach不动点定理。现在我们已经完成了度量空间中的内容，你能够回答文章开头的问题了吗？对于度量空间这个概念有什么新的理解吗？