# PAC附加部分



1.证明: 对于**给定的**假设 $h$​​ ,泛化误差是经验误差的期望



证：由于样本是 i.i.d.，故对  $\forall~x \in $ Sample $S$​
$$
\underset{S \sim \mathcal{D}^{m}}{\mathbb{E}}\left[\widehat{R}_{S}(h)\right]=\frac{1}{m} \sum_{i=1}^{m} \underset{S \sim \mathcal{D}^{m}}{\mathbb{E}}\left[1_{h\left(x_{i}\right) \neq c\left(x_{i}\right)}\right]=\frac{1}{m} \sum_{i=1}^{m} \underset{S \sim \mathcal{D}^{m}}{\mathbb{E}}\left[1_{h(x) \neq c(x)}\right]
$$
进一步地
$$
\underset{S \sim \mathcal{D}^{m}}{\mathbb{E}}\left[\widehat{R}_{S}(h)\right]=\underset{S \sim \mathcal{D}^{m}}{\mathbb{E}}\left[1_{h(x) \neq c(x)}\right]=\underset{x \sim \mathcal{D}}{\mathbb{E}}\left[1_{h(x) \neq c(x)}\right]=R(h)
$$



2.realizable：

 There is at least one hypothesis in the hypothesis set under consideration that achieves zero expected error



3.Hoeffding inequality

1.  $x_i\in [0,1],i = 1,2,\cdots,n$ 为独立随机变量 

$$
\begin{aligned}
&P\left(\frac{1}{m} \sum_{i=1}^{m} x_{i}-\frac{1}{m} \sum_{i=1}^{m} \mathbb{E}\left(x_{i}\right) \geqslant \epsilon\right) \leqslant \exp \left(-2 m \epsilon^{2}\right) \\
&P\left(\left|\frac{1}{m} \sum_{i=1}^{m} x_{i}-\frac{1}{m} \sum_{i=1}^{m} \mathbb{E}\left(x_{i}\right)\right| \geqslant \epsilon\right) \leqslant 2 \exp \left(-2 m \epsilon^{2}\right)
\end{aligned}
$$



3.由 Hoeffding inequality 直接推得的泛化误差界

Corollary $2.11$ (Generalization bound - single hypothesis) **Fix a hypothesis** $h: X \rightarrow\{0,1\}$. Then, for any $\delta>0$, the following inequality holds with probability at least $1-\delta:$
$$
R(h) \leq \widehat{R}_{S}(h)+\sqrt{\frac{\log \frac{2}{\delta}}{2 m}}
$$

4.McDiarmid 不等式

 若 $x_{1}, x_{2}, \ldots, x_{m}$ 为 $m$ 个独立随 机变量, 且对任意 $1 \leqslant i \leqslant m$, 函数 $f$ 满足
$$
\sup _{x_{1}, \ldots, x_{m}, x_{i}^{\prime}}\left|f\left(x_{1}, \ldots, x_{m}\right)-f\left(x_{1}, \ldots, x_{i-1}, x_{i}^{\prime}, x_{i+1}, \ldots, x_{m}\right)\right| \leqslant c_{i}
$$
则对任意 $\epsilon>0$, 有
$$
\begin{aligned}
&P\left(f\left(x_{1}, \ldots, x_{m}\right)-\mathbb{E}\left(f\left(x_{1}, \ldots, x_{m}\right)\right) \geqslant \epsilon\right) \leqslant \exp \left(\frac{-2 \epsilon^{2}}{\sum_{i} c_{i}^{2}}\right) \\
&P\left(\left|f\left(x_{1}, \ldots, x_{m}\right)-\mathbb{E}\left(f\left(x_{1}, \ldots, x_{m}\right)\right)\right| \geqslant \epsilon\right) \leqslant 2 \exp \left(\frac{-2 \epsilon^{2}}{\sum_{i} c_{i}^{2}}\right)
\end{aligned}
$$
