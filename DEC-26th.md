回忆：域的代数扩张，正规扩张，可分扩张，Galois扩张。
多项式的分裂域  Galois理论的基本定理

#方程的根式解
给定一个$\mathbb{Q}$-系数多项式$f(x)$，只用加减乘除，乘方，开方，把$f(x)$的根，表示成$f(x)$的系数的函数. 

$f(x)=ax^2+bx+c$     $x = \frac{-b\pm \sqrt{b^2-4ac}}{2a}$  $a\neq 0$. 

$f(x)=ax^3+bx^2+cx+d, \quad a\neq 0$.  

$x^3-d=0$   $x_1= \sqrt[3]{d}, x_2 = x_1 \omega,  x_3=x_1 \omega^2$,    $\omega = -\frac{1}{2}+\frac{\sqrt{-3}}{2}$.    


#分圆域
先研究：$x^3-1$  {$x^n-1$} 在$F=\mathbb{Q}$上的分裂域$E$, 问Gal$(E/F)=?$     已知Gal$(E/F)$的阶，等于域扩张$[E:F]$的次数.   $E/F$是一个单代数扩张，$E=F(\omega)$.

{$E=F(\zeta_n)$, $\zeta_n$是一个本原$n$-次单位根, 例如$\zeta_n = \exp(\frac{2\pi \sqrt{-1}}{n})$}  

问: $\omega=\zeta_3$   {$\zeta_n$} 在$F$上的极小多项式是什么？  
$x^3-1=(x-1)(x^2+x+1)=(x-1)(x-\omega)(x-\omega^2)$, $\omega=\zeta_3$.    

{Gauss: $x^n-1 = \prod_{d\vert n}\Phi_d(x)$}  {注意：if $d\vert n$, $\alpha^d =1 \Longrightarrow \alpha^n =1$. 由此可证$x^n-1$在$F=\mathbb{Q}$上的分裂域，等于$F(\zeta_n)$.}  

而$x^2+x+1$在$\mathbb{R}$上不可约，所以在$F=\mathbb{Q}$上也不可约 。 它就是$\omega$在$F$上的极小多项式。{需要证明$\Phi_n(x)$在$\mathbb{Q}$上不可约， 从而$\zeta_n$在$F$上的极小多项式就是$\Phi_n(x)$. }

所以$E/F$是二维{$\phi(n)$维}$F$-线性空间，所以Gal$(E/F)$的非单位元$s$，一定是把$E$的两个$F$-基向量对换. {Galois群的非单位元，置换$E$的$F$-基向量.}

可以有更好的描述：$E$的两个$F$-基向量是$\omega, \omega^2$, 那么$s(\omega)=\omega^2, s(\omega^2)=\omega = \omega^4$. 

定理：设$E$是$x^n-1$在$F=\mathbb{Q}$上的分裂域，那么$E=F(\zeta_n)$, 而且Gal$(E/F)$与$\mathbb{Z}/n\mathbb{z}$的单位群$U(\mathbb{Z}/n \mathbb{Z}) = (\mathbb{Z}/n \mathbb{Z})^\times = \{a \mid 1\leq a \leq n, (a, n)=1\}$同构. 具体地，$a \in (\mathbb{Z}/n\mathbb{Z})^\times$对应于$\zeta_n \mapsto \zeta_n^a$. 


*定义*：
1. 单（一个）根式扩张：$n=[K:F]$, 如果$\exists \alpha \in K$, st.  $K=F(\alpha), \alpha^n \in F$. 则称K/F是单根式扩张

2. 根式扩张：设K/F是一个有限扩张，如果可以找到中间域

$F=F_0 \subset F_1 \subset \cdots \subset F_m=K$    （根式扩张链）
 使得每一个扩张$F_{i}/F_{i-1}$都是单根式扩张, 则称$K/F$是一个根式扩张
 
3. 如果定义在$F$上的多项式$f(x)$, 它在F上的分裂域E, 包含在某一个根式扩张$K/F$中，那么我们说f的根，在F上，可以用根式求解。

