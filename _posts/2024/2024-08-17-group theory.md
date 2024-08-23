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
      - Aug 23,更新2.1节和2-2节(到酉表示)
      - Aug 24
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
\begin{aligned}
A:V &\to V,\ A(x) \in V;\\
A(ax+y)&=aA(x)+A(y).
\end{aligned}
$$

> - 设$A$和$B$是从$V$到$V$的线性变换,则可定义线性变换的数乘、加法和乘法为:
>
$$
   \begin{aligned}
            (a A)(x)&=a(A(x)), \\
           (A+B)(x)&=A(x)+B(x), \\
        (A B)(x)&=A(B(x)) .
    \end{aligned}
$$
>
> - 若线性变换$A$还是把$V$映入$V$的一一对应满映射,则存在$A$的逆线性变换$A^{-1}$.
{: .prompt-info }
### 复一般线性群
设 $V$ 为 $n$ 维复向量空间, 当定义乘法为连续两次线性变换时,$V$ 上全部非 奇异线性变换构成一个群, 称为 $n$ 维复一般线性群 $G L(n, C)$或者$G L(V, C)$.其中,单位元素为$V$上的恒等变换,互逆元素为互逆变换.

> - 如果在 $V$ 中选一组基 $\left(e_1, e_2, \cdots, e_n\right), V$ 中非奇异线性变换就表示 $n \times n$ 非奇异复矩阵. 因此群 $G L(n, C)$ 也 可定义 为 $n \times n$ 非奇异复矩阵所构成的群.这个群的乘法就是矩阵乘法.
> - $V$上线性变换群$L(V,G)$是$V$上非奇异线性变换构成的群,它是群$GL(V,C)$的子群.
{: .prompt-info }

### 线性表示
- 群 $G$ 到线性空间 $V$ 上线性变 换 群 $L(V, C)$ 的 同态映射 $A$,称为 $G$ 的一个线性表示或者简称表示, $V$ 称为表示空间.当 $V$ 的维数是 $n$ 时，表示 $A$ 的维数也是 $n$.  即

$$
A: G \rightarrow L(V, C).
$$

对 $g_\alpha \in G$, 有 $A\left(g_\alpha\right) \in L(V, C)$ 与之对应, 而且保持 $G$ 的乘 法不变.即对 $g_\alpha, g_\beta \in G$, 有

$$
A\left(g_\alpha g_\beta\right)=A\left(g_\alpha\right) A\left(g_\beta\right) .
$$

> 如在表示空间 $V$ 选一组基, 线性变换群就和矩阵群同构. 因此群 $G$ 在表示空间 $V$ 的线性表示也可定义为 $G$ 到 $n \times n$ 矩 阵群的同态映射 $A$:$\forall g_\alpha \in G$, 有非奇异矩阵$A\left(g_\alpha\right)$ 与之对应,且对 $g_\alpha, g_\beta \in G$, 矩阵乘法保持
>
$$
A\left(g_\alpha g_\beta\right)=A\left(g_\alpha\right) A\left(g_\beta\right) .
$$
>
> $G$的单位元素$g_0$对应$n$级单位矩阵$E_{n \times n}$,互逆元素$g_\alpha$和$g_\alpha^{-1}$,对应互逆矩阵$A(g_\alpha^{-1})=A(g_\alpha)^{-1}$.
{: .prompt-info }

- 若一个群元$g_\beta$的表示矩阵$A(g_\beta)$是奇异的,即$\mathrm{det} A(g_\beta)= 0$,则所有群元的表示矩阵奇异.

### 忠实表示
如果群 $G$ 到群 $L(V, C)$ 的映射不仅同态而且 同构,即$\forall g_\alpha \in G$有唯一的 $A\left(g_\alpha\right) \in L(V, C)$ 与之 对应, 反之 $\forall A\left(g_\alpha\right) \in L(V, C)$也唯一对应 $g_\alpha \in G$, 则称此 表示 $A$ 为忠实表示.

> 对于两个同构的群 $G \cong G^{\prime}$, 若 $A$ 是 $G$ 的一个表示, 则 $A$ 必是 $G^{\prime}$ 的一个表示. $G$ 和 $G^{\prime}$ 可能代表完全不同 的物理意义,表示 $A$ 在 $G$ 中和 $G^{\prime}$ 中代表的意义也可能完全不同.
{: .prompt-info }

