---
title: Cauchy-Schwarz不等式的证明
---

Cauchy-Schwarz不等式的表述为：存在非零向量$\vec x , \vec y \in \mathbb{R}^n$使得 $|\vec x \cdot \vec y| \leq \\| \vec x\\| \\| \vec y\\| $，当且仅当$\vec x = c \vec y $ 时等号成立。

证明如下：

首先构造一个关于$t$的函数 $$ p(t)=\\|t\vec y-\vec x\\|^2 \geq 0 .$$
根据公式 $\\|\vec v\\|^2 = \vec v\cdot \vec v$, 上式可改写为
$$ p(t)=(t\vec y-\vec x)\cdot (t\vec y-\vec x) .$$
将其展开，有：
$$ p(t)=t\vec y\cdot t\vec y- \vec x\cdot t\vec y -t\vec y\cdot\vec x +\vec x\cdot \vec x .$$
接着，有
$$ p(t)=(\vec y \cdot \vec y)t^2 - 2(\vec x \cdot \vec y)t +\vec x\cdot \vec x \geq 0 .$$
假设$a=(\vec y \cdot \vec y), b=2(\vec x \cdot \vec y), c=\vec x\cdot \vec x, $ 那么 $p(t)=at^2-bt+c $ 对于任意的$t$都大于等于0.
因此有，
$$p(\frac{b}{2a})=a(\frac{b}{2a})^2-b\frac{b}{2a}+c \geq 0. $$
化简得，
$$4ac \geq b^2.$$
代入原来的$x$,$y$, 有：
$$4 (\\|\vec y\\|^2 \\|\vec x\\|^2) \geq (2(\vec x\cdot \vec y))^2.$$
即
$$\\|\vec y\\|^2 \\|\vec x\\|^2 \geq (\vec x\cdot \vec y)^2 .$$
对两边同时开方，有
$$\\|\vec y\\| \\|\vec x\\| \geq \|\vec x\cdot \vec y\| .$$

当$\vec x=c\vec y$, 有
$$\|\vec x\cdot\vec y\|=\|c\vec y\cdot\vec y\|=\|c\|\|\vec y\cdot\vec y\|=\|c\| \\|\vec y\\|^2$$
$$=\|c\|\\|\vec y\\| \\|\vec y\\| =\\|c\vec y\\| \\| \vec y\\| = \\|\vec x\\| \\| \vec y\\|. $$

## Reference:
https://www.khanacademy.org/math/linear-algebra/vectors-and-spaces/dot-cross-products/v/proof-of-the-cauchy-schwarz-inequality


