# Introduction

$$
\text{Beauty is the first test : there is no permanent place in the world for ugly mathematic——G.H.H\small{ARDY}}
$$

## Euler 定理

我们通过一个$\text{Euler}$的关于多面体的定理的证明开始.正如我们所示,这个命题以及对于定理的证明启发了很多关于拓扑学的想法.

![image-20230713210105529](./Image/1.png)

$\text{Figure 1.1}$展示了四个多面体,它们每一个看起来都各有不同.

然而,若对于每一个多面体,我们将其顶点个数记为$(v)$,将其边的个数记为$(e)$,将其面的个数记为$(f)$,那么,$v-e+f$的大小都等于$2$.

公式
$$
v-e+f = 2
$$
是否对于所有的多面体都成立呢?

答案是否定的,但是对于一个庞大并且有趣的类中,结果是正确的.



我们通常都是以一些有规律的(或者是凸的)多面体(左侧三个多面体)来进行我们的第一步工作,而$v-e+f$对于这些多面体来说确实为$2$.然而,在我们的示例中有一个例子不是凸的,但是也满足上式并且不能去忽视这一点.

为了去寻找一个反例,我们需要变得稍微有一些些灵巧,考虑$\text{Figure 1.2}$和$\text{Figure 1.3}$所展示的多面体可以分别得到$v - e + f = 4$以及$v-e+f = 0$.

![image-20230713211346142](./Image/2.png)

那么是哪里出问题了呢?

在第一种情况下我们构造了一个多面体,其表明由两个不同的部分组成,这似乎带上了一点欺骗性;用技术上的语言来说就是它的表面并不连通.我们怀疑(完全正确地)我们不应该允许这种情况发生,因为每一块表面对于$v-e + f$的贡献都是$2$.不幸的是,这个异议在$\text{Figure }1.3$中似乎不起效果,如图所示的多面体的表面是一个整体.然而这个表面在一个非常重要的方面与前面的不同.我们能在其表面上找到一个无法将多面体分成两个不同部分的回路($\text{loop}$);即,如果我们想象用一把剪刀围绕着这个回路剪开,多面体的表面展开后不会分成两个部分.在$\text{Figure 1.3}$中标出了一个这样的回路.

我们将表明对于不符合$\text{Figure 1.2}$和$\text{Figure 1.3}$所示性质的多面体都满足$v - e + f = 2$.

在进行下一步之前,我们需要明确的一点时直至目前为止,在我们的讨论中,只使用到了如图所示的一些固体的表面(除非我们提到凸性).所以,我们认为可以使用"多面体($\text{polyhedron}$)"一词来形容这样一个表面而不是其所包围的实体.

因此，多面体是平面多边形的有限集合,这些平面多边形在以下意义上很好地组合在一起:如果两个多边形相交,它们会相交在一条公共边上,而一个多边形的每条边恰好位于另一个多边形上.另外,如果我们考虑包含了特定顶点的一个多面体,我们便可以对其进行编号$Q_1,Q_2,\cdots,Q_k$,其中$Q_i$与$Q_{i+1}$有一个公共边($1 \leq i < k$).并且$Q_k$与$Q_1$有一个公共边.换句话讲,这些多边形结合在一起,在给定顶点的周围形成了一块表面($k$的大小因顶点而异).这最后一个条件排除了比如说两个立方体通过一个顶点连接而构成一个多面体的情况.



$(1.1)$$\text{Euler}$ 定理.令$P$是一个满足如下条件的多面体

1. $P$中的任意两个顶点可以被一条由边所组成的链所连接
2. $P$上任何由直线段(不一定是边)组成的回路可以将$P$分成两部分.

对于$P$成立$v - e + f = 2$

公式$v - e + f =2$有着悠久并且复杂的历史,它第一次出现在$1750$年$\text{Euler}$与$\text{Goldbach}$的书信中.然而,$\text{Euler}$对于他的多面体没有进行任何限制,这就导致他的推理只能运用于凸多面体的情况.$60$年后$(\text{Lhuilier})$才注意到如$\text{Figure 1.2}$和$\text{Figure 1.3}$中多面体所引出的问题.定理的精确描述和下面概述的证明都是由$\text{von Staudt}$在$1847$年发表的.

[证明]

![image-20230713222702386](./Image/3.png)

$P$中连通的顶点和边所构成的集合称为图$(\text{graph})$:连通仅仅意味着任意两个顶点可以通过图中的边组成的链连接起来.更一般的,我们将使用图这个词来表示三维空间中任何有限连接的线段集合,它们像$\text{Figure 1.4}$一样很好的结合在一起(若两线段相交,则必然相较于一个公共顶点),一个不包含任何回路的图称为一个树$(\text{tree})$.不难发现,对于一个树,顶点的个数减去边的个数总是为$1$.使用$T$来表示一个树,那么可以得到$v(T) - e(T) =1$.

根据假设$1$.$P$中所有顶点和边的集合形成一个图.不难发现对于任意一个图都可以找到一个包含了$P$中所有顶点并且为树的子图.于是可以选择一个树$T$使其由一些便以及$P$中所有的点组成.($\text{Figure 1.4a}$展示了$\text{Figure 1.1}$中一个多面体的树).

![image-20230713224648828](./Image/4.png)

接着形成一个树$T$的"对偶",这个对偶是根据如下方法所定义的一个图$\Gamma$:对于$P$中的每一个面$A$,我们给$\Gamma$一个顶点$\hat{A}$.$\Gamma$中的两个顶点$\hat{A}$和$\hat{B}$是被一条边连接的当且仅当$P$的对应面$A$与$B$相邻并且相交于$T$中的边.($\hat{A}$对应于$A$的一个内点).要做到这一点,我们不得不像$\text{Figure 1.5}$中的构造一般允许它的边是弯曲的.

不难发现这个对偶$\Gamma$是连通的因此其也形成一个图.直观地说,如果$\Gamma$的两个顶点不能被一条由边所组成的链相连接,则它们必然能被$T$中的一个回路所切割开来(其中所需要的证明我们在$\text{Chapter 7}$中会进行介绍).因为$T$为树(不会包含任何回路),于是我们得知$\Gamma$必然是连通的.

事实上$\Gamma$也是一个树.因为如果$\Gamma$中有一个回路,则根据假设$2$,它会把$P$分为两个不同的部分,而每个部分至少包含$T$的一个顶点.任何试图通过边所构成的链连接$T$中处于不同部分的两个顶点的尝试都会导致这个链满足这个分离回路,因此这条链无法完全位于$T$中.因此$\Gamma$是一个树.(对于如$\text{Figure 1.3}$所示的多面体,这个证明便失效了,因为其对偶图$\Gamma$包含一个回路)

> ![image-20230713235417615](./Image/5.png)
>
> 上图为$\text{Figure 1.3}$的一个树,接下来我们构建其对偶图$\Gamma$
>
> ![image-20230713235353954](./Image/6.png)
>
> 不难发现其存在一个回路.

因此对于任何树来说顶点的数量总是比边的数量多$1$.得到$v(T) - e(T) = 1$且$v(\Gamma) - e(\Gamma) = 1$于是
$$
v(T) - [e(T) + e(\Gamma)]+v(\Gamma) = 2
$$
根据树的构造得到$v(T) = v$,$e(T) + e(\Gamma) = e$并且$v(\Gamma) = f$.这就证明了$\text{Euler}$公式.$\Box$



## 拓扑等价

![image-20230714114401950](./Image/7.png)

这里还有很多种关于$\text{Euler}$公式的证明.我们选择先前的证明是由于两个原因:其一,它很优美,其他很多证明都对于$P$的面数使用了数学归纳法.其二,因为它包含了比$\text{Euler}$公式更多的信息.再做进一步探讨,它实际上告诉我们$P$是由两个沿其边界的两个圆盘($\text{disc}$)所组成的.为了揭示这一点,仅仅需要将$P$上的$T$和$\Gamma$增厚一点(如$\text{Figure 1.6}$所示),就可以得到两个不相交的圆盘(对于树进行加厚总是可以得到一个圆盘(__灰色部分__),而对于带回路的图进行加厚可以得到一个带洞的空间).一点一点地扩大这些圆盘,直到它们的边界重合.多面体$P$现在就由两个具有相同边界的圆盘组成.虽然这些圆盘看起来形状相当古怪,但是我们可以将其展成一个圆形的扁平圆盘.

![image-20230714115841805](./Image/8.png)

现在,将一个球由两个圆盘(南北半球)组成,并且沿着它们共同的边界缝合在赤道($\text{equator}$)上(如$\text{Figure 1.7}$)所示.换句话讲,$\text{Euler}$定理的假设旨在告诉我们$P$在某种意义上看起来像一个变形的球体.

![image-20230714164438657](./Image/9.png)

当然,对于一个特定的多面体,在它的点和球体的点之间建立一个适当的对应关系是很容易的.举个例子,在正四面体$T$的情况下,我们可以通过$\hat{T}$处向$T$施加重力的径向投影(往外)将$T$投影到一个以$\hat{T}$为球心的球体上(__以后称其为径向投影法__).$T$中的面投射到球体上的曲线三角形上(如$\text{Figure 1.8}$所示).事实上$\text{Legendre}$正是使用了这个过程证明了凸多面体的$\text{Euler}$定理.我们稍后将描述其证明过程.

在$\text{Figure 1.1}$右侧所展示的多面体并不是凸的也不适合上述论证.然而,如果我们认为它是由橡皮制成的,那么我们很容易想象如何将其变形为一个普通的球体.在变形的过程中,我们可以随意拉伸和弯曲多面体,但是不能生成新的顶点也不会撕裂多面体.

给定多面体上的点与球面上的点的对应关系是拓扑等价或同胚的一个例子.在正式场合中它是一个一一的具有连续逆的连续函数.(__此即拓扑等价的定义__)

![image-20230714195641923](./Image/10.png)

我们将在$1.4$节中仔细研究同胚的定义,在此,为了能够具体地了解同胚,我们现在给出了四个例子($\text{Figure 1.9}$)

$(a)$ 圆柱体的表面,不包括其上两个圆

$(b)$由方程$x^2 + y^2 - z^2 = 1$给出的单叶双曲面($\text{one-sheeted hyperboloid}$)