## 等价表示、不可约表示和酉表示
### 等价表示
 设群 $G=\left\\{g_\alpha\right\\}$ 在 表示空间 $V$ 的表示为 $A=$ $\left\\{A\left(g_\alpha\right)\right\\}$, 对应每一个 $g_\alpha$有唯一非奇异线性变换 $A\left(g_\alpha\right)$ 与之对应.在一组基 $\left(e_1, e_2, \cdots, e_n\right)$ 下, $A\left(g_\alpha\right)$ 就是与 $g_\alpha$ 对应的非奇异矩阵. 设 $X$ 是 $V$ 上非奇异矩阵, $\operatorname{det} X \neq 0$, 则相似矩阵集合 $\left\\{X A\left(g_\alpha\right) X^{-1}\right\\}$也给出群 $G$ 的一个表示,称为 $\left\\{A\left(g_\alpha\right)\right\\}$ 的等价表示.

> - 两个等价表示的维数一定相同,但维数相同的表示却不一定等价.
> - 一个表示,原则上存在无穷多个等价表示.
{: .prompt-info }
### 可约表示
 - 设 $A$ 是群 $G$ 在表示空间 $V$上的一个表 示. 如 果 $V$存在一个$G$不变的真子空间 $W$ (即 $W$ 不是空集或 $V$ 本身), 则称表示 $A$ 是可约表示,亦即$\forall y \in W,g_\alpha \in G$ ，有 $A\left(g_\alpha\right) y \in W $. $A\left(g_\alpha\right)$ 不把 $W$ 中的向量变到 $W$ 以外去.
 - 也可以从表示矩阵具有以下形式来定义可约表示.

 当$V$中存在$G$不变的真子空间$W$时,总可以在$V$中选一组基$(e_1,e_2,\cdots,e_m,e_{m+1},\cdots,e_n)$,其中$(e_1,e_2,\cdots,e_m)$是$W$的基,使得$\forall g_\alpha \in G,A(g_\alpha)$具有如下形式:

 $$
A(g_\alpha) =
\begin{pmatrix}
    & {C_\alpha} & {N_\alpha} \\\
    &0 &B_\alpha 
\end{pmatrix}.
$$

 其中$C_\alpha$位于$m$行$m$列,$N_\alpha$位于$m$行$n$列,$B_\alpha$位于$n$行$n$列,其余矩阵元均为0.
 
 $W$中的向量具有如下的形式:

$$y=\pmatrix{
    &Y  \\
    &0 
    }
$$

其中$Y$位于$m$行. 这样$A(g_\alpha)$不会使$W$中向量变到$W$外去.
   
> 一个表示,只要有一个等价表示矩阵具有上述形式,这表示就是可约的,而这表示本身并不一定具有上面的形式.因为只有通过适当选择基,才可以把$W$是$G$的不变子空间的性质用以上矩阵形式表示出来.
 {: .prompt-info }

### 直和
 设 $W$ 和 $W^{\prime}$ 是线性空间 $V$ 的子空间, 若$\forall x \in V$, 可找到 $y \in W, z \in W^{\prime}$唯一的将 $x$ 表为
$
x=y+z 
$
,
或

$$
V=W+W^{\prime}, \quad W \cap W^{\prime}=\{\emptyset\},
$$

则称 $V$ 是线性空间 $W$ 和 $W^{\prime}$ 的直和, 记为$
V=W \oplus W^{\prime} 
$.

### 完全可约表示
- 设群 $G$ 的表示空间 $V$ 可以分解为 $W$ 和 $W^{\prime}$ 的直和:$V=W \oplus W^{\prime}$, 且 $W$ 和 $W^{\prime}$ 都是 $G$ 不变的. 即$\forall y \in W, z \in W^{\prime}$, $V$ 上表示 $A$ 有

$$
A\left(g_\alpha\right) y \in W,  A\left(g_\alpha\right) z \in W^{\prime},
$$

则称表示 $A$ 是完全可约表示.  

- 对完全可约表示$A$,总可以取一组基$(e_1,e_2,\cdots,e_m,e_{m+1},\cdots,e_n)$,使得$(e_1,e_2,\cdots,e_m)$和$(e_m,e_{m+1},\cdots,e_n)$是$W$和$W'$的基.$W$和$W^\prime$中向量具有形式:

$$
y=\pmatrix{
    &Y  \\
    &0 
    }
  ,z=\pmatrix{
        &0  \\
        &Z 
        }   
$$

表示矩阵$A(g_\alpha)$具有形式:

$$
    \pmatrix{
        & C(g_\alpha) &0 \\
        &0 &B(g_\alpha) \\
        }   =C(g_\alpha) \oplus B(g_\alpha) ,
