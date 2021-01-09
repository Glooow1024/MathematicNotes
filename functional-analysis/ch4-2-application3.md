
## 3. Riemann-Stieltjes积分

称函数 $$\omega:[a,b]\to\mathbb{K}$$ 为**有界变差函数**，若存在常数 $$C\ge0$$，使得任取 $$[a,b]$$ 的分划
$$
a=t_0<t_1<\cdots<t_n=b
$$
都有 $$\sum_{i=1}^n |\omega(t_i)-\omega(t_{i-1})|\le C$$。记所有 $$[a,b]$$ 上的有界变差函数构成的集合为 $$BV[a,b]$$。并定义 $$[a,s],a\le s\le b$$ 上的**全变差**为
$$
\text{Var}_{[a,s]}(\omega)=\sup\sum_{i=1}^n |\omega(t_i)-\omega(t_{i-1})|
$$
其中上确界是对所有 $$[a,s]$$ 上的分划来取。

**命题**：若 $$\omega:[a,b]\to\mathbb{R}$$ 单调，则 $$\omega\in BV[a,b]$$，并且此时有 $$\text{Var}_{[a,b]}(\omega)=|\omega(b)-\omega(a)|.$$

**命题**：若 $$\omega:[a,b]\to \mathbb{R}$$ 为有界变差的，则存在 $$\omega_1,\omega_2$$ 单调递增，使得 $$\omega=\omega_1-\omega_2.$$

证明：取 $$\omega_1(t)=\text{Var}_{[a,t]}(\omega)$$，那么易证 $$\omega_1$$ 是单调递增的。取 $$\omega_2=\omega-\omega_1$$ 也是递增的，这是因为 $$\forall t<s$$，$$t,x\in[a,b]$$ 都有 
$$
\begin{aligned}
\omega_2(s)-\omega_2(t)
&=\text{Var}_{[a,s]}(\omega)-\text{Var}_{[a,t]}(\omega)-\omega(s)+\omega(t) \\
&=\text{Var}_{[t,s]}(\omega)-(\omega(s)-\omega(t)) \ge 0
\end{aligned}
$$
其中第二个等号用到了下面的引理。

**引理**：$$\text{Var}_{[a,s]}(\omega)=\text{Var}_{[a,t]}(\omega)+\text{Var}_{[t,s]}(\omega).$$

证明：略。

在 $$BV[a,b]$$ 上定义范数 $$\Vert \omega\Vert_{bv}=\text{Var}_{[a,b]}(\omega)+|\omega(a)|$$，则可以证明 $$\Vert\cdot\Vert_{bv}$$ 为 $$BV[a,b]$$ 上的范数，并且 $$BV[a,b]$$ 为 Banach 空间。

对 $$\forall \omega\in BV[a,b], x\in C[a,b]$$，若 $$\mathcal{P}$$ 为 $$[a,b]$$ 的分划 $$a=t_0<t_1<\cdots<t_n=b$$，令 
$$
S(x,\omega,\mathcal{P})=\sum_{i=1}^n x(t_{i-1})(\omega(t_i)-\omega(t_{i-1}))
$$
是 $$x$$ 关于有界变差函数 $$\omega$$ 和分划 $$\mathcal{P}$$ 的 Darboux 和。记 $$\eta(\mathcal{P})=\max_i (t_i-t_{i-1}) \to 0$$，若存在唯一的 $$A\in\mathbb{K}$$ 使得 $$S(x,\omega,\mathcal{P})\to A$$，则称 $$A$$ 为 $$x$$ 关于 $$\omega$$ 的 Riemann-Stieltjes 积分，记为
$$
A = \int_a^b x(t)d\omega(t).
$$
定义线性泛函 $$\phi_{\omega}:C[a,b]\to\mathbb{K}$$ 为
$$
\phi_\omega(x)=\int_a^b x(t)d\omega(t)
$$
则 $$\phi_\omega\in C[a,b]'$$，并且有 $$\Vert \phi_\omega\Vert\le \text{Var}_{[a,b]}(\omega)$$。

**定理**：$$\forall \phi\in C[a,b]'$$，$$\exists! \omega\in BV[a,b]$$，满足 $$\omega(a)=0$$，$$\forall x\in C[a,b]$$，$$\phi(x)=\int_a^b x(t)d\omega(t)$$，此时有 $$\Vert \phi\Vert=\Vert\omega\Vert_{bv}.$$

证明：略。