目标是理解Galois的**定理**：设域$F$特征$0$. 又设$p(x)$是系数在$F$上的多项式, 它在$F$上的分裂域是$E$. 那么$p(x)$在$F$上可以用根式求解 当且仅当 Gal$(E/F)$是一个可解群. 

*例子*：$x^3-2$     $a=\sqrt[3]{2}, a\omega, a\omega^2$  是它的三个根. 它在$F=\mathbb{Q}$上的分裂域是$E=F(\omega, a)$.    记 $F_1=F(\omega)=\mathbb{Q}(\sqrt{-3})$.       

可知

$F \subset F_1 \subset E=F_1(a)$ 
是根式扩张。相应的Galois群序列是

$\{1\} \subset A_3 \subset S_3$  

注意：可解群的子群与商群，都是可解的. 

Gal$(F_1/F) = (\mathbb{Z}/3\mathbb{Z})^\times = \{\bar{1}, \bar{2}=-\bar{1}\}$.     Gal$(E/F_1)=\langle t \rangle$是一个三阶的（循环）群   （单位元，$a\mapsto a\omega$   $a\mapsto a\omega^2$)        问： Gal$(E/F)$=? 答案是$S_3$


找求根公式，有一个关键的**定理**：设$p$是素数，假如域$F$包含了$p$个不同的$p$次单位根($\zeta^j: j=0, 1, \ldots, p-2, p-1$)，那么F上任意一个p次循环扩张（即相应的Galois群$\langle s \rangle$，是p阶循环群），都是根式扩张。证明的关键，是用Lagrange的*预解式(resolvent)* : 设$K=F(\theta)$, 其中$\theta \in K \setminus F$. 用$p$次单位根，从$\theta$中，构造出一个新的生成元$\alpha$, 使得$\alpha^p \in F$. 

Lagrange resolvent: 用$1, \zeta, \zeta^2, \ldots, \zeta^{p-1}$依次与$\theta, s(\theta), s^2(\theta), \ldots, s^{p-1}(\theta)$相乘，然后求和. 

$(\zeta, \theta) := \theta + \zeta s(\theta) + \ldots + \zeta^{p-1} s^{p-1} (\theta)$.   

类似可以定义$(\zeta^j, \theta)$, 总有一个非零 （证明方法是计算所有p个$(\zeta^j, \theta)$的和，证明这个和非零）  

$s(\zeta, \theta) \neq (\zeta, \theta)$  $s((\zeta, \theta)^p)=(\zeta, \theta)^p \Longrightarrow (\zeta, \theta)^p \in F$  


----------------
#3次方程求根公式
在$F=\mathbb{Q}$上讨论三次方程求根公式 $f(x)=x^3+t_1x^2+t_2x+t_3$.

$F_1=F(t_1, t_2, t_3)$  

令$x=y-t_1/3$, $f(x)=g(y)=y^3+py+q$, 设$g$的根是$\beta_1, \beta_2, \beta_3$.
$p =-t_1^3/3+t_2,  q= \frac{1}{27}(2t_1^3-9t_1t_2+27t_3)$ 

$\delta:=\prod_{i< j}(\beta_i -\beta_j)$  (Vandermonde行列式)
$\Delta = \delta^2 = -4p^3-27q^2$ 是判别式.    $\Delta \in F_1$       $F_2:=F_1(\delta)$   

$E=F_2(\beta_1, \beta_2, \beta_3)$    是分裂域
重点：$F_2$是否有三个三次单位根？使用Lagrange resolvent，构造E中的一个元素$\alpha$, 使得$\alpha^3 \in F_2$. 

$(1, \beta_1)=\beta_1+ \beta_2+\beta_3 =0 \in E$, $(\omega=\zeta_3, \beta_1), (\omega^2, \beta_1)$   

已知$(\omega, \beta_1)^3, (\omega^2, \beta_1)^3 \in F_2(\omega)$ 

使用$X^3+Y^3 = (X+Y)(X+\omega Y)(X+\omega^2 Y)$, 计算可知
$(\omega, \beta_1)^3 + (\omega^2, \beta_1)^3 =27 \beta_1 \beta_2 \beta_3 = -27q$ (Vieta定理)
$(\omega, \beta_1)^3 \cdot (\omega^2, \beta_1)^3 = (\beta_1^3+\beta_2^3+\beta_3^3-\beta_1\beta_2-\beta_2\beta_3-\beta_1\beta_3)^3=(-3p)^3=-27p^3$       

