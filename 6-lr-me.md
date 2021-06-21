Logistic regreesion 是统计学习中的经典**分类方法**。

最大熵(maximum entropy) 是概率模型学习的一个准则，将其推广到分类问题就得到最大熵模型。

逻辑回归模型和最大熵模型都属于**对数线性模型**。

本章先介绍逻辑回归，然后最大熵模型，最后介绍他们的学习算法 (迭代尺度算法和拟牛顿法)。

研究一个随机变量，不只要看它能取哪些值，更重要的是它取各种值的概率如何！[here](https://www.huaweicloud.com/articles/aca927073280aaa89d5a269107f8afeb.html)
### 概率函数
#### 离散型随机变量
- 概率函数，就是用函数的形式来表达概率。

$p_i = P(X=a_i)$ (i = 1,2,3,4,5,6)

在这个函数里，自变量(X)是随机变量的取值，因变量（$p_i$)是取值的概率。它代表了每个取值的概率，所以顺理成章的它就叫做了X的概率函数。从公式上看概率函数一次只能表示一个取值的概率。

- 概率分布： 随机变量的值分布和概率分布列表
- 概率分布函数：就是把概率函数累加

The **probability** that an event will occur is the fraction of times you expect to see that event in many trials.
The **odds** are defined as the probability that the event will occur divided by the probability that the event will not occur.




## 逻辑回归
