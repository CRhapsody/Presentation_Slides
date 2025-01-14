### PAC讲义

PPT1:

 从理论上解决 ：什么问题可以被学习算法解决，什么不可以或者比较困难？有没有统一的模型可以回答这些问题

复杂度：

计算复杂度

样本复杂度：学习需要样本，样本数量越大，预测结果越可靠。所以需要考虑样本的复杂度，即多少样本能满足学习

错误：学习发生错误的一个可能性，或者误差的一个界是怎么样的



PPT3：

C:用支集表实



PPT4:

H:学习算法所收集的它认为是概念的集合



1.首先，一般C是不等于H的，因为学习算法很多时候不知道概念类应该是啥。比如线性分类和二阶分类

2.为什么是估计c呢

(1) 获得的训练集 $S$ 往往仅包含有限数量的样例, 因此通常会存在一些在 $S$ 上“等效”的假设, 学习算法无法区别这些假设

(2) 从分布 $D$ 采样得到 $S$ 的过程有一定的偶然性, 即便对同样大小的不同训练集, 学得结果也可能有所不同.



PPT5:

**加一张证明**



PPT6：

PCA定义：对任意的采样S



PPT7:

1.首先，定义中学习算法学习的是整个概念集的一个情况，而不是对单独的目标概念。我们注意的是，我们在学习之前是不知道我们要学习的目标概念是什么的，但是我们有时可以知道概念集是什么（待会儿我举一个例子）

2.最后关于复杂度，根据定义，其实我们还应该考虑两个部分：表实概念的复杂度和表实样本的复杂度



PPT8：

实际上这两个部分，在确定问题时，都会统一确定，所以样本复杂度的最关键的两个变量，是准确率，和置信度倒数这两个变量



PPT9：

问题：想学习平面中的一个矩形面

样本空间是平面，样例是里面的点集



PPT10：

简单的方法:不断举例平面中的点，并标记它们的标记，在R中记1，不在就记0，最后我们输出的假设是，最小的能包住所有标记为1的样例点的矩形

那么这样的假设的一个误差是多少呢，或者说，这个误差大于 $\epsilon$ 的概率是多少呢



PPT11：

我们定义概率，P[R]是由R（target concept）定义的一个概率密度函数，它指的是根据一定分布从平面中采样，最后落到R中的概率

假设它大于 $\epsilon$ ，否则这是一个trivial的问题，因为你怎么学，它的误差都是小于 $\epsilon$ 的

这时候我们从矩形R的四周定义4个小矩形



PPT12:

由于我们学习算法得到的假设，它的误差只会发生在 R-R‘中，从几何上也就是

念PPT，解释一下不等式



PPT13：

念PPT

我们从这个例子中可以看出我们定义的合理性：样本复杂度为什么要求是准确率和置信度倒数的多项式



PPT14：

念PPT



PPT15：

接下来我们分情况，首先讨论假设空间有限，并且学习算法可分的情况下

学习算法一致的定义：我觉得有两种定义方式

1.目标概念属于假设空间。

由于目标概念属于假设空间，存在一个假设，对所有的样本，经验误差等于0；所以我们可以在学习的时候，有理由以经验误差等于0的方法，不断的采样，让学习算法得到的假设不断的逼近目标概念。

2.经验误差等于0

因为我们在有一些学习算法的学习过程中，由于我们算法本身的一个性质（比如学习矩形），它的经验误差都是等于0，对于这样的问题，我们想求它的一个准确率或者置信度。由于这样的样本是任意取的，所以它此时目标函数一定是属于假设空间的



PPT16-17：

照着念



PPT18：

这里由于学习算法是一致的，那么这个算法自然是ERM的



PPT19：

再举一个例子：问题是求布尔字符的合取

这里的目标概念是：最多由n个布尔字符连接的式子，目标集是所有的这样的式子构成的集合

样例为一个n元向量，每个向量的分量为0或1，它的标记为正或负，正例和负例的含义是不一样的



PPT21-22：

照着念



PPT23：

再前面加一张Hoeffding不等式

添一张不是一致界的PPT



不可以，这是因为我们由采样得到的假设，是随着采样的变化而随之改变的，也就是说这是一个随机变量，而上面的界，是关于一个固定的假设的上界。并且这个时候，经验误差的期望是一个常数，而泛化误差是一个随机变量，也就是说他们不相等。我们再返回去看一下他们俩相等的证明。

所以，我们刚才得到只是对固定假设的一个界，但是我们想求的是所有假设，这样一个函数族的一致界，所以不能直接用上面那个不等式，那么如何求一致界呢



PPT24:





