## 3. 收敛性与完备性

这一部分则开始考虑 $$X$$ 中的元素序列，以及序列的极限是否存在、极限是什么的问题。之所以考虑序列这件事情，是因为我们实际中处理问题的时候往往是用序列去逼近一个元素，序列当中的每个元素可能是简单的，二最后去逼近的这个元素往往是不太显然或者比较复杂的东西。这样我们只需要证明序列中的元素满足某些性质，就能证明最后的极限具有某些特殊性质，更容易处理。

### 3.1 序列收敛性

我们对**序列收敛性**的定义是对于 $$x_n,x\in\mathbb{R}$$，称 $$x_n$$ 收敛到 $$x$$，记为 $$x_n\to x$$ ($$\lim_{n\to\infty} x_n=x$$)，若 $$\forall \varepsilon> 0,\exists N,\ \forall n\ge N$$，都有 $$|x_n-x|<\varepsilon$$。换一种表述方式就是在度量空间 $$(X,d)$$ 中，$$d(x_n,x)\to 0$$。

**注**：需要注意的是只有 $$x\in X$$，我们才能说 $$x_n\to x$$。例如取 $$X=(0,1),x_n=\frac{1}{n+1}$$，那么 $$x_n$$ 在 $$X$$ 中**不收敛**。

**命题**：若 $$x_n\to x$$，则 $$\{x_n\}_{n\ge1}$$ 为有界集合，且 $$x$$ 唯一。

**定理**：度量空间 $$(X,d)$$，有 $$M\subset X$$，那么

- $$x\in \bar{M} \iff \exists x_n\in M,\ x_n\to x$$；
- $$M$$ 为**闭集** $$\iff \forall x_n\in M$$，设 $$x_n\to x\in X$$，则 $$x\in M$$（即**闭集对极限封闭**）。

证明：第一条应用定义，第二条应用第一条的结论。细节略。

### 3.2 柯西列与完备性

**定义**：$$x_n\in X$$，称 $$x_n$$ 为**柯西列**，若 $$\forall \varepsilon > 0,\exists N, \forall m,n\ge N$$，则 $$d(x_m,x_n)<\varepsilon$$。称 $$X$$ 是**完备**的，若 $$\forall x_n\in X$$ 为柯西列，则 $$\exists x\in X,x_n \to x$$。

**注**：实际上，收敛列一定是柯西列，即 $$\{收敛列\} \subset \{柯西列\}$$；而如果 $$X$$ 又是完备的，那么说明柯西列也一定是收敛列。因此 $$X$$ 完备 $$\iff \{柯西列\}=\{收敛列\}$$。

**命题**：$$x_n$$ 为柯西列，则 $$\{x_n,n\ge 1\}$$ 为有界集。

***例子 1***：$$(\mathbb{R},d_1)$$ 完备；$$(\mathbb{K}^n, d_p)$$ 完备；$$(\ell^\infty, d_\infty)$$ 完备；$$(\ell^p,d_p)$$ 完备；$$(C[a,b],d_\infty)$$ 完备。

***证明***：证明完备性的套路：

1. 任取柯西列 $$x_n\in X$$；
2. 找到可能的极限 $$x$$；
3. 证明 $$x\in X$$；
4. 证明 $$x_n\to x$$。

***例子 2***：$$(C[a,b], d_p)$$ **不完备**（反例如下图所示）；$$\mathbb{Q}$$ 不完备（因为不是闭集）；$$c_{00}$$ （有限个元素不为零的序列）不完备。