$$

即$A(g_\alpha)$是矩阵$C(g_\alpha)$和$B(g_\alpha)$的直和.

### 重复度
 一般完全可约表示 $A\left(g_\alpha\right)$ 可以写为不可约 表 示 $A^{\prime}\left(g_\alpha\right)$ 的直和

$$
A\left(g_\alpha\right)=\sum_p \oplus m_p A^{\prime}\left(g_\alpha\right),
$$

其中 $m_p$ 是正整数, 是表示 $A^{\prime}\left(g_\alpha\right)$ 在 $A\left(g_\alpha\right)$ 中出现的次数, 称为重复度.
### 不可约表示
- 设群 $G$ 的表示 $A$ 的表示空间 $V$ 不存在 $G$ 不变 的真子空间, 则 $A$ 是 $G$ 的不可约表示或既约表示. 

- 如果$A$是不可约表示,那么$A$的任何一个等价表示$A(g_\alpha)$对所有的$g_\alpha \in G$都不具备

$$\begin{pmatrix}
C_\alpha &N_\alpha \\
0& B_\alpha   
\end{pmatrix}$$

的形式,也不具有准对角

$$
\begin{pmatrix}
    C(g_\alpha) &N_\alpha \\
    0& B(g_\alpha)   
    \end{pmatrix}  
$$

的形式.

### 内积与内积空间
设 $V$ 是数域 $K$ 上线性空间, 将 $V$ 中两个有序向量 $x, y$映为数 $(x \mid y) \in K$, 对 $x, y, z \in V, a \in K$, 如满足
- $(x+y \mid z)=(x \mid z)+(y \mid z)$,
- $(x \mid a y)=a(x \mid y)$,
- $(x \mid y)=(y \mid x)^*$,
- $(x \mid x)>0$, 当 $x \neq 0$,

则数 $(x \mid y)$ 称为 $x$ 和 $y$ 的内积.

内积空间是定义有内积的线性空间.在内积空间中,定义向量$x$的长度$|x|=\sqrt{(x\mid x)}$.若两向量$x,y$的内积$(x\mid y)=0$,称$x$与$y$垂直.总可以在内积空间中选择基$(e_1,e_2,\cdots,e_n)$满足正交归一性:$(e_i\mid e_j)=\delta_{ij}$.
>- 欧氏空间:有限维实内积空间;
>- 酉空间:有限维复内积空间;
>- 希尔伯特空间:无限维复内积空间.
{: .prompt-info }

### 幺正变换

设 $U$ 是内积空间 $V$ 上线性变换, 若$\forall x, y \in V, U$ 保持 $x$ 和 $y$ 的内积不变, 即
$
(U x \mid U y)=(x \mid y),
$   
则称 $U$ 为 $V$ 上幺正变换.  

> 内积空间$V$上线性变换$A$的共轭变换$A^\dagger$定义为$\forall x,y \in V$有$(Ax\mid y)=(x\mid A^\dagger y)$.因此幺正变换$U$满足:
>
$$(Ux|Uy)=(x|U^\dagger U y)=(x|y).$$
>
> 所以幺正变换$U$存在逆变换$U^{-1}$,满足:
>
$$
\begin{aligned}
    &U^\dagger U=UU^\dagger=E,U^\dagger=U^{-1}.
\end{aligned}
$$
>
> 其中,$E$是$V$上的恒等变换.在$V$的一组固定基下,$U$用幺正矩阵$(U_{ij})$表示,满足$U^{*T}U=E$. 
{: .prompt-info }

### 酉表示
 设 $A$ 是群 $G$ 在内积空间 $V$ 上的表示, 若$A$ 是 $V$ 上幺正变换, 则 $A$ 称为 $G$ 的酉表示 ,亦即 $A$ 是 $G$ 到 $V$ 上幺正交换群的同态映射:$\forall g_\alpha, g_\beta \in G$, 有 $A\left(g_\alpha\right), A\left(g_\beta\right)$ 与之对应, 而且

$$
\begin{aligned}
A\left(g_\alpha g_\beta\right)&=A\left(g_\alpha\right) A\left(g_\beta\right), \\
A\left(g_\alpha\right)^{\dagger}&=A\left(g_\alpha\right)^{-1}=A\left(g_\alpha^{-1}\right), \\ A\left(g_\beta\right)^{\dagger}&=A\left(g_\beta\right)^{-1}=A\left(g_\beta^{-1}\right) .
\end{aligned}
$$