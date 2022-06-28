# Transient 1D

Total acceleration comprises of constant forward thrust $a_o$ and linear drag against velocity:

$$\begin{align}
\frac{dv}{dt} 
&= a_o - \mu v \\
&= A(v)\end{align}$$

Define velocity $v(t_o)=v_o$ and $v(t_o+\Delta t)=v_o+\Delta v$, we can integrate the above equation to find velocity progression over time:

$$\begin{align}
dt &= \frac{1}{a_o - \mu v} dv\\
\rightarrow \int\limits_{t=t_o}^{t=t_o+\Delta t}dt
&= \int\limits_{v=v_o}^{v=v_o+\Delta v} \frac{1}{ a_o - \mu v} dv\\
\rightarrow \Delta t
&= \int\limits_{v=v_o}^{v=v_o+\Delta v} \frac{1}{A}dv \\
&= \int\limits_{v=v_o}^{v=v_o+\Delta v} \frac{1}{A}\frac{dv}{dA}dA \\
&= \int\limits_{A=A(v_o)}^{A=A(v_o+\Delta v)} \frac{1}{A}\left(-\frac{1}{\mu}\right)dA \\
&= \left[-\frac{1}{\mu}\ln A\right]_{A=A(v_o)}^{A=A(v_o+\Delta v)} \\
&= -\frac{1}{\mu}\ln\left(\frac{a_o-\mu (v_o+\Delta v)}{a_o-\mu v_o}\right) \\
\rightarrow v_o + \Delta v
&= a_o\frac{1-e^{-\mu\Delta t}}{\mu} + v_o e^{-\mu\Delta t} \\
\implies v(t)
&= a_o\frac{1-e^{-\mu(t-t_o)}}{\mu} + v_o e^{-\mu(t-t_o)} 
\end{align}$$

Now that we have an explicit expression of velocity over time, finding displacement vs time is just a matter of integrating $v(t)$ with respect to $t$:

$$
\begin{align}
\Delta d 
= \int\limits_{t=t_o}^{t=t_o+\Delta t}v(t)dt 
&= \int\limits_{t=t_o}^{t=t_o+\Delta t} a_o\frac{1-e^{-\mu(t-t_o)}}{\mu} + v_o e^{-\mu(t-t_o)} dt \\
&= \left[a_o\left(\frac{t}{\mu}+\frac{e^{-\mu (t-t_o)}}{\mu^2}\right) + v_o\left(-\frac{e^{-\mu (t-t_o)}}{\mu}\right)\right]_{t=t_o}^{t=t_o+\Delta t} \\
&= a_o\frac{\Delta t-\frac{1-e^{-\mu\Delta t}}{\mu}}{\mu} + v_o\frac{1-e^{-\mu\Delta t}}{\mu} \\
\implies d(t) 
&= a_o\frac{(t-t_o)-\frac{1-e^{-\mu(t-t_o)}}{\mu}}{\mu} + v_o\frac{1-e^{-\mu(t-t_o)}}{\mu} + d_o
\end{align}
$$

If we define $d(t_o)=0$ and $t_o=0$ then the kinematic equations simplify to:

$$\begin{align}
d(t) &= a_o \frac{t-\frac{1-e^{-\mu t}}{\mu}}{\mu} + v_o \frac{1-e^{-\mu t}}{\mu} \\
v(t) &= a_o \frac{1-e^{-\mu t}}{\mu} + v_o e^{-\mu t} \\
a(t) &= (a_o-\mu v_o) e^{-\mu t} 
\end{align}$$

Notice that when $\mu=0$ (frictionless case) the equations reduce to constant-acceleration kinematics, i.e. 

$$\begin{align}
d(t)&=a_o\frac{t^2}{2}+v_o t \\ 
v(t)&=a_o t+v_o \\ 
a(t)&=a_o
\end{align}$$

We can therefore summarize the kinematic equations as:

$$
\begin{align}
d(t) &= a_o f_2(t) + v_o f_1(t) \\
v(t) &= a_o f_1(t) + v_o f_0(t) \\
a(t) &= (a_o-\mu v_o) f_0(t)
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

Or even more succinctly using prime notation:

$$
\begin{align}
q(t) &=
\begin{cases}
\frac{t}{\mu}-\frac{1-e^{-\mu t}}{\mu^2} & \mu\ne0 \\
\frac{t^2}{2} & \mu=0
\end{cases}\\
d(t) &= a_o q(t) + v_o q'(t) \\
v(t) &= a_o q'(t) + v_o q''(t) \\
a(t) &= a_o q''(t) + v_o q'''(t) \\
\end{align}
$$


https://www.desmos.com/calculator/nlknnwqeur