![](https://raw.githubusercontent.com/Glooow1024/ImgHosting/master/hexo/2020/2-example.jpg)

 **定理**：度量空间 $$(X,d)$$

- $$\forall Y\subset X$$ 为完备的，则 $$Y$$ 为闭集；
- 若 $$(X,d)$$ 完备，则 $$\forall Y\subset X$$ 完备 $$\iff Y$$ 为闭集。

证明：第一条应用闭集对极限封闭的性质；第二条反向应用 $$(X,d)$$ 完备的性质。细节略。

**定理**：若 $$x_n\in C[a,b],x_n\rightrightarrows x$$（一致收敛），则 $$x\in C[a,b]$$。



## 4. 映射与连续性

前面从单个度量空间的角度来考虑元素的性质，现在考虑两个度量空间的对应关系，也就是映射。

对于实空间的映射 $$f:(a,b)\to \mathbb{R}$$，我们对连续性的定义为：$$f$$ 在 $$t_0\in(a,b)$$ 处连续，若 $$\lim_{t\to t_0}f(t)=f(t_0)$$。由于我们在度量空间中已经定义了距离 ，因此可以将其推广至度量空间。

假设有度量空间 $$(X_1,d_1)$$ 和 $$(X_2,d_2)$$，映射 $$T:X_1 \to X_2$$。

**定义**：称映射 $$T$$ 在 $$t=t_0$$ 处**连续**，若 $$\forall \varepsilon > 0,\ \exists \delta > 0$$，使得 $$\forall t\in X_1,\ d_1(t,t_0)<\delta$$，都有 $$d_2(Tt, Tt_0)<\varepsilon$$。若 $$T$$ 在 $$\forall t\in X_1$$ 处都连续，则称 $$T$$ 为**连续映射**。

***例子 1***：若 $$(X_1,d_1)$$ 为离散度量空间，那么任意 $$T:X_1 \to X_2$$ 一定是连续映射。证明只需要套用定义，取 $$\delta=1/2$$ 即可。

***例子 2***(Lipschitz 连续)：$$\exists c>0,\ \forall s,t\in X_1$$ 都有 $$d_2(Ts,Tt)< c d_1(s,t)$$，那么 $$T$$ 是连续映射。

**定理**：$$T$$ 为**连续映射** $$\iff \forall G\subset X_2$$ 为开集，那么 $$T^{-1}(G)=\{x\in X_1, Tx\in G\}$$ 是 $$X_1$$ 中的开集。

**证明**："$$\Longrightarrow$$"：若已知 $$T$$ 连续，$$G$$ 为开集

$$G$$ 为开集，就有 $$\forall x_0\in T^{-1}(G),\exists \varepsilon > 0,\ B(Tx_0,\varepsilon)\subset G$$

由于 $$T$$ 连续，则一定 $$\exists \delta > 0$$，使得 $$\forall x\in B(x_0, \delta)$$，都有 $$Tx\in B(Tx_0,\varepsilon)$$，因而 $$B(x_0,\varepsilon)\subset X_1$$

故 $$T^{-1}(G)$$ 为开集。

"$$\Longleftarrow$$"：假设 $$\forall G\subset X_2$$ 为开集，$$T^{-1}(G)$$ 在 $$X_1$$ 中也是开集，那么套用连续映射的定义，就能证明 $$T$$ 为连续映射。

证毕。

**推论**：$$T$$ 为**连续映射** $$\iff \forall F\subset X_2$$ 为闭集，那么 $$T^{-1}(F)=\{x\in X_1, Tx\in F\}$$ 是 $$X_1$$ 中的闭集。

**定理**：$$T$$ 在 $$x_0$$ 处连续 $$\iff \forall x_n\in X_1, x_n\to x_0$$，则 $$Tx_n \to Tx_0$$。

**证明**："$$\Longrightarrow$$"：应用定义；

"$$\Longleftarrow$$"：反证法，假设 $$T$$ 在 $$x_0$$ 处不连续，

那么 $$\exists \varepsilon_0 > 0,\forall \delta >0, \exists x\in B(x_0, \delta)$$，使得 $$d(Tx_0, Tx) > \varepsilon_0$$

可以取 $$\delta = 1/n$$，由此构造出一个序列 $$x_n \in B(x_0,1/n)$$，

可以知道 $$x_n\to x_0$$，但是却有 $$d(x_n,x_0) \ge \varepsilon_0$$，与假设矛盾。

证毕。

**推论**：$$T:X_1\to X_2$$ 处处连续 $$\iff \forall x_n\to x, Tx_n \to Tx$$。