结论：$(\omega, \beta_1)^3, (\omega^2, \beta_1)^3$ 是二次多项式$z^2+27qz-27p^3=0$的根.  不妨设

$(\omega, \beta_1)^3 = \frac{-27q}{2}+ \frac{3}{2}\sqrt{-3\Delta}$ , 
$(\omega^2, \beta_1)^3 = \frac{-27q}{2}- \frac{3}{2}\sqrt{-3\Delta}$. 

再开3次方根，共9对，但$(\omega, \beta_1) \cdot (\omega^2, \beta_1)=-3p$, 其实只有3种配对。任取其一，再代入公式
$\beta_1 = \frac{1}{3}((\omega, \beta_1)+ (\omega^2, \beta_1))$
$\beta_2 = \frac{1}{3}(\omega^{-1}(\omega, \beta_1)+ \omega^{-2}(\omega^2, \beta_1))$
$\beta_3 = \frac{1}{3}(\omega^{-2}(\omega, \beta_1)+ \omega^{-1}(\omega^2, \beta_1))$
就能求出$\beta_1, \beta_2, \beta_3$. 如果取其它配对，算出来的根，只差了一个轮换. 

--------------------
继续 #分圆域

定义: 设$\zeta_n$是任意一个本原$n$-次单位根.  $n$-次分圆域定义为$\mathbb{Q}(\zeta_n)$. 

回忆: $x^n-1 =\prod_{d\vert n} \Phi_d(x)$， $\Phi_n(x)=\prod_{\zeta \in \mu_n^\times(\mathbb{C})} (x-\zeta)$ 
定理：(1) $\mathbb{Q}(\zeta_n)$是$x^n-1$在$\mathbb{Q}$上的分裂域 （此因如果$a^d=1, d\vert n \Longrightarrow a^n=1$.) 
Galois群同构于$(\mathbb{Z}/n\mathbb{Z})^\times$, $a \in (\mathbb{Z}/n\mathbb{Z})^\times$对应于$\zeta_n \mapsto \zeta_n^a$. 
(2) $\Phi_n$在$\mathbb{Q}$上不可约. 它的根恰好是$\zeta_n$在Galois 群$(\mathbb{Z}/n\mathbb{Z})^\times$作用下的轨道. 
(3) 由(2)得知 $\zeta_n$在$\mathbb{Q}$上的极小多项式是$\Phi_n(x)$, 从而$[\mathbb{Q}(\zeta_n): \mathbb{Q}]=\phi(n)$. 

证明：$\sum_{j=1}^5\cos\frac{2j\pi}{5}$是一个有理数  

定义：极大实子域  $\mathbb{Q}(\zeta_n+\zeta_n^{-1})=\mathbb{Q}(\cos(\frac{2\pi}{n})) \; (n \geq 3)$  , 它是$\mathbb{Q}$的$\phi(n)/2$次扩张. 


**Kronecker - Weber theorem**: 所有的Abelian扩张，都包含于某个分圆扩张当中. 

#有限域
1. $p$是个素数: $\mathbb{F}_p=\{\bar{0}, \bar{1}, \ldots, \overline{p-1}\}$, 即环$\mathbb{Z}/p$有域的结构
2. 定理：如果$q=p^n$, 那么$\mathbb{F}_q$必定同构于$\mathbb{F}_p[x]/(x^{q^n}-x)$.  
   {上课时这里讲错了，已更正}
3.  如果$\mathbb{F}_{q^m} \subset \mathbb{F}_{q^n}$， 那么$m \vert n$. 反之亦然.
4. 有限域的可分扩张  比特征零域复杂，因为$(a+b)^p=a^p+b^p$   
5. $Fr_p: \mathbb{F}_q \to \mathbb{F}_q, \quad x\mapsto x^p$, $\mathbb{F}_q$的自同构，保持$\mathbb{F}_p$的元素不变. 它生成了Gal$(\mathbb{F}_q /\mathbb{F}_p)$

