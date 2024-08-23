---
title:      "Summary of Group Theory"
date:       2024-08-17
categories: [Mathematics, Algebra]
tag: [Group Theory]
toc: true
math: true
comment: true
description: This blog mainly records the notes I took while studying group theory, covering topics such as finite groups, Lie groups, and their representations.
---
# 前言
本文是对韩其智、孙洪洲所著《群论》(1989年出版,后无再版)一书概念、定理的*摘录*,力求简洁明了,略去相关的数学证明.除正文以外,本文还有如下环境

> 这用来表示“建议”或者“提示”,通常与本文内容关系不大,仅仅起到提示的作用.
{: .prompt-tip }

> 这用来表示作者(即韩和孙)的“注记”,是书里面提到过的,并且有助于深刻理解的内容.
{: .prompt-info }

> 这用来表示我的“注记”,是我(Collapsar)的理解,未必准确到位,读者自行参考.
{: .prompt-warning }

> 这用来表示“警告”,常常出现在某些易错、易混淆的内容后面.
{: .prompt-danger }

下面是各章节维护更新的情况
  - [x] 群的基本知识
  - [x] 群表示论的基础
      - Aug 23-Aug 24,更新2.1-2-3节
      - Aug 25-Aug 26,更新2.4-2.6节
  - [ ] 点群
  - [ ] 转动群
  - [ ] 对称群与酉群
  - [ ] 李群基础
  - [ ] 李代数基础
  - [ ] 李代数的表示
  
<!-- [東雲正樹, 群论 (Group Theory) 终极速成](https://zhuanlan.zhihu.com/p/294221308)
- [韩其智&孙洪洲,群论](https://github.com/Collapsar0615/MyNotes/tree/main/Group%20Theory)
- 刘玉鑫,物理学家用李群李代数
- 梁灿彬,李群和李代数
- Brian Hall,Lie Groups,Lie Algebras,and Representations(GTM 222)  
-->

# 群的基本知识
# 群表示论的基础

## 群表示
### 线性空间
线性空间或者向量空间$V=\{x,y,z,
    \cdots\}$是定义在数域$K$(如实数域$\mathbb{R}$或者复数域$\mathbb{C}$)上的向量集合,其中定义了加法和数乘两种运算,$\forall x,y,z\in V;a,b,c\in K$.向量加法和数乘具有封闭性,而且满足:

加法:
- 交换律:$x+y=y+x$ .
- 结合律:$x+(y+z)=(x+y)+z$.
- 存在唯一的$0$元素,$x+0=x$.
- $\forall x,$存在唯一的$(-x)$,使得$x+(-x)=0$.

数乘:
- $ 1\cdot x=x $.
- $ (ab)x=a(bx) $.
- $a(x+y)=ax+ay$.
- $(a+b)x=ax+bx$.

> 若把加法运算看作群的乘法,线性空间$V$构成一个可交换的加法群.
{: .prompt-info }

### 线性变换
设$V$是数域$K$上的线性空间,线性变换$A$是将$V$映入$V$的线性映射,即$\forall x,y \in V,a \in K$有
$$
\begin{align*}
A:V &\to V,\ A(x) \in V;\\
A(ax+y)&=aA(x)+A(y).
\end{align*}
$$



>  设$A$和$B$是从$V$到$V$的线性变换,则可定义线性变换的数乘、加法和乘法为:
   $$
   \begin{aligned}
            (a A)(x)&=a(A(x)), \\
           (A+B)(x)&=A(x)+B(x), \\
        (A B)(x)&=A(B(x)) .
    \end{aligned}$$
{: .prompt-info }