$(c)$$1<|z|<3$所给出的复平面上的开环(指两边是开的)

$(d)$去掉南北极点的球体.



我们将给出一个$(b)$到$(c)$的具有具体同胚(连续的,一一的,并且具有连续逆的函数).

表示$(b)$中点最方便的方式就是使用柱坐标表示$(r,\theta,z)$,对于$(c)$则是使用平面极坐标$(r,\theta)$来表示.

当$(b)$中$\theta = 0$我们便得到了双曲线$x^2 - z^2 = 1$的一支,我们打算将其放在相应的环面上($(c)$中的环面)即射线$\{(x,y):1<x<3,y = 0\}$(注意,这是极坐标).如果我们能够对于所有的介于$0$到$2\pi$中的$\theta$都连续的执行先前的操作,那么我们将会得到前文所需要的同胚映射.定义函数$f : (-\infty,+\infty) \to (1,3)$且$f(x) = \frac{x}{1+|x|}+2$.不难发现$f$是一个双射,并且$f$是连续的且有连续逆.于是我们便可以把$(r,\theta,z)$中的点映射到$(f(z),\theta)$.



接下来,我们将引领读者去研究其他的可能性:注意到拓扑等价关系显然是一个等价关系

> 由于$a$与$b$拓扑等价是指$a$与$b$间存在一个一一的具有连续逆的连续函数,于是存在$f : a \to b$使得$f$是一个一一的具有连续逆的连续函数,于是由于$f$是双射,可以考虑其逆$f^{-1}$,由于$f$具有连续逆,于是$f^{-1}$也是连续的,并且不难得出$(f^{-1})^{-1} = f$而$f$也是连续的.于是可以说$f^{-1}$具有连续逆.
>
> $f^{-1}: b \to a$也是一个一一的,具有连续逆的连续函数,于是得知$b$与$a$也拓扑等价(对称性)
>
> 接下来验证另外两个性质.
>
> 自反性:
>
> 考虑恒等变换$\text{id}_a$将$a$中的每个元素$x$映射到其自身,其显然会是一个连续函数,并且其对于自身就构成一个逆,也就是说其满足拓扑等价的条件.即$a$对于自身拓扑等价.
>
> 传递性:
>
> 若$a$与$b$拓扑等价,$b$与$c$拓扑等价,那么存在$f : a \to b$,$g: b \to c$使得$f$和$g$均为一一的具有连续逆的连续函数.由于$f$和$g$均为双射,于是$g \circ f: a \to c$也是双射,并且由于其同时为连续函数,由于是$g \circ f$也为一个连续函数.不难发现$(g\circ f)^{-1} = f^{-1}\circ g^{-1}$也为一个连续函数,即$g \circ f$具有连续逆.于是$a$与$c$范畴等价.
>
> 综上所述,范畴等价确实为一个等价关系.

因此,若我们能够证明空间$(a)$和$(d)$与空间$(c)$拓扑等价,就可以验证$4$个空间相互拓扑等价(使用传递性和对称性).在拓扑学中,我们认为这$4$个空间是"相同的空间".去掉三个点的球面与前面几个空间则是不同的(不同胚)这是为什么呢?是否能够描述复平面的一个子集同胚于移去三个点的球面?

回到$\text{Euler}$定理的证明,将树$T$和$\Gamma$进行增厚后将$P$分解为一个具有两个共同边界的圆盘,因此,可以同构将一个圆盘中的点映射到北半球,另一个圆盘中的点映射到南半球,这是一种定义多面体$P$到球的同胚的方法.制造一个反例是有可能的(我们将在$\text{Chapter 7}$中进行详细讨论)并且证明如果$P$拓扑等价于一个球面,那么$P$满足$(1.1)$的两个条件(其中条件$1$是很容易进行验证的,由于$P$拓扑等价于一个球,于是其边可以拓扑等价于球上的边,由于我们可以将其视为是相同的空间,于是$P$上任意两个顶点之间是否能够由边构成的链连通便转化成球上任意两点是否能够由球上的边构成的链所连接,这是显然的;而条件$2$的证明比较难,这是著名的$\text{Jordan}$曲线定理的一个特例),于是$\text{Euler}$定理可以作用于$P$.从而,若$P$与$Q$为拓扑等价于球的多面体,并且若我们称$v-e+f$作为多面体的$\text{Euler}$数,则我们从前面的讨论中可以得知$P$与$Q$具有相同的$\text{Euler}$常数$2$.

![image-20230715160544782](./Image/11.png)

在$\text{Figure 1.3}$中展现的多面体具有完全不同的形式,它同胚于一个环面(我们甚至可以想象如何将其连续变成一个环面,如$\text{Figure 1.10}(b)$所示,)并且其$\text{Euler}$数为$0$.对于任何其他的与环面同胚的多面体并且去计算其$\text{Euler}$数会发现均为$0$.(尽管这很难证明,直到$\text{Chapter 9}$我们才将其证明).我们现在仅仅需要一个小步骤(一个小步骤是在数学直觉上的小步骤,但是详细证明我们还有很长的路要走)就可以触及拓扑最基本和最核心的结果之一了.

$(1.2)$定理:拓扑等价的多面体具有相同的$\text{Euler}$数.

这个显著的结果是现代拓扑学的起点.值得注意的是,在计算多面体的$\text{Euler}$数时,我们使用了多面体的顶点,边和面的数量,它们经过拓扑等价都不一致(即拓扑等价不会保证它们相等).它导致对空间其他性质的探索,这些性质在同胚中的应用没有改变.

我们稍后应当回到$\text{Euler}$数,并且表明其可以在比目前所考虑的普通多面体更广泛的空间中被定义.这些多面体更加"坚硬",有角,边,有平面,我们不会特别感兴趣.在拓扑学家的角度上球体足以表示$\text{Figure 1.1}$所展示的所有多面体.

我们的准则如下:$\text{Euler}$数$2$不属于某一类特定的多面体,_它属于球面_.一个满足$\text{Euler}$定理假设的多面体(同胚于球面的一个多面体)仅仅给出一种计算球的$\text{Euler}$数的方便方法.有了这个重点,定理$(1.2)$表明,用明显不同的方法计算总是得到相同的答案.我们将在$\text{Section } 9$继续进行讨论.

我们以$\text{Legendre}$对于凸多面体上$\text{Euler}$公式的独特证明来结束本节,如$\text{Figure 1.8}$所示,使用径向投影法将多面体投影到半径为$1$的球面上,多面体的多边形边投影为球面上的多边形.

现在,若$Q$是一个具有角$\alpha_1,\alpha_2,\cdots,\alpha_k$并且带有$n$条边的球面多边形,那么$Q$的面积由
$$
\alpha_1+\alpha_2+\cdots+\alpha_k - (n-2)\pi = (\alpha_1+\alpha_2+\cdots+\alpha_k)-n\pi + 2\pi
$$
 不难发现球上的所有球面多边形的面积之和为$2\pi v - 2\pi e + 2\pi f$(每个顶点的总角度为$2n$,因此$2nv$正好包含了所有的$\alpha_i$($i = 1,2,\cdots,k$),每条边都要被计数两次,因为其正好属于两个多边形面,每个面在上式中贡献一个$2\pi$).由于单位球的表面积为$4\pi$于是得到$2\pi v - 2\pi e + 2\pi f = 4\pi \Leftrightarrow v - e + f =2$.



## 曲面(Surfaces)

### 十万个为什么阶段(吐槽)

拓扑学与空间有关的性质不会被拓扑等价或者同胚所改变.但是什么类型的空间对我们有吸引力以及我们平常所说的"空间"到底是什么意思?同胚的概念与连续性的概念密切相关;两个空间之间的连续函数是什么意思?我们将在这一节和下一节中讨论这些问题.

### 正文

我们先从一些有趣的空间起步,从事分析工作的人总是习惯于考虑一个实线,一个复平面甚至在一个单位闭区间上的所有实值连续函数所构成的集合称为(度量)空间.作为本质上是几何学家的我们对于欧式空间中自然出现的有界构型更感兴趣.

![image-20230715160544782](./Image/11.png)

举个例子,例如在平面上的单位元和单位圆盘,球面,环面,$\text{M}\ddot{\text{o}}\text{bius}$环,圆柱面和带穿孔的双环面等表面都存在于三维空间中,如$\text{Figure 1.10}$所示.

此外还有性质更为复杂,更加难以想象的像$\text{Klein}$瓶这样的表面,其难以想象源于任何试图在三维空间中表示它时,$\text{Klein}$瓶都必须与自己交叉.在图中$(\text{Figure 1.10})$,这个曲面被切割成一个小圆.我们可以通过建立$\text{Klein}$瓶的模型来更好地理解它.

![image-20230717131842596](./Image/12.png)

考虑我们通常用来构建环面的方法:从$\text{Figure 1.11}$所示的长方形纸开始(此处为构造圆环),确定边缘.前半部分与圆环的构造是一致的,但是到了圆柱体这个阶段,其两端需要向着相反的方向确定(具体如$\text{Figure 1.12}$所示)为了做到这一点,就必须让圆柱体弯曲,一段穿过其侧面.

![image-20230717132146409](./Image/13.png)

在四维空间中$\text{Klein}$瓶$(K)$可以不带任何自交地被构造出来.

> 不妨想象一个独立于纸面的额外维(注意,我们认为纸面是一个三维空间).在$K$的交叉点处附近有$2$根管子,其中一根穿过另一根管子,将右上方那根管子提到纸张之外,然后在四维空间中表示出的另一个管子的部分在四维空间中的"坐标"只是局限的(比如说在三维空间中表示一个圆可以只用两个坐标$x$和$y$进行表示,而$z$可以始终维持在某个常数上,那么我们想连通圆内和圆外的两点$a$和$b$,在二维的平面上来看是不可能的,但是我们在三维情况下看则可以发现由于圆的$z$轴大小均为固定的,于是可以通过$z$轴构造一道"桥"连接$a$与$b$但是又不与圆相交).于是我们可以通过第四个维度构造一个"桥"绕过另一根管子的壁而进入其内部(我们使用四维空间对其进行坐标表示可以发现其第四个维度可以保持在某个区间大小之内,也有可能是一个常数,于是我们可以在四维空间中构造一个"桥"),于是在四维空间中,纸中的"壁"可以在第四个维度中绕过,即从纸张之外将管子"接进去"是不会与三维空间中的部分相交的.

