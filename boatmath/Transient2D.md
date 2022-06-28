# Transient 2D

In the 1D case the ODE was

$$\begin{align}
\frac{dv}{dt} 
&= a_o - \mu v \\
&= A(v)\end{align}$$

Generalizing to vector form, the differential equation becomes:

$$ \frac{d\vec v}{dt} = \vec a_o - \mu \vec v $$

Since every term is linear, the components are independent of each other, so the result is simply the 1D transient solution applied to each component separately.

$$
\begin{align}
\vec d(t) &= \vec a_o f_2(t) + \vec v_o f_1(t) \\
\vec v(t) &= \vec a_o f_1(t) + \vec v_o f_0(t) \\
\vec a(t) &= (\vec a_o-\mu \vec v_o) f_0(t)
\end{align}
$$

$$\begin{align}
\mu\ne0:&
\begin{cases}
f_0(t)=e^{-\mu t}\\
f_1(t)=\frac{1-f_0(t)}{\mu}\\
f_2(t)=\frac{t-f_1(t)}{\mu}
\end{cases}
&\mu=0:
\begin{cases}
f_0(t)=1\\
f_1(t)=t\\
f_2(t)=\frac{t^2}{2}
\end{cases}
\end{align}$$

Since at any given situation, only the directions of $a_o$ and $v_o$ are involved, the resulting motion is always in the plane formed by your thrust and momentum vectors.

In other words, the problem can always be formulated in terms of the direction receiving full thrust, which is simply the 1D solution, and the direction in the plane that receives no thrust:

$$\begin{align}
\begin{pmatrix}
d_{\parallel} \\
d_{\perp}
\end{pmatrix}&=
\begin{pmatrix}
a_o\\
0
\end{pmatrix}f_2(t)+
\begin{pmatrix}
v_{o\parallel}\\
v_{o\perp}
\end{pmatrix}f_1(t)\\
\begin{pmatrix}
v_{\parallel} \\
v_{\perp}
\end{pmatrix}&=
\begin{pmatrix}
a_o\\
0
\end{pmatrix}f_1(t)+
\begin{pmatrix}
v_{o\parallel}\\
v_{o\perp}
\end{pmatrix}f_0(t)\\
\begin{pmatrix}
a_{\parallel}\\
a_{\perp}
\end{pmatrix}&=
\begin{pmatrix}
a_o-\mu v_{o\parallel}\\
0-\mu v_{o\perp}
\end{pmatrix}f_0(t)
\end{align}$$
