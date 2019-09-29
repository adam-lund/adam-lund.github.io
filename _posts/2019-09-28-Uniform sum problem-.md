---
layout: post
title: Stopping time
categories:
---

*Suppose you  independently  sample uniformly from the unit interval and then sum these samples. On average how many times would you have to do this before the sum is  bigger than one?*

This question --or a variation of it-- is apparently by now a well known problem from a 1958 Putnam examination. I was unaware of that when I first encountered it as part of  an (closed book) entrance test I had to sit to get access to a round of interviews with a (quantitative?) company a couple of years ago. Also I couldn't find a way to solve it back then since my solution relied on integrating the tail of the distribution of the $n$-fold convolution of iid uniform(0,1) variables to obtain the desired expectation.  Off the top of my head I didn't (and still don't) know this distribution though it does have a closed form expression (originally derived by Laplace I think). An alternative and related solution strategy, that requires that you know the volume under the $n$-dimensional simplex  (it is $1/n!$ by the way), makes the problem fairly easy to solve as well. I'd expect very few people to know this volume or integral so this solution is also a bit unsatisfactory.    

A few weeks ago the question resurfaced for some reason and I started to think  about how you might go about solving it without knowing the convolution result, the $n$-dimensional integral or any other piece of niche knowledge for that matter.
Of course, if your aim is to land a quantitative job, this is not the right approach to take to questions like this. Instead what you should do is: i) look up as many questions and their answers in books on questions from quantitative job interviews as you can, ii) memorize  these questions and answers meticulously  and iii) when asked a question that you remember the solution to, repeat the solution in a way that makes it seem like you are deriving the answer and not regurgitating it and --and this is important-- at the same time makes your interviewer feel superior.

i)-iii) is *the* industry wide approach to interviewing and apparently results in an interview dynamic that is still second to none when it comes to revealing "how a job candidate thinks". In taking the exact opposite approach to that of i)-iii) I came up with a self contained and suspiciously succinct answer that I haven't seen anywhere else and therefore thought I'd give here.

###### Answer

Let $\\{U_i: i\in \mathbb{N}\\}$ be iid uniform on $[0,1 ]$ and consider $ S_n=\sum_i^nU_i$. Define $ \tau_x=\min_n\\{ n :S_n>x\\} $ for $x\leq 1$ with the convention $\tau_x=0$ when $x\leq0$.
Clearly $S_{\tau_x}=S_{\tau_x+1 -1}$ so  $\tau_x+1$ is the smallest $n\in \mathbb{N}$ such that $S_{n-1}>x$. Using this fact and the independence we have   for $x\leq1$

$$\begin{alignat*}{4}
  E(\tau_x\mid U_1=u)
&  =  E\Bigl(\min_{n }\Bigl\{n:\sum_{i=1}^{n-1}U_{i+1} >x-u\Bigr\}\mid U_1=u\Bigr)\\
 & =   E(\min_{n }\{n  :S_{n-1} >x-u\})\\
 &  =1+E(\tau_{x-u}).
\end{alignat*}$$

By the law of total expectation for $x\in (0,1)$

$$\begin{align}  E(\tau_x)&=\int_0^1 E(\tau_x\mid U_1=u)du\\
  &=\int_0^x 1+E(\tau_{x-u})du  +\int_x^1 1+E(\tau_{x-u})du\\
  &=x-\int_x^0 E(\tau_s)ds+1-x\\
  &=\int_0^x E(\tau_s)ds+E(\tau_0),
\end{align}$$

using $E(\tau_{x-u})=0$ for $u>x$, the substitution $s=x-u$ and that $E(\tau_0)=1$.
 Only $x \mapsto E(\tau_x)=e^{x}$ satisfies this integral equation in particular $E(\tau_1)=e$.

Note that for $x>1$ we cannot split up the integral to get the integral equation.
So in this case we don't obtain the function $e^x$ as the solution. So what do we get for $x>1$? 

Happy birthday!