上文看起来比较难想象,可以通过$\text{Figure 1.13}$来辅助理解

![image-20230717144309572](./Image/14.png)

上图中$(a)$不分两条直线是相交的,$(b)$部分将一条直线提到三维空间再放下(也就是跳线)后,它们本质上是没有相交的.从四维空间中看待$\text{Klein}$瓶的方式也类似于这样.



我们通过欧式空间中表示曲面来引入曲面的方法也不像想象中那么好.我们更感兴趣的是"通过同胚改变"的曲面,换句话说,拓扑等价的曲面将会被视为相同的空间.

<img src="./Image/15.png" alt="image-20230717144843288" style="zoom:80%;" />

在$\text{Figure 1.14}$中我们给出了$3$份$\text{M}\ddot{\text{o}}\text{bius}$环$(M)$.前两个是同胚的,这并不奇怪,我们只需要将第一个像拉橡皮一样拉伸成为第二个(认为空间是由橡皮构成来解释拓扑等效的想法源于$\text{M}\ddot{\text{o}}\text{bius}$,可以追溯到$1860$年左右).但是$1.14(a)$和$1.14(c)$之间是否同胚呢?这两个空间是同胚的,但是无论怎样拉伸,弯曲都无法将其中一个空间变为另一个.

于是为了证明两个空间是同胚的,必须在它们之间找到一个连续的双射,并且保证其逆也是连续的.现在忘记我们先前所构建的$\text{M}\ddot{\text{o}}\text{bius}$环,现在试着自己构造一个$M$.建立一个模型是简单的:从一个长方形纸张开始,找到一对对边$(A)$和$(B)$,将其中一边扭曲半圈($180$度),而后将其拼到一起便得到了先前的$\text{Figure 1.14a}$.

<img src="./Image/16.png" alt="image-20230717150011298" style="zoom:80%;" />

为了得到$\text{Figure 1.14c}$,我们必须在原来的步骤上(扭转$180$度后)再扭转一个整圈($360$度)而后将其拼接起来,即对于一个长方形纸片的一边转一圈半后再拼到其对边上.

但是上述两步对于边$A$与边$B$的方向却没有改变(还是通向的),也就是说在$1.14\text{a}$中相交的点(相对于相交位置的坐标)在$\text{1.14c}$中保持一致.于是$\text{1.14a}$和$\text{1.14c}$所展示的空间是同胚的.它们只是同一个空间在欧式空间中的不同表示.

尽管我们可以找到它们之间的同胚,但是没有办法将这种同胚拓展到整个欧式空间上,即不存在欧式空间到自身的同胚映射将$1.14 \text{a}$投影到$1.14\text{c}$上.

由于我们的直觉在$\text{Figure 1.14}$这种图片上产生歧义,这表明我们需要一种抽象化空间,而不是依赖于它们在欧式空间中特定的代表形状.接下来我们会尝试把曲面的概念转化为精确的数学语言.这个过程会相当漫长,首先其涉及到抽象(拓扑)空间的定义,其次去认识曲面是那些局部看起来像欧式空间的空间.

## 抽象空间

为了找寻一个令人满意的拓扑空间定义(现代定义出现的很晚,拓扑空间的公理是在$1914$年首次出现在$\text{Hausdorff}$的著作中)我们心中应当追寻两个目标:

* 定义应当足够通用,以允许足够广泛的结构(指足够多的结构都适用)作为空间.我们打算考虑一个有限的,离散的点所构成的集合作为空间,或者同样地考虑一个完整的不可数点的连续体,比如实线作为空间.一个漂亮的集合曲面应当符合这个定义,一个函数空间(比如复平面单位元上定义的连续复值函数集合)也应当符合这个定义.我们希望对于我们的空间进行简单的构造(例如取两个空间的笛卡尔积)或者确定空间中的一些点以形成一个新的空间(比如前文中$\text{M}\ddot{\text{o}}\text{bius}$环的构造)
* 空间的定义应当包含足够多的信息,以便我们定义空间之间的函数的连续性的概念.(正是这一点引出了我们下文所将的抽象定义).



令$f$为两个欧式空间之间的函数,记为$f:  \mathbb{E}^m \to \mathbb{E}^n$.关于$f$的连续性的经典定义如下:若对于任意的$\varepsilon>0$,存在$\delta>0$当$\|\boldsymbol{y} - \boldsymbol{x}\|<\delta$时有$\|f(\boldsymbol{y}) - f(\boldsymbol{x})\|<\varepsilon$则称$f$在$\boldsymbol{x} \in \mathbb{E}^m$上连续.若其对于所有的$\boldsymbol{x} \in \mathbb{E}^m$都满足上述条件则称$f$为一个连续函数.如果对于某个实数$r > 0$的以$\boldsymbol{p} \in \mathbb{E}^m$为中心,$r$为半径所组成的实球$B(\boldsymbol{p},r)$完全处于$N$内($N\subset \mathbb{E}^m$,注意,$N$不是实球,它只是一个子集)则称$N$为点$\boldsymbol{p}$的邻域.可以容易的将连续性的定义改写为:若对于任意的$\boldsymbol{x}\in \mathbb{E}^m$以及任意$f(\boldsymbol{x})$在$\mathbb{E}^n$中的邻域$N$都有$f^{-1}(N)$是$\boldsymbol{x}$在$\mathbb{E}^m$上的邻域.

> 为什么连续的定义具有合理性,即根据我们所定义的条件为什么可以推导出$f$连续(这也是连续性定义的推理过程).
>
> 若$f(\boldsymbol{x})$在$\mathbb{E}^n$的邻域$N$有$f^{-1}(N)$是$\boldsymbol{x}\in \mathbb{E}^m$的邻域.
>
> 取$f(\boldsymbol{x})$的一个开球$B(f(\boldsymbol{x}),\varepsilon)$(即满足连续性定义的$\varepsilon$)将其视为$f(\boldsymbol{x})$的一个邻域$N$,那么其逆$f^{-1}(N)$是$\boldsymbol{x}$的一个邻域,那么就不难发现存在一个开球$B(\boldsymbol{x},\delta)$使得$B(\boldsymbol{x},\delta)\subset f^{-1}(N)$,即处于这个$\delta$为半径的开球内的任意点$\boldsymbol{x}'$的像与$f(\boldsymbol{x})$的距离均小于$\varepsilon$
>
> 
>
> 至于连续的定义为什么不是对于任意的$\boldsymbol{x}\in \mathbb{E}^m$及其邻域$N$都有$f(N)$是$f(\boldsymbol{x})$在$\mathbb{E}^n$上的邻域呢?
>
> 这就需要进行讨论,证明我们刚刚提到的条件无法推导出$f$连续.
>
> 考虑$f : [0,1) \to C$,$f = e^{2\pi i x}$的逆$f^{-1} : C\to [0,1),f^{-1} = \frac{\ln x}{2\pi i}$也可以写为$f^{-1}:x = \cos \theta + i \sin \theta \to \frac{\theta}{2\pi}$.其中$\theta \in [0,2\pi)$,不难发现对于任意$x\in C$的邻域$N$都有$f^{-1}(N)$是$[0,1)$中关于$\frac{\theta}{2\pi}$的邻域.但是$f^{-1}$并不连续,这是因为对于$0$的邻域$[0,\frac{1}{2})$有$f([0,\frac{1}{2})) = 1$是$C$的上半圆周,但是并不是一个关于$f(0) = 1$的邻域.
>

空间中的每个点都有一组"邻域",这些邻域反过来又能很好地定义连续函数,所以这一概念是至关重要的.注意到在定义欧式空间中的邻域时,我们使用了点与点之间的欧式距离,于是在构建抽象空间时,我们希望保留邻域这个概念但摆脱对于距离函数的依赖(拓扑等价是不保持距离的,可以通过$\text{Figure 1.8}$四面体上两点之间的距离与其投影到球面上后两点之间的距离看出).

通过对于欧式空间中点的邻域的性质的考察,我们可以得到拓扑空间的下列公理.

> 这些公理的得出需要在欧式空间中的邻域概念里去掉距离有关的内容,即我们只通过集合之间的关系来定义这个公理.
>
> 那么不难发现邻域对于集合的运算满足集合的交并仍为邻域
>
> 对于每个元素$x$的邻域必然有其自身也包括在邻域中
>
> 邻域与任意集合的并集也是一个邻域(其至少包含原来那个邻域所满足的实球)
>
> 若该邻域还作为其他元素$z$的邻域,则考虑$\mathring{N} = \{z\in N : N\text{是}z\text{的邻域}\}$(其实就是$N$的开核)有$\mathring{N}$为$x$的邻域

$(1.3)$ 对于集合$X$,若对于$X$中的每个点$x$都有一组非空的$X$的子集,将其称为$x$的邻域.这些邻域需要满足以下四条公理.

1. $x$需要在其邻域内
2. 两个邻域的交集还是一个邻域
3. 如果$N$是$x$的一个邻域,并且$U$是$X$的一个包含了$N$的子集,则$U$也是$x$的一个邻域
4. 若该邻域还作为其他元素$z$的邻域,则考虑$\mathring{N} = \{z\in N : N\text{是}z\text{的邻域}\}$(其实就是$N$的开核)有$\mathring{N}$为$x$的邻域

这整个结构称为拓扑空间,对于每个$x \in X$满足公理$1-4$的邻域集合称为$X$上的拓扑(为了给公理$4$增加一点点的动机,在$\mathbb{E}^m$中取点$\boldsymbol{x}$令$B$(一个开球)表示与$\boldsymbol{x}$的距离小于$1$的点所构成的集合(一个实球减去其边界部分),于是$B$是一个$\boldsymbol{x}$的邻域)

现在,我们可以精确地说明连续函数和同胚到底是什么意思了.

令$X$和$Y$是拓扑空间(根据定义$(1.3)$生成的复杂结构).

* 一个函数$f : X \to Y$是连续的若对于每个$x \in X$以及所有的$f(x)$在$Y$中的邻域$N$都有集合$f^{-1}(N)$是$X$中关于$x$的邻域.

* 一个函数$h : X \to Y$被称为是同胚映射若其为一个一一的,连续的且具有连续逆的函数,如果这样一个函数存在,那么$X$和$Y$之间可以称为同胚(或拓扑等价)空间.

