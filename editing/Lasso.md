---
title: Variable Selection and Lasso
author: Keen
tag: statistical learning
---
### 线性回归模型
当我们的假设模型是线性回归模型时，我们认为自变量和因变量之间的关系是$ Y =\beta_0 + X\beta + \epsilon $，需要给出估计的方程是$ E(Y) =\beta_0 + X\beta$，其中给定的数据样本为$ \mathcal{D}:(x, y) = \{(x_i,y_i), i=1,2,...,n\} $，最终我们可以得到的方程的估计为 $ \hat Y =\hat \beta_0 + X \hat \beta$。对于样本$(x_i, y_i)$中自变量是含有多维特征值，即$x_i = (x_{i1}, x_{i2},...,x_{ip})$，所以需要估计的方程展开应该是$ E(Y) = \beta_0 + \beta_1 X_1 +...+ \beta_p X_p$。
### Variance and bias
正常情形下，我们通过最小二乘法来得到最优的参数，获得估计模型的参数$\hat \beta_0, \hat \beta_1,..., \hat \beta_p $，它的目的其实是得到使得损失函数$ loss =\frac{1}n\|y - \hat y\|^2_2$最小化的参数$\beta_0, \beta_1,...,\beta_p$。<br />
从模型的解释程度出发，可以将损失函数进行分解<br />
$$
\begin{align}
loss    
\end{align}
$$
损失函数体现了模型的误差，通过对损失函数的分解，可以看出估计模型误差的来源。<br />
$$
\begin{align}
loss &= \frac{1}{n} \|y-\hat y\|^2_2 \\
&= E(Y - \hat Y)^2 \\
&= E(E(Y) + \epsilon - \hat Y)^2 \\
&= E(E(Y) - \hat Y)^2 + var(\epsilon)\\
&=  E[E(Y) - E(Y|\mathcal{D}) + E(Y|\mathcal{D}) - \hat Y]^2 + var(\epsilon)\\
&= E[Y-E(Y|\mathcal{D})]^2 + [E(Y|\mathcal{D}) - \hat Y]^2+var(\epsilon) \\
&= Var(\hat Y) + Bias^2(\hat Y) +var(\epsilon) \\
&= variance + bias^2 + noise
\end{align}
$$
通过上述分解可以看出，估计模型的误差来源有三个，估计模型的方差，估计模型的偏差、噪声。
### 变量选择的原因 
一个很自然的想法，既然已经选择了使得损失函数最小的参数估计，那可以尽可能多的变量包含到假设模型中去，模型$Y \sim X_1, X_2,...,X_p$的模型空间包含了$ Y \sim X_1, X_2,...,X_{p-1}$ 的模型空间，可以获得理论上更优的解。
#### 1. 过拟合
变量越多，模型越复杂
#### 2. 维度灾难
### 常见的判别量
#### 1. AIC
#### 2. BIC
#### 3. adjusted r squared
### 变量选择的方法
#### Lasso
