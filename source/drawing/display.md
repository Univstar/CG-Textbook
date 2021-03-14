# 显示技术

本书的第一个专题将围绕简单图形绘制展开，我们将介绍如何在屏幕上画出我们想要的二维图形或图像。本专题所介绍的技术和方法，将成为渲染三维场景的基础。如同绘画需要先准备颜料和纸、笔，为了在屏幕上绘制图形，也必须先从显示技术讲起。

## 颜色空间

我们之所以能区分世间万物，依赖于不同的物体在不同的光照和远近下所产生的颜色上的不同，这也是为什么我们能在彩色相片中看出比黑白相片更多的细节。在进行图形绘制之前，我们必须调好我们的“色盘”——然而，颜色的种类是否是无限的？面对如此多种多样的颜色，我们又该如何表示、储存和显示它们呢？

### 颜色的本质

对光学有了解的读者一定知道：太阳光透过棱镜可以折射出赤橙黄绿青蓝紫的连续色谱，而这正是彩虹形成的原理。这一条简单的常识至少向我们透露了下列两条信息：

1. 不同波长的光线具有不同的颜色；

2. 一种颜色（例如阳光的“白色”）可能是由多种颜色组合而成的。

````{prf:theorem} Orthogonal-Projection-Theorem
:label: my-theorem

Given $y \in \mathbb R^n$ and linear subspace $S \subset \mathbb R^n$,
there exists a unique solution to the minimization problem

$$
\hat y := \mathop{\arg\min}_{z \in S} \|y - z\|
$$

The minimizer $\hat y$ is the unique vector in $\mathbb R^n$ that satisfies

* $\hat y \in S$

* $y - \hat y \perp S$


The vector $\hat y$ is called the **orthogonal projection** of $y$ onto $S$.
````

测试引用功能：{cite}`economic-dynamics-book`

测试中 English 混排
