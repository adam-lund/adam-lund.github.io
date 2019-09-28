---
layout: post
title: A take on a interview question
categories:
---

Question

Suppose you   independently  sample uniformly from the unit interval and then sum these samples. On average how many times would you have to do this before the sum is  bigger than one?


Answer

Let $(U_i)_{i\in \mathbb{N}}$ be iid uniform on $[0,1 ]$ and consider $S_n=\sum_i^nU_i$.


Define $\tau_x=\min_n\{n :S_n>x\}$ for $x\leq 1$ with the convention $\tau_x=0$ when $x\leq0$. Then we want to find $E(\tau_1)$.  


Clearly $S_{\tau_x}=S_{\tau_x+1 -1}$ so  $\tau_x+1$ is the smallest $n\in \mathbb{N}$ such that $S_{n-1}>x$.
 Using this fact and the independence we have   for $x\leq1$

$$
  E(\tau_x\mid U_1=u)
&  =  E(\min_{n }\{n:\sum_{i=1}^{n-1}U_{i+1} >x-u\}\mid U_1=u)\\
 & =   E(\min_{n }\{n  :S_{n-1} >x-u\})\\
 &  =1+E(\tau_{x-u}).
$$
By law of total expectation for $x\leq1$
$$
  E(\tau_x)&=\int_0^1 E(\tau_x\mid U_1=u)du\\
  &=\int_0^x 1+E(\tau_{x-u})du  +\int_x^1 1+E(\tau_{x-u})du\\
  &=x-\int_x^0 E(\tau_s)ds+1-x\\
  &=\int_0^x E(\tau_s)ds+E(\tau_0),
$$
using $E(\tau_{x-u})=0$ for $u>x$, the substitution $s=x-u$ and that $E(\tau_0)=1$. Only $E(\tau_x)=e^{x}$ satisfies this integral equation in particular $E(\tau_1)=e$.
