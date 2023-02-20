三对角行列式 
$$
D_n = \left \vert \begin{matrix} a+b & b & 0 & \cdots & 0 & 0 \\
a & a+b & b & \cdots & 0 & 0 \\ 
0 & a & a+b & \cdots & 0 & 0 \\
\vdots & \vdots & \ddots & \ddots & \ddots & \vdots \\
0 & 0 & 0 &\cdots & a+b & b \\ 
0 & 0 & 0 & \cdots & a & a+b\end{matrix}\right\vert_n = \frac{a^{n+1}- b^{n+1}}{a-b}.
$$
这里要求$a \neq b$. 如果$a=b$, $D_n= (n+1)a^{n} =(n+1)b^n$. 

但注意

$a^{n+1}-b^{n+1} = (a-b)(a^n + a^{n-1}b + a^{n-2}b^2 + \cdots + ab^{n-1}+b^n)$. 

所以无论$a, b$是否相等，总有$D_n = a^n + a^{n-1}b + a^{n-2}b^2 + \cdots + ab^{n-1}+b^n$. 

我们将计算出下面的行列式：
$$
T_n = \left \vert \begin{matrix} c & b & 0 & \cdots & 0 & 0 \\
a & c & b & \cdots & 0 & 0 \\ 
0 & a & c & \cdots & 0 & 0 \\
\vdots & \vdots & \ddots & \ddots & \ddots & \vdots \\
0 & 0 & 0 &\cdots & c & b \\ 
0 & 0 & 0 & \cdots & a & c\end{matrix}\right\vert_n
$$
这样，只要取$c=a+b$，就能得到$D_n$的计算公式。

下面用递推法计算$T_n$：按首行展开$T_n$，得到$T_n = c\cdot (-1)^{1+1}\cdot T_{n-1}+ b\cdot (-1)^{1+2} \cdot a \cdot T_{n-2}$. 即
$$
T_n = cT_{n-1}-abT_{n-2}.
$$
我们希望有两个常数$r, q$，使得
$$
T_n - rT_{n-1} = q(T_{n-1}-rT_{n-2}).
$$
这样$\{T_n - rT_{n-1}\}$就是等比数列。比较上面两个式子的系数，可得$q+r=c, qr=ab$. 这表明$q, r$是方程
$$
x^2-cr+ab=0
$$
的两个根。由于这一点，我们可以期望
$$
T_n - qT_{n-1}=r(T_{n-1}-qT_{n-2})
$$
也成立。（而的确如此，因为对比(3),(6)两式的系数，一样可以得到$q, r$是$x^2-cr+ab=0$的两个根。）

按定义，$T_1=c, T_2 = c^2-ab$. 由(4)得到$T_n - rT_{n-1} = q^{n-2}(T_2-rT_1)=q^{n-2}(c^2-ab-rc) = q^{n}$. 同理由(6)可得$T_n - qT_{n-1}=r^n$. 现在只要从方程组
$$
\begin{cases}
T_n - rT_{n-1}=q^n, \\
T_n - qT_{n-1}=r^n,
\end{cases}
$$
中解出$T_n$即可。如果$q\neq r$, 则$T_n = \frac{q^{n+1} - r^{n+1}} {q-r}$ . 但如果$q=r$, 则只有一个方程$T_n - qT_{n-1}=q^n$. 此时有
$$
T_n = q^n + qT_{n-1}=q^{n}+q(q^{n-1}+qT_{n-2}) = \ldots = (n-1)q^n+ q^{n-1}T_1=(n+1)q^n. 
$$
如果$c=a+b$, 则方程(5)变成$x^2-(a+b)x+ab=(x-a)(x-b)=0$. 这样$(q, r)=(a, b)$或$(b, a)$. 我们得到$D_n$的公式. 

例子：我们把$\varphi= \frac{1+\sqrt{5} }{2}$称为黄金分割。如果取$q=\varphi, r = -1/\varphi,$ 则
$$
T_n = \frac{1}{\sqrt{5}}[\left(\frac{1+\sqrt{5}}{2} \right)^{n+1} - \left(\frac{1-\sqrt{5}}{2} \right)^{n+1} ]
$$
计算可得$T_0=1, T_1 = 1, T_2 = 2$. 可以证明$T_n = T_{n-1}+T_{n-2}$. 所以$\{T_n\}$就是Fibonacci数列. 

-------------------

我们还可以考虑更一般的三对角行列式：
$$
T_n(\mathbf{c, a, b}) = \left \vert \begin{matrix} c_1 & b_1 & 0 & \cdots & 0 & 0 \\
a_1 & c_2 & b_2 & \cdots & 0 & 0 \\ 
0 & a_2 & c_3 & \cdots & 0 & 0 \\
\vdots & \vdots & \ddots & \ddots & \ddots & \vdots \\
0 & 0 & 0 &\cdots & c_{n-1} & b_{n-1} \\ 
0 & 0 & 0 & \cdots & a_{n-1} & c_n \end{matrix}\right\vert_n
$$
电子计算机计算这个行列式的方法是"用初等行变换化为三角形矩阵". 我们假设$c_1 \neq 0$. 记上面的行列式为$ t_0$. 作初等行变换$r_2 + r_1 (-a_1/c_1)$. 则上式变成
$$
t_1 = \left \vert \begin{matrix} c_1 & b_1 & 0 & \cdots & 0 & 0 \\
0 & c'_2 & b_2 & \cdots & 0 & 0 \\ 
0 & a_2 & c_3 & \cdots & 0 & 0 \\
\vdots & \vdots & \ddots & \ddots & \ddots & \vdots \\
0 & 0 & 0 &\cdots & c_{n-1} & b_{n-1} \\ 
0 & 0 & 0 & \cdots & a_{n-1} & c_n \end{matrix}\right\vert_n
$$
其中$c'_2 = c_2 - a_1b_1/c_1$. 我们假设$c'_2 \neq 0$. 继续作初等行变换$r_3+r_2(-a_2/c'_2)$, 又可以把$t_1$的第(3, 2)位置变成0. 如此不断进行，最后就可以化$t_0$为上三角行列式，从而求出行列式的值$T_n(\mathbf{c, a, b})=t_0=t_1=\ldots =\prod_{i=1}^n c'_i $. 其中
$$
c'_1 = c_1,\; c'_2 = c_2-a_1b_1/c_1, \; c'_3 =c_3 - a_2b_2/c'_2,\; \ldots c'_n = c_n - a_{n-1}b_{n-1}/c'_{n-1}. 
$$
只要输入初始值$\mathbf{c, a, b}$, 用公式(12)编程求出$c'_1, \ldots, c'_n$，即可求出行列式. 