突然之间,事情变得非常复杂,接下来我们需要一些例子来辅助我们理解这些概念.

$Example$

1. 任何具有邻域定义的欧式空间都是拓扑空间(稍后我们将证明不同维数的欧式空间不可能同胚,这是一个很难的问题.但是如果我们有足够的信心让我们的同胚定义和空间的维度概念共存,这是必不可少的)

2. 设$X$是一个拓扑空间,$Y$是$X$的一个子集,我们可以通过如下方式来定义$Y$上的拓扑:对点$y \in Y$取其在$X$中的一组邻域集合再对每个邻域与$Y$求交集,这样就得到了$y$在$Y$中的一组邻域其关于拓扑空间的公理是很容易验证的,我们称$Y$有一个子空间拓扑.这是一个非常有用的步骤,比如它允许我们把欧式空间中的任何子集视为一个拓扑空间.特别地,我们的曲面例子也就称为了一个拓扑空间.

3. 用$C$表示复平面上的一个单位圆且用$[0,1)$表示大于等于$0$且小于$1$的实数.我们分别从平面和实线给出这两个集合的子空间拓扑.定义一个函数$f : [0,1) \to C$使得$f(x) = e^{2\pi i x} = \cos(2\pi x)+i\sin(2\pi x)$,显然有这是一个连续函数,并且这是双射,但是它的逆却是不连续的(考虑$[0,\frac{1}{2})$这是一个关于$0$的邻域,而$f([0,\frac{1}{2}))$不是一个关于$f(0) = 1$的邻域($1$是其界点,而不是其内点,所以有$f([0,\frac{1}{2}))$的开核$f([0,\frac{1}{2}))\mathring{}$并不包含$1$)于是根据邻域的公理得知其逆不连续).这很好地说明了反函数连续这个条件在同胚定义中的重要性:我们不乐意看到圆与区间同胚.

4. 以$\text{Figure 1.8}$所示的情况为例,将球体与四面体视为$\mathbb{E}^3$的一个子空间.考察径向投影$\pi$在这两个空间中给出的一个同胚,这类同胚称为三角剖分(这是在球面上的情况)并且这将会是我们后继章节的主题.

5. 集合上的距离函数或者度量会产生集合上的拓扑邻域的构造完全类似于欧式空间中的过程.我们举例说明函数空间的情况,设$X$是所有定义在闭区间$I$上的连续实值函数所构成的集合.集合中的函数必然是有界的(连续并且在闭区间上,于是没有间断点),通常把$X$上的距离函数定义为
   $$
   \text{d}(f,g) = \sup_{x\in I}|f(x) - g(x)|
   $$
   给定一个函数$f \in X$,若存在一个正实数$\varepsilon$,所有与$f$距离小于等于$\varepsilon$的$g \in X$都属于$N$,则称$N$为$f$的一个邻域.

6. 两个不同的拓扑空间可能会基于一个相同的点集.作为实数集合上一个相当奇特的拓扑的例子:定义一个实数的子集如果它包含该实数并且其补集是有限的则称其为一个特殊的实数邻域.这就给出了一个与实线不同的(不同胚)的拓扑空间.注意在实数集合上没有距离函数可以产生这种拓扑(由于其补集有限,即至多只存在可列个点不被其所包含,若存在距离函数$d$使其可以产生这种拓扑,则令$x,y \in X$,取$D = d(x,y)$于是得到以$x$为球心,以$D$为半径的实球$D_x$正好经过$y$,同理$D_y$正好经过$x$,接下来,设$B'_x$是以$\frac{D}{2}$为半径所构成的__开球__,同理得到$B'_y$于是有$B'_x \cap B'_y = \varnothing$而$B'_x$和$B'_y$,显然有$B'_x$和$B'_y$非空,且其可以定义前文的邻域,由于补集有限,于是对于$x$考虑有$(B'_x)^c$包含有限个点,即$B'_x$包含无穷多个点,接着对于$y$进行讨论得到$(B'_y)^c$具有有限个点,而$B'_x \subset (B'_y)^c$,于是其只有有限个点,与前文的推论矛盾.)

7. 设$X$是一个集合,并且对于所有的$x \in X$,定义$\{x\}$作为$x$的邻域,于是根据公理$3$,$X$中任何包含$x$的子集均为$X$的邻域.直观地,我们认为这种拓扑结构式把$X$变成一个离散的点的集合,我们安排每个点$x$都有一个不包含其他点的邻域,那么在这种拓扑下,任何具有定义域的函数$X$都是连续的.

现在,我们已然开发出了一款足够完备的工具,这可以准确地表示我们所说的曲面是什么,并且摆脱了必须在欧式空间中的束缚.

$(1.4)$ __定义__:曲面是一个拓扑空间,其中每个点都有一个邻域同胚于一个平面,并且任意两个不同的点都有不相交的邻域.

花费点功夫详细研究这个定义肯定是物有所值的.空间中每一个点都有一个与平面同胚的邻域这一要求正好符合我们对于曲面的直观理解.如果我们站在某一个点上(想象一个巨大的表面,地球就是一个例子除非你认为地球是平的,看着离我们脚很近的点,我们应当能够想象我们站在一个平面上.仔细想想这个要求:我们要求空间中每一个点的某个邻域与平面同胚.那么,我们必须把这个邻域当作自身的一个拓扑空间来看,这并没有什么困难(邻域毕竟是给定空间的一个子集),因此我们可以为它建立一个子空间拓扑.

第二个要求,即任何两个不同的点都有不相交的邻域,这在本质上更有技术含量.它是由我们日常经验所引出的:我们所有曲面的例子都具备这个性质,但是局部看起来像平面的空间无法直接满足这个性质.

<img src="./Image/17.png" alt="image-20230717211343702" style="zoom:80%;" />

我们给了一个尽可能简单的定义.如果我们希望允许一个曲面具有边缘或者边界(如$\text{M}\ddot{\text{o}}\text{bius}$环的情况),那么我们就不能指望每一个点都与平面有邻域同胚.我们必须允许有邻域同胚于上半平面($y \geq 0$的部分).当它们从欧式空间中得到子空间拓扑时,所有曲面的例子现在都很好地符合这个定义.$\text{Figure 1.16}$说明了$\text{M}\ddot{\text{o}}\text{bius}$环情况下的定义.



## 一个分类定理

在$1.3$节开始前,我们曾声称自己是几何学家,但在这里,我们慢慢地陷入了技术细节的泥沼.为了逃避这些细节泥潭(暂时的逃避,将在下一章对于抽象拓扑空间的性质进行更详细地研究)我们将回到曲面理论.

我们应该限制在一个相当好的曲面类型中,并且只考虑那些没有边界的以及在某种意义下是封闭的曲面:此外,我们还要求我们的曲面是连通的,即由单个部分组成的.球体,环面以及$\text{Klein}$瓶都是我们想象出的符合要求的表面,而圆柱体和$\text{M}\ddot{\text{o}}\text{bius}$环由于具有边而被排除在外.接着排除平面以及$\text{Figure 1.9}$所示的曲面,由于其不"闭合"$(\text{closed})$.

![image-20230714195641923](./Image/10.png)



确切地说,我们处理的是紧致的,连通的曲面,但是紧致性和连通性的精确定义要等到$\text{Chapter 3}$才会给出.

值得注意的是,如果我们只同意在这些所谓的"闭合"曲面上进行工作,那么我们或许可以得知它们具体的数量,并且对它们进行归类.这样的分类需要制作一个曲面的列表,使得给定任意一个闭合的曲面都同胚于列表中的某一个曲面,另一方面,列表又不能太长,也就是说,我们的列表中不存在两个同胚的曲面.

![image-20230720164034862](./Image/18.png)

我们可以构建如下的闭合的曲面作为示例.对于一个正常的球面,取下两个不相交的圆盘,然后添加一个圆柱体将其两个边界圆与球体的两个边界口相连,得到如$\text{Figure 1.17}$所示的曲面.这个过程称作给球面"加个柄".经过重复,我们可以得到一个带有两个,三个或任意有限个的柄的球体.

不难看出一个只有一个柄的球体同胚于环面(可以将环面的一部分进行橡皮扩张称一个球).这个添加把柄的过程提供了列表中一半的表面.

其他一些封闭曲面与克莱因瓶类似,它们无法在欧几里得三维空间中表示,并且因此更难以想象.幸运的是,构造这些曲面的模型是一个容易描述的过程.从一个球体开始,去掉一个圆盘,并在它的位置上加上一个莫比乌斯带.莫比乌斯带的边界实际上只有一个圆,我们要求的是将这个边界圆的点与球体孔的边界圆的点进行等同.我们必须想象这种等同发生在某个有足够空间的地方(例如欧几里得四维空间,在$\text{Chapter 4}$中我们将会解释如何将两个拓扑空间粘合在一起以形成一个新的空间,从而不以任何方式依赖于$\mathbb{E}^3$和$\mathbb{E}^4$中的空间模型),如前面所提到的,在三维空间中是无法实现的,因为会导致莫比乌斯带与自身相交.由此构造得到的封闭曲面被称为射影平面.

![image-20230720193517448](./Image/19.png)

对于每一个正整数$n$,我们都可以通过从球面中拆除$n$个不相交的圆盘并且将其换为$\text{M}\ddot{\text{o}}\text{bius}$环来得到一个封闭的曲面,当$n = 2$时,我们重新捕捉到$\text{Klein}$瓶.$\text{Figure 1.18}$是一个对其进行解释的尝试.在平面上把$\text{Klein}$瓶切成两半,并且移除两部分的自交点,这样就可以得到$\text{Figure 1.18}(a)$中的两个$\text{M}\ddot{\text{o}}\text{bius}$环(注:左侧为沿着自交点向外剪的$\text{M}\ddot{\text{o}}\text{bius}$环,右侧为向内剪去的情况)

取其中一个并且在其边界的一带上进行标记($\text{Figure 1.18}(b)$);不难发现这个带状区域同胚于一个圆柱体,接着我们移除这样一个圆柱体($\text{Figure 1.18}(c)$),留下一个较小的$\text{M}\ddot{\text{o}}\text{bius}$环.并且由于圆柱体同胚于一个球体去掉两个不相交圆盘的形状(于是$\text{Klein}$瓶相当于一个圆柱体加上两个$\text{M}\ddot{\text{o}}\text{bius}$环亦即球面拆除两个圆盘并换成$\text{M}\ddot{\text{o}}\text{bius}$环).因此,当$n = 2$时,$\text{Klein}$瓶的通常描述与我们的构造一致.



$(1.5)$ 分类定理 : 任意封闭曲面要么同胚于一个球,或一个球加上有限个柄,亦或者一个球拆除$n$个不相交的圆盘并将圆盘转化为$\text{M}\ddot{\text{o}}\text{bius}$环.并且上述曲面两两不同胚.

举个例子,取一个带有一个把柄的球面,接着移除一个圆盘,将移除的部分改为$\text{M}\ddot{\text{o}}\text{bius}$环,这样就得到了一个域去掉三个不相交圆盘并且用$\text{M}\ddot{\text{o}}\text{bius}$环代替的球体同胚.我们将在$\text{Chapter 7}$中对其进行证明.

![image-20230720202623711](./Image/20.png)



在球体上添加$n$个柄后形成的曲面称为亏格为$n$的可定向曲面.我们之所以称之为可定向曲面是因为以下原因:如果我们在其上绘制一条平滑闭曲线,在某一点选择其切向量与法向量(即在该点选择一个坐标系,通常称为局部定向),而后将这些向量沿着曲线推进一周,会回到相同的坐标系上(即切向量与法向量方向保持不变)如$\text{Figure 1.19}(a)$所示.包含$\text{M}\ddot{\text{o}}\text{bius}$环的任何曲面,也就是列表中的后面那类,都无法满足这个性质,因此被称为不可定向曲面.$\text{Figure 1.19}(b)$显示了当我们将切向量和法向量沿$\text{M}\ddot{\text{o}}\text{bius}$环的中心推进一周之后发现——法向量会反向(注意看$5$和$1$)

曲面的分类是由$\text{M}\ddot{\text{o}}\text{bius}$$(1790-1860$)在一篇提交给巴黎科学院的参与获奖的数学论文中首次提出并继续深入探讨了可定向情况下的曲面分类问题,当时他已经是$71$岁高龄.但是评委会认为收到的所有稿件都不值得获奖,因此$\text{M}\ddot{\text{o}}\text{bius}$的工作最终只是作为另一篇数学论文发表出来.


## 拓扑不变量

我们应该能够马上发现我们不可能对于所有的拓扑空间进行分类.然而,我们想开发一种方法来确定两个具体的空间,比如两个曲面之间是否同胚.

不难发现证明两个空间的同胚关系是一个几何问题,涉及到它们之间构造一个特定的同胚.此处所用到的方法因问题而异.我们已然给出了一个例子(至少在轮廓上)表明$\text{Klein}$瓶同胚于一个球面移除两个不相交的圆盘并将其转化为$\text{M}\ddot{\text{o}}\text{bius}$环后的曲面.

试图证明两个空间彼此不同胚是一个性质完全不一样的问题,我们不可能在两个空间之间检查它们之间所有的函数来得到它们不同胚.相反,我们通过寻找空间中的一个"拓扑不变量":这是一个可能代表了空间的几何属性的不变量(类似于$\text{Euler}$数),被空间或者代数系统所定义(例如由空间所构造的群和环)重要的是,同胚可以保留不变量——因此得名.如果我们怀疑两个空间不同胚,我们可以通过计算一些合适的不变量并且表明它们有所不同来证实我们的怀疑.下面举两个例子.

在$\text{Chapter 3}$中我们将介绍连通性的概念:简单粗暴的说,如果空间是一体的,那么空间就是连通的.这个概念可以非常精确,如果我们将一个同胚应用到空间上,我们将发现其连通的性质是保留的,即连通是一个拓扑不变量.平面$\mathbb{E}^2$就是一个连通空间的例子.假设现在我们有一个同胚$h : \mathbb{E}^1 \to \mathbb{E}^2$.它将诱导一个同胚从$\mathbb{E}^1\setminus \{0\}$到$\mathbb{E}^2\setminus\{h(0)\}$.但是$\mathbb{E}^2$去掉一个点是一个连通空间(它是一体的)然而$\mathbb{E}^1 \setminus \{0\}$不是连通的.于是我们得知$\mathbb{E}^1$和$\mathbb{E}^2$不同胚.

第二个例子,我们将考虑一个源于$\text{Poincar}\acute{\text{e}}$的结构(这是$\text{Chapter 5}$的主题)其思想是给每一个拓扑空间都分配一个群,使得同构空间的群互相同构,那么若我们想要区分两个空间,就可以使用代数的方法来解决这个问题,首先计算它们的群,然后观察这些群是否同构,若群不同构,则两个拓扑空间彼此不同胚.当然,我们可能会不幸的得到同构群(这个时候还不能认为两个拓扑空间同胚)就需要额外找其他的拓扑不变量来区分这两个空间.

![image-20230723195922508](./Image/21.png)

考虑$\text{Figure 1.20}$中所展示的两个空间,我们不期望它们是同胚的,毕竟环($\text{annulus}$右侧)上有个洞而圆盘(左侧)上没有.

![image-20230723200240612](./Image/22.png)

这个洞可以很好地用回路$\alpha$来表示如$\text{Figure 1.21}$所示.正是这个洞阻止了我们不断地收缩,在不离开环的情况下收缩到一点,而在圆盘中,任意回路都可以连续的收缩到一点.$\text{Poincar}\acute{\text{e}}$的结构利用像$\alpha$一样的回路构建一个群(称为这个环的基本群),这个群包含环有一个洞的事实.

像$\alpha$这样的回路会造成一个带有非平凡元素的基本群.重新观察环面,从对于洞的识别的角度上看,回路$\beta$和回路$\alpha$是一致的,因为它可以在不穿过洞的前提下连续地转化为回路$\alpha$.这就表明回路$\beta$与回路$\alpha$在基本群中应当代表同样(类型)的元素.

从特定点开始和结束的一个回路应当意味着有一种自然的将这些回路相乘的方式.我们将两个回路的乘积$\alpha \cdot \beta$定义为一个先穿过$\alpha$然后穿过$\beta$的回路.在这种乘法下,回路本身并不构成一个群,但是若我们意识到一个回路可以连续地变为另一个回路(不需要移动它们的终点),那么我们就可以从这些回路的等价类(即顺逆时针绕过洞的次数是一个等价关系)中得到一个群.

> 我们将沿着顺时针绕过一次洞的回路$\beta$记为$-1$,将沿逆时针绕过一次洞的回路$\alpha$记为$1$,将回路$\alpha \cdot \beta$记为$0$,那么我们可以发现上述乘法类似整数的加法.
>
> 那么不难发现这个乘法满足封闭性(对于任意的回路$a$和$b$均满足$a \cdot b$为一个绕过洞可列次的回路)
>
> 结合律:$(a\cdot b)\cdot c$表示先经过$a\cdot b$再经过$c$的回路,即先经过$a$,再经过$b$最后经过$c$的回路,$a\cdot(b\cdot c)$表示经过$a$后经过$b\cdot c$的回路,将$b\cdot c$转义为先经过$b$再经过$c$的回路即可.于是发现$(a\cdot b) \cdot c = a \cdot(b\cdot c)$
>
> 于是可以得知基本群是一个半群.
>
> 由于前文中将$\alpha \cdot \beta$回路记为$0$,这也表示这是一个朝顺时针绕洞和逆时针绕洞次数相同或不绕过洞的回路.对于任何回路$a$都有$a\cdot 0 = a$即其逆时针绕洞次数为$a$次.于是基本群是一个含幺半群.
>
> 对于任意的$a$都存在回路$-a$使得其$a\cdot( -a )= 0$(将$-a$拆解为若干个$\beta$的乘积即可),于是基本群是一个群.
>
> 不难发现,环上的基本群同构于整数加法群.

以上的讨论是相当精确的,从数学上来讲,拓扑空间$X$中的一个回路不过是一个连续函数$\alpha : C \to X$,其中$C$表示复平面上的一个单位圆,并且若$\alpha(1) = p$则称回路的起点和终点都在$X$中的点$p$上.将$C$参数化为$\{e^{i\theta}: 0 \leq \theta \leq 2\pi\}$在我们的图中,回路上的箭头表示增加$\theta$的方向.翻转箭头就可以产生一个不同的回路,并且这是在基本群中原回路相应元素的逆.回路大概是一个将$C$中的所有元素都送到$p$点的函数,这代表着这个基本群的单位元.

![image-20230724150928214](./Image/23.png)

圆盘上的基本群则是一个平凡群,因为其上的任意回路都可以连续地缩小到一点上(我们将在$\text{Chapter 5}$对于连续变形进行定义).对于圆环,我们得到了一个整数的无限循环群.在$\text{Figure 1.22}$中分别展示了代表$0,-1$和$2$的回路.

不难想象,同胚的空间具有同构的基本群.毕竟,若$\alpha : C \to X$是一个$X$上的回路,且$h :X \to Y$是一个同胚映射,那么考虑$h \circ \alpha: C \to Y$定义了一个$Y$上的回路.连续变形也通过同胚发生.

于是,我们得出圆环与圆盘是不同胚的.

对于我们来说,完成这个介绍并且提前捕捉了后面章节的内容(不说人话就是:为后文做铺垫)的最好方法是列出一些问题(三个几何问题,一个代数问题),我们将使用基本群来辅助解决.

$Classification\,\, of\,\,surface$(曲面分类)在定理$1.5$中给出的任意两个曲面都没有同构的基本群,所以这些曲面在拓扑上是不同的.

$Jordan \, \, separation\,\, theorem$($\text{Jordan}$分离定理)平面上任何简单的闭合曲线都将平面分成两个部分.

$Brouwer\,\, fixed-point \,\, theorem$(在代数拓扑中会进行进一步证明,$\text{Brouwer}$不动点定理)任何从圆盘到其自身的连续函数都至少有一个固定点.

$Nielsen-Schreier\,\, theorem$($Nielsen-Schreier$定理)一个自由群的子群也是自由的.

# 习题

1. 证明对于任意树$T$均成立$v(T) - e(T) = 1$.

   由于树是一个不包含有任何回路的图(显然是连通的).

   于是可以得知$T$中任意两个点之间有且仅有一条由边所组成的链与之相连.

   先对于每个顶点进行编号$1,2,\cdots$,然后依次相连便得到了一个我们所求的树$(T')$

   接下来使用反证法进行证明,若$v(T) - e(T)< 1$,则顶点的数量小于边的数量$+1$,由于顶点和边的数量均为整数,即$v(T)\leq e(T)$,若$v(T) \leq e(T)$,则存在一条边连接两个可以由$T'$(这个边不属于$T'$)相连接的顶点,自然就会构成一个回路,这与树的定义相矛盾

   若$v(T) - e(T) >1$,那么就无法保证连通,由于一条边至少需要两个顶点连接,那么若$v(T) = n$,$e(T) \leq n$,假设这种情况下集合仍然构成一个图,那么令$n = 1$,不难发现$e(T) = 2$构成一个反例,于是$v(T) - e(T)>1$时无法保证连通性.

   > 或许我们可以使用数学归纳法对其进行一个严格的证明设$v(T) = n$,$e(T)$为保证$T$连通的最小边数(此处$T$不一定是树)
   >
   > 对于$n = 1$时,有$e(T) = 0$
   >
   > 对于$n = 2$时,有$e(T) = 1$
   >
   > 于是假设对于$n = k-1$时成立$e(T) = k-2$
   >
   > 那么对于$n = k$时,将$v(T)$划分为$k - 1$个顶点$T_1$与$1$个顶点$T_2$的两个部分,
   >
   > 那么对于$k - 1$个顶点的部分$T_1$有$e(T_1) = k-2$,而且我们只需要$T_1$中的一个点与$T_2$的那个点相连即可,于是得到$e(T) = e(T_1) + e[T_1,T_2] = k-2+1 = k-1$($[T_1,T_2]$表示连接两个图的最小边数,由于$T_2$是一个点,于是只有一条边)
   >
   > 于是得知$v(T) - e(T) \leq 1$时,图才有可能是连通的.

   所以对于任意树$T$均成立$v(T) - e(T) =1$.

   

2. 接着证明,$v(\Gamma) - e(\Gamma) \leq 1$对于任意的图$\Gamma$均成立,当且仅当$\Gamma$是树时取等号.

   由于我们所说的图都是连通的,于是根据前文的数学归纳法证明得知其成立.

   接着证明其取等号时必然为树.

   若$v(\Gamma) - e(\Gamma) = 1$时图$\Gamma$不为树,则$\Gamma$中至少存在一个回路(假设有一个回路).

   于是仿照前文数学归纳法中的讨论,设有$n$个顶点,将$n-1$个顶点划为一类,并且假设它们中没有回路,那么这$n-1$个顶点间的边数为$n-2$.接下来由于$\Gamma$中带有一个回路于是最后一个点与$n-1$个顶点之间至少有两条边连接,即$e(\Gamma) \geq n-2 + 2 = n$,这与$v(\Gamma) - e(\Gamma) = 1$矛盾.

   

3. 证明在任何图中我们总能找到一个包含所有顶点的树.

   使用数学归纳法进行证明.对于图$G$

   $v(G) = 1$时$G$自身就构成一个树.

   $v(G) = 2$时,由于$G$是连通的,于是必然存在一条边连接两个顶点,取这样的一条边以及$G$的两个顶点构成的树即可.

   设对于$v(G) = k-1$时成立,则对于$v(G) = k$时,可以将$G$的顶点划分为$k-1$个和$1$个顶点$j$.先不考虑$k-1$个顶点和$j$之间的联系,不难发现$k-1$个顶点所构成的图$G'$包含一个树$T'$并且该树$T'$不包含$j$.于是可以取$T'$中任意顶点$i$,连接$i$与$j$(由于$G$是一个图,连接了$j$的$i$是显然存在的)构成新图$T$,由于$T'$与$j$无连接,于是只有$i$连接上$j$时不会产生一个回路,并且有$v(T) = k,e(T) = e(T')+1 = k-1$即$T$确实为一个树.

   $T$显然是包含了$G$所有顶点的树.

   

4. 在$\text{Figure 1.3}$的多面体中找到一个包含所有顶点的树.构造对偶图$\Gamma$并证明$\Gamma$包含回路.

   ![image-20230713211346142](./Image/2.png)

   ![image-20230713235417615](./Image/5.png)

   上图为$\text{Figure 1.3}$的一个树,接下来我们构建其对偶图$\Gamma$

   ![image-20230713235353954](./Image/6.png)

   不难发现其存在一个回路(在内部和左上部分都构成了回路).

   (其实在正文中已经证明过了)

   

5. 接续第$4$题,加厚树$T$可以发现它编程了一个圆盘,那么加厚$\Gamma$会变成什么呢?

   由于前文所述,其在内部和多面体左上部分构成了两个回路,于是将其进行增厚应当会得到一条线连着的两个环,利用同胚将线缩小作为两个圆环的连接部分之后可以得到如下所示的形状.

   ![image-20230724142604004](./Image/24.png)

6. 设$P$是一个规则的多面体,且每个面有$p$条边,每个顶点有$q$个面相连接.使用$\text{Euler}$公式证明
   $$
   \frac{1}{p}+\frac{1}{q} = \frac{1}{2}+\frac{1}{e}
   $$
   其中$e$是边的总数.

   先回顾$\text{Euler}$公式
   $$
   v-e+f = 2
   $$
   由于每个面都有$p$条边,且$P$是一个规则的多面体,于是得到$pf = 2e$(每条边都被计算了两次),由于每个顶点都对接$q$个面(每个面接在顶点上都有两条边),而统共有$v$个顶点,于是可以得到$2e = qv$.

   那么我们可以将$\text{Euler}$公式转化为
   $$
   v-e+f = \frac{2e}{q}-e+\frac{2e}{p}=2e(\frac{1}{p}+\frac{1}{q}-\frac{1}{2}) = 2
   $$
   于是得到
   $$
   \frac{1}{p}+\frac{1}{q} = \frac{1}{2}+\frac{1}{e}
   $$

7. 从第$6$题中推出只有$5$个正多面体满足上述情况.

   首先,由于我们要构建一个多面体,于是其每个面的边数$p$必然满足$p \geq 3$.并且一个顶点至少要连接$3$个面(不然,两个面相交只会构成一条边),即$q \geq 3$

   通过观察上式得到$\frac{1}{p}+\frac{1}{q}\geq \frac{1}{2}$.对$p \geq 6$时,有$\frac{1}{q} = \frac{1}{3} +\frac{1}{e}$由于$e>0$于是得知此时$q < 3$,与$q \geq 3$矛盾.于是得到$p < 6$.

   那么对于$p$分别从$p = 3,4,5$进行测试即可.

   对于$p = 3$时,其每个面都是三角形,不难发现这样的多面体只有正四面体,正八面体和正二十面体.经过验算得知它们都符合要求.

   $p = 4$时,其每个面都是正方形,$\frac{1}{q} = \frac{1}{4}+\frac{1}{e}$得到正六面体满足条件.

   $p =5$时,正十二面体满足条件.

   

8. 检查$\text{Figure 1.3}$的$\text{Euler}$数$v-e+f =  0$.并且寻找一个与可以变为下图的多面体,并计算其$\text{Euler}$数.

   ![image-20230724151049130](./Image/26.png)

   对于$\text{Figure 1.3}$的验证不难进行,接下来将$\text{Figure 1.3}$中的多面体变成两个然后拼接起来,使其俯视图如下图所示,不难发现其与题目要求的几何图形同胚(去掉贴合部分).不难发现它有$38$个面(贴起来的那两个面不算),$76$个边,以及$36$个顶点.即$v+e-f = -2$

   ![image-20230724151529079](./Image/25.png)

   

9. 拿一个网球,观察它的表面被标记为沿其边界相交的两个圆盘的结合.

   读者自己去拿,乒乓球等其他球也可以(其实足球也可以,不过不一定规则,可以通过拓扑等价成规则的)

   

10. 求一个从实数到开区间$(0,1)$的同胚.证明任意两个开区间是同胚的.

    考虑函数$\arctan: \R \to (-\frac{1}{2}\pi,\frac{1}{2}\pi)$,不难发现$\arctan^{-1} = \tan$即$\arctan$具有连续逆,显然有$\arctan$是双射,即$\arctan$是一个同胚映射,即$\R$与$(-\frac{\pi}{2},\frac{\pi}{2})$同胚.

    我们只需要证明$(-\frac{\pi}{2},\frac{\pi}{2})$与任意开区间$(a,b)$同胚即可证明任意的开区间都是同胚的(由于同胚是一个等价关系,可以经过$(-\frac{\pi}{2},\frac{\pi}{2})$进行转化).

    接下来考虑$f(x) = (b-a)(\frac{x}{\pi}+\frac{1}{2})+a$得到这是一个$(-\frac{\pi}{2},\frac{\pi}{2})$到$(a,b)$的同胚,于是得到$\R$与$(0,1)$同胚,且任意两个开区间都是同胚的.

    

11. 想象$\text{Figure 1.23}$中展示的所有空间都是由橡胶制成的,对于每个空间$X,Y$,试着说服自己将$X$经由连续的变换变为$Y$

    ![image-20230724153447195](./Image/27.png)

    ![image-20230724153512687](./Image/28.png)

    $(\text{a})$,由正文的拓扑等价部分可以得知圆柱体与带有一个洞的圆盘同胚,于是可以得知$X$与$Y$同胚

    $(\text{b})$,将$X$中的小洞进行一个拉伸,变为一个几乎可以环绕圆环的条带,这样,就可以把圆环分开成为两个圆柱体.

    $(\text{c})$,套在一起即可

    

12. 

    ![image-20230724165720396](./Image/29.png)

    "立体投影"$\pi$是一个如$\text{Figure 1.24}$所示的从一个去掉了北极点的球面上投射到平面上的映射,请求出$\pi$的公式并且验证$\pi$是一个同胚.

    注意到$\pi$给我们提供了一个从一个移除了南北极点的球面到去掉原点的平面的同胚.

    [求解]

    将球面设为单位球,即$S^2 = \{x\in \R^3: \|x\| = 1\}$.去掉其北极点$(0,0,1)$.取$p= (x_0,y_0,z_0) \in S^2 \setminus\{(0,0,1)\}$就得到了定义域,不难发现其向量为$(0-x_0,0-y_0,1-z_0) = (-x_0,-y_0,1-z_0)$.根据我们在解析几何中学习的直线方程可以得知该直线的一般方程为
    $$
    \frac{x}{-x_0} = \frac{y}{-y_0} = \frac{z-1}{1-z_0}
    $$
    将$z = 0$带入得到$\frac{x}{-x_0} = \frac{y}{-y_0} = \frac{1}{z_0 - 1}$即$x = \frac{x_0}{1-z_0},y = \frac{y_0}{1-z_0}$.

    于是得到$\pi(x,y,z) = (\frac{x}{1-z},\frac{y}{1-z})$.

    接下来验证$\pi$确实是一个同胚,需要验证$\pi$是一个双射,连续且具有连续逆.

    1. 验证$\pi$是双射

       对于任意的$(x,y,z) \in S^2\setminus\{(0,0,1)\}$,不难发现由于$z\neq 1$于是得到$\frac{x}{1-z}$以及$\frac{y}{1-z}$都是有意义的,即$\pi$是良定义的.

       接下来验证$\pi$是单射若存在$(x_1,y_1,z_1)$和$(x_2,y_2,z_2)$使得$\frac{x_1}{1-z_1} = \frac{x_2}{1-z_2},\frac{y_1}{1-z_1} = \frac{y_2}{1-z_2}$得到$x_1 = \frac{(1-z_1)x_2}{1-z_2}$,同理得到$y_1 = \frac{(1-z_1)x_2}{1-z_2}$.那么
       $$
       x_1^2 + y_1^2 +z_1^2 = \frac{(1-z_1)^2x_2^2}{(1-z_2)^2}+\frac{(1-z_1)^2y_2^2}{(1-z_2)^2}+z_1^2 = \frac{(1-z_1)^2(x_2^2+y_2^2)}{(1-z_2)^2}+z_1^2 = 1
       $$
       于是得到
       $$
       \frac{1-z_1^2}{(1-z_1)^2} =  \frac{(x_2^2+y_2^2)}{(1-z_2)^2} = \frac{1-z_2^2}{(1-z_2^2)}
       $$
       推出$z_1 = z_2$.于是有$x_1 = x_2,y_1 = y_2$.即$\pi$是单射

       验证$\pi$为满射,即说明对于任意的$(x,y)\in \R^2$存在$(x_0,y_0,z_0) \in S^2\setminus\{(0,0,1)\}$使得$x = \frac{x_0}{1-z_0},y = \frac{y_0}{1-z_0}$.此时有$x_0 = (1-z_0)x,y_0 = (1-z_0)y$从而$(1-z_0)^2(x^2+y^2)+z_0^2 = 1$得到$x^2 + y^2 = \frac{1-z_0^2}{(1-z_0)^2}$.
       $$
       \frac{1-z_0^2}{(1-z_0)^2} = \frac{1-z_0^2}{1-2z_0+z_0^2} = \frac{2-2z_0}{(1-z_0)^2} - 1 = \frac{2}{1-z_0}-1
       $$
       由于$z_0 \in [-1,1)$于是可以得知$\frac{2}{1-z_0}-1$的值域为$\R_{\geq 0}$.即对于任意的$x^2 + y^2 = r$上的$(x,y)$存在一个$z_0$使$r = \frac{1-z_0^2}{(1-z_0)^2}$,那么由于半径$r \in \R$,$(x,y)$可以取遍所有从原点出发,任意$r\in\R$为半径的圆,便可以视为整个平面$\R^2$.于是$\pi$是满射.

    2. 验证$\pi$是连续的

       先接续上一步的工作$x^2+y^2 = \frac{2}{1-z_0} - 1$于是有$1-z_0 = \frac{2}{x^2+y^2 + 1}$,即$z_0 = \frac{x^2+y^2 -1}{x^2+y^2 +1}$.于是得到$(x_0,y_0,z_0) = \frac{1}{x^2+y^2 + 1}(2x,2y,x^2+y^2-1)$.

       取$\R^2$上一点$p = (x,y)$,接着使用欧式空间对于邻域的定义得到其邻域$N(p)$.$\forall q = (x',y')\in N(p)$存在$r$使得$\|p-q\|\leq r$,接下来计算$\|\frac{1}{x^2+y^2 + 1}(2x,2y,x^2+y^2-1) - \frac{1}{x'^2+y'^2 + 1}(2x',2y',x'^2+y'^2-1)\|\leq r'$,于是得知$\pi^{-1}(N)$是关于$\pi^{-1}(p)$的邻域.

    3. 同理可证$\pi^{-1}$是连续的.

    于是$\pi$是一个同胚映射.

    

13. 设$x$和$y$是球面上的点,求一个将$x$变为$y$的球到自身的同胚映射.然后使用平面和环面代替球面做同样问题.

    由于题目中要求将$x$映射为$y$,这本质上是对于$x$绕着原点进行一个旋转,显然是一个等距变换.

    接下来介绍关于三维旋转群的有关内容,并且使用三维旋转群对于本题进行求解

    > $SO(3)$三维旋转群
    >
    > 围绕原点的旋转是一种保持原点,欧式距离(因此是等距的)以及方向的变换,将两个旋转组合成另一个旋转,每个旋转都有一个唯一的逆旋转.显然恒等映射满足旋转的定义.不难发现,所有旋转的集合构成一个群.
    >
    > 每一个非平凡的旋转都是由其旋转轴(一条穿过原点的直线)和其旋转角度所决定的.不难发现旋转是不可交换的(在$xy$平面上沿着$R$旋转$90$度,然后在$yz$平面上沿着$S$旋转$90$度,其中$S$与$R$不一样)因此旋转群是一个非$\text{Abel}$群
    >
    > 由于旋转是一个$\R^3$上的线性变换,因此一旦选定$\R^3$的基,就可以用矩阵来表示.若我们选定了一个$\R^3$的正交基,那么每一次旋转都可以用行列式为$1$的$3 \times 3$正交矩阵来表示.不难发现$SO(3)$可以视为这些矩阵在矩阵乘法之下的群.这些矩阵被称为"特殊正交矩阵($\text{special orthogonal matrices}$)",这也是$SO(3)$符号的由来

    接下来考虑$S^2$和$SO(3)$,不难发现把$x$映射为$y$的过程是一个线性变换,且由于其本质上是绕原点进行旋转,于是存在$X \in SO(3)$将$x$映射为$y$.由于$|X| = 1$于是$X^{-1}$存在.

    不难发现以$X$为矩阵的线性变换(线性变换一定连续)显然是双射(行列式为$1$,可逆)且连续,且其逆显然也是连续的,于是这是一个球到自身的同胚映射.

    对于平面上的情况,考虑$(x_1,y_1),(x_2,y_2)\in \R^2$可以构建一个映射$f(a,b) = (x_1+x_2-a,y_1+y_2-b)$将$(x_1,y_1)$映射至$(x_2,y_2)$.并且它显然是一个双射,连续且具有连续逆.于是它是一个同胚

    对于环面,我们将其想象成两个$S^1$的直积即可($S^1 \times S^1$)

    

14. 用一张长方形的纸做一个$\text{M}\ddot{\text{o}}\text{bius}$环,沿着它的中心圆(环带中心所围成的圆)剪下去.结果如何?

    自己动手试试就知道力,结果应该是两个圆柱面

    

15. 沿圆切一条$\text{M}\ddot{\text{o}}\text{bius}$环,该环位于环的边界和中心圆的中间.对距离边界三分之一处的圆做同样的处理.得到的空间是什么

     懒得写了,要不自己试试

    

16. 现在拿一条有一个完全扭曲的带子,沿着它的中心圆环切开,看看会发生什么.

    同上懒

    

17. 定义$f:[0,1) \to C$使得$f(x) = e^{2\pi i x}$,证明$f$是一个双射并且是连续的.找出一个$x \in [0,1)$对于$x$的邻域$N$,证明$N$不是$f(N)$的邻域

    考虑$\text{Euler}$公式$e^{2\pi i x} = \cos(2\pi x)+i \sin(2\pi x)$可以得到若存在$x,y$使得$f(x) = f(y)$则有$2\pi x = 2\pi y$即$x = y$.

    对于任意的$y \in C$,有$y = (x',y')$且满足$x'^2 + y'^2 =1$于是可以令$x' = \cos \theta$,$y' = \sin \theta$得到$y = \cos \theta + i\sin \theta = \cos(2\pi y_0)+i \sin(2\pi y_0)$.

    于是存在$y_0 \in [0,1)$使得$f(y_0) = y$.于是$f$是一个双射.

    由于$\cos$和$\sin$均为连续函数,$f$显然也是一个连续的函数.

    考虑$[0,\frac{1}{2})$这是一个关于$0$的邻域,而$f([0,\frac{1}{2}))$不是一个关于$f(0) = 1$的邻域($1$是其界点,而不是其内点,所以有$f([0,\frac{1}{2}))$的开核$f([0,\frac{1}{2}))\mathring{}$并不包含$1$)于是根据邻域的公理得知其逆不连续.

    

18. 如果你对问题11$(b)$有困难,做一个环面减去圆盘的模型如下.从一个正方形开始,用通常的方法来确定它的边,从而得到一个环面($\text{Figure 1.25}$).注意,四个阴影区域合在一起代表环面中的一个圆盘.将这些区域从正方形中剪出,然后在正方形边缘的其余部分上进行标识.

    ![](./Image/30.png)

    

19. 令$X$为一个拓扑空间,$Y$为$X$的一个子集,检验我们先前说的子空间拓扑确实是$Y$上的拓扑

    > 设$X$是一个拓扑空间,$Y$是$X$的一个子集,我们可以通过如下方式来定义$Y$上的拓扑:对点$y \in Y$取其在$X$中的一组邻域集合再对每个邻域与$Y$求交集,这样就得到了$y$在$Y$中的一组邻域其关于拓扑空间的公理是很容易验证的,我们称$Y$有一个子空间拓扑.这是一个非常有用的步骤,比如它允许我们把欧式空间中的任何子集视为一个拓扑空间.特别地,我们的曲面例子也就称为了一个拓扑空间.

    即验证$y \in Y$在$X$上的一组邻域与$Y$的交集是$y$在$Y$上的邻域,设$N$是$X$上关于$y$的一个邻域,不难发现$y \in N \cap Y$.若$N \cap Y$是$y$的邻域,且还存在一个邻域$N'$也是$y$的邻域,则$y \in N \cap N'$,即$N \cap N'$也是$y$的邻域(由于$N\cap N'$自动蕴涵$N \cap Y$,在此处只用$N \cap N'$来表示).显然有$N\cap Y \subset Y$于是$Y$也是$y$的一个邻域(这是显然的).不难发现开核的公理也是可以验证的.于是$N\cap Y$确实是$y$在$Y$上的邻域.

    

20. 证明$\text{Figure 1.8}$所示的径向投影是从四面体表面到球体的一个同胚(假设这两个空间都具有来自$\mathbb{E}^3$的子空间拓扑)

    将其想象成橡皮构造即可,不难发现它们可以连续地互相转化,于是径向投影是一个同胚.

    

21. 令$C$是复平面上的一个单位圆,$D$是一个以它为边界的圆盘,现在有两个点$x,y \in  D \setminus C$找到一个交换$x$和$y$并且对$C$中所有其他$C$上的点均不变的同胚.

    乍一看很容易,但是实际做起来还是很麻烦的.

    注意到对于$a\in \C$,考虑函数$f(z) = \frac{z-a}{1-\overline{a}z}$.它将$S^1$映射为它自身.接下来假设$|z| = 1$,有
    $$
    \begin{eqnarray*}
    \left|\frac{z-a}{1-\overline{a}z}\right| &=& \left|\frac{z-a}{\overline{z}z-\overline{a}z}\right|\\
    &=&\left|\frac{z-a}{(\overline{z}-\overline{a})z} \right|\\
    &=& \left|\frac{z-a}{\overline{z-a}} \right|\frac{1}{|z|}\\
    &=& 1
    \end{eqnarray*}
    $$
    当$|a|<1$时,分母是不会消失的,于是它在$D$上是一个连续函数.且有$f(0) = -a$,所以若$|a|<1$(将$D$映射到$D$)由于$f$将$C$映射到它自身且$0$映射至$-a\in D\setminus C$,$f$必须将$D$映射到它自身.其逆也是一个连续的从$D$映射到$D$且将$C$映射到$C$.现在假设$x,y \in \C$且有$|x|<1,|y|<1$令
    $$
    f_1(z) = \frac{z-x}{1-\overline{x}z}
    $$
    以及
    $$
    f_2(z) = \frac{z-ty_1}{1-t\overline{y_1}z}
    $$
    其中$y_1 = f_1(y)$且$t = \frac{1-\sqrt{1-|y_1|^2}}{|y_1|^2}$,不难发现$f_1$和$f_2$均把$C$映射为它自身.

    最后,令
    $$
    g(z) = ze^{i(1-|z|)\pi/(1-|x_2|)}
    $$
    其中$x_2 = f_2(0)$.于是有$g(x_2) = -x_2$且$g(-x_2) = x_2$,对于其他的$z\in C$均有$g(z) = z$.由于$z\mapsto |z|$是连续的,且$g$由加法乘法以及连续函数的复合所构成,因此$g$是连续的.

    不难发现$f_1^{-1}f_2^{-1}gf_1f_2$即我们所需要的函数.

    

22. 延续上文的$C$和$D$,定义$h: D\setminus C \to D \setminus C$如下
    $$
    h(0) &=& 0\\
    h(re^{i\theta})&=&r\exp \left[i\left(\theta+\frac{2\pi r}{1-r}\right)\right]
    $$
    证明$h$是一个同胚,但是$h$不能被拓展为一个$D$到$D$上的同胚.绘图表明$h$对于$D$的直径的影响.

    使用$\text{Euler}$公式$e^{2\pi i x} = \cos(2\pi x)+i \sin(2\pi x)$对于$h$进行分解得到.
    $$
    h(r(\cos(\theta) + i\sin(\theta))) = r\left(\cos(\theta+\frac{2\pi r}{1-r})+i(\sin(\theta+\frac{2\pi r}{1-r})\right)
    $$
    可以发现:

    限制在半径为$r$的圆上的函数$h$的作用是旋转$\frac{2\pi r}{1-r}$弧度.

    现在当$r\to 1$时$\frac{2\pi r}{1-r} \to\infty$.因此当半径趋向于$1$时,旋转的角度便越来越大,最后趋近于无穷.

    因此在直观上可以很明显的看出这不能拓展到边界.由于题目中所给予的条件是$h(re^{i\theta})$也就是说我们或许可以将其视为一个极坐标来判断,使用$r$表示半径长度,$\theta$表示角度.

    现在,我们使用极坐标$(r,\theta)$来表示$\R^2$.并且使用$\R^2$的规则来定义$\C$上的拓扑.因此关于$r$和$\theta$的函数不过是一些连续函数的求和,乘积与商还有复合运算的产物,由于$|r|<1$时分母不为$0$,于是可以得知$h$确实是一个关于$r$和$\theta$的在$D$上连续的函数$h:(r,\theta) \to (r,\theta+\frac{2\pi r}{1-r})$.由于我们要求$|r|<1$于是可以得知$h$是可逆的.

    接着求出$h$的逆(只需要将$\theta$变为$\theta - \frac{2\pi r}{1-r}$即可)
    $$
    h^{-1}(0) &=& 0\\
    h^{-1}(re^{i\theta})&=& r\exp\left[i(\theta-\frac{2\pi r}{1-r}) \right]
    $$
    根据前文的讨论可以同理得到$h^{-1}$也是连续的,于是可以得知$h$是一个同胚

    接下来证明$h$不能拓展到$D$上.我们只需要证明$\lim_{r \to 1}h(re^{i\theta})$不存在即可.

    即证$(r,\theta) \to (r,\theta + \frac{2\pi r}{1-r})$在$r\to 1$时极限不存在.其重点在$\frac{r}{1-r}$上.根据$\text{Heine}$定理(归结原则)可以取一个数列$\{a_n\}$使得在$n \to \infty$时,$a_n \to 1$,这样$a_n$就可以代替$r$,我们只需要证明$\lim_{n \to \infty} h(a_n)$不存在即可.

    可以从$\frac{r}{1-r}$入手.

    欲证极限不存在,只需要证明其两个子列$\{a_k\}$和$\{a_m\}$的极限不一致即可.不难发现我们可以构造一个数列$\{b_n\}$使得$\frac{b_n}{1-b_n} = \frac{1}{k}n$不难得出$\frac{n}{n+k}$是一种可能的数列.于是我们可以构造$a_m = \frac{m}{m+1}$以及$a_k = \frac{k}{k+2}$.得到它们的极限分别为$\lim_{m \to \infty}a_m = m$以及$\lim_{k \to \infty} a_k = \frac{k}{2}$.

    带入$h$中可以得知$\lim_{m \to \infty}h(a_m,\theta) = (a_m,\theta + 2\pi m) = (a_m , \theta)$($m$为整数)$\lim_{k \to \infty} h(a_k ,\theta) = (a_k,\theta +\frac{2\pi k}{2}) = (a_k , \theta +k\pi)$.发现当$k$为奇数,$m$为偶数时它们不相等.

    于是,将$\{a_k\}$与$\{a_m\}$视为$\{a_n\}$在奇数$(k)$与偶数$(m)$情况下的值便可以得到极限不存在.

    

23. 利用连通性证明一个圆和一个带刺的圆(如$\text{Figure 1.26}$所示)是不同胚的.

    ![image-20230728223845742](./Image/31.png)

    题目要求使用连通性证明圆和带刺的圆不同胚,由于连通是拓扑不变量,我们只需要证明圆和带刺的圆上的连通并不一致即可.

    若圆和带刺的圆是同胚的,它将诱导一个同胚$h : \text{Circle}\setminus{p(\text{a point})} \to \text{Circle with spike}\setminus{q(\text{a point})}$.

    由于$\text{Circle}\setminus{p}$还是连通的(从任一点出发可以从绕过$p$点通过其他的点到达空间内其他点).而当$q$在$\text{spike}$上时,$\text{spike}$上的其他点与圆上的点不连通.

    于是根据连通性得到圆与带刺的圆不同胚.

    

24. 令$X$和$Y$为$\text{Figure 1.27}$所示空间的子空间,从圆环上的同胚必须使其两个边界圆的点互相映射这一假设出发,论述$X$和$Y$不可能同胚.

    ![image-20230728224756736](./Image/32.png)

    由于我们假设两个边界圆上的点互相映射,于是可以取$X$上两个$\text{spike}$与圆的交点.若存在$X$与$Y$之间的同胚,那么这两个交点将被映射到$Y$上$\text{spike}$与圆的两个交点上(否则将会破坏连通性).

    根据假设得知$X$内侧圆上的交点无法映射到$Y$的外侧圆上.于是$X$与$Y$不可能同胚.

    

25. 保持$X$和$Y$如上,考虑$\mathbb{E}^3$上的两个形如
    $$
    X\times [0,1] = \{(x,y,z) : (x,y) \in X, 0 \leq z \leq 1\}\\
    Y \times [0,1] = \{(x,y,z) : (x,y) \in Y, 0 \leq z \leq 1\}
    $$
    的子空间,说服你自己将这两个空间视为是橡胶制成的,那么它们可以相互变形,因此它们是同胚的.

    

    先对于圆环部分进行考虑,$X \times [0,1]$与$Y \times [0,1]$会将圆环变成一个沿$z$轴截面为矩形的环面,将这两个空间视为橡皮空间后可以将矩形变成圆形,那么我们就得到了一个"甜甜圈(环)",这对于我们下一步操作非常重要.

    接下来我们对$\text{spike}$部分构成的矩形进行考虑,把$X$上内侧的那个矩形往外翻,由于我们上一步已经将矩形变成了圆形,不用担心这会造成矩形的扭曲问题.

    于是我们可以将环内的矩形移到环外的边界圆上.由于同胚是一个等价条件可以得知,$X \times [0,1]$与$Y \times [0,1]$是同胚的.

    

26. 与27.均为手操脑补题,不做了(实际上是懒)

 	
