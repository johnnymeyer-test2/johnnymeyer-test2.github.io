---
layout: post
title: "Differentiation"
date: 2016-01-26
---

The derivative $f'(x)$ of a function $f(x)$ is the rate of change of the
function. If we have $y=f(x)$ then we can say the derivative is
$\frac{dy}{dx}$. Another notation for the derivative is $y'$.

If \\[f(x)=x^n\\]
is a polynomial term then we have a rule for finding the derivative, namely
\\[f'(x)=nx^{n-1}.\\]

# The Gamma Function

Define the gamma function $\Gamma(x)$ by
\\[\Gamma(x) := \int_0^\infty u^{x-1} e^{-u} dx, \quad x>0.\\]
We would like to compute $\Gamma(1/2).$ Making the substitution
$u=t^2$ we get
\\[\Gamma(1/2) = \int_0^\infty u^{-1/2} e^{-u} dx
= 2 \int_0^\infty e^{-t^2} dt
= \int_{-\infty}^\infty e^{-t^2} dt.\\]
We could calculate this by noting that
$\frac{1}{\sqrt{2\pi\sigma^2}} e^{-\frac{t^2}{2\sigma^2}}$
is the density of a $N(0,\sigma^2)$ random variable. By setting
$\sigma^2 = 1/2$ and noting that such a density integrates to one over the whole
real line we get
\\[\Gamma(1/2)
= \sqrt{\pi} \frac{1}{\sqrt{\pi}} \int_{-\infty}^\infty e^{-t^2} dt
= \sqrt{\pi}.\\]
We could also show this by making use of double integrals.
Using Fubini's theorem we have
\\[[\Gamma(1/2)]^2 = \left(\int_{-\infty}^\infty e^{-t^2} dt\right)^2
= \left(\int_{-\infty}^\infty e^{-t^2} dt\right)\left(\int_{-\infty}^\infty e^{-s^2} ds\right)
= \int_{\mathbb{R}} \int_{\mathbb{R}} e^{-(t^2+s^2)} \, dt \, ds.\\]
Changing to polar coordinates this becomes
\\[[\Gamma(1/2)]^2 = \int_0^{2\pi} \int_0^\infty re^{-r^2} \, dr \, d\theta = \pi.\\]
Upon taking square roots we obtain the same result, namely
\\[\Gamma(1/2) = \sqrt\pi.\\]

# An Interesting Infinite Sum

We evaluate the series $\sum_{k=1}^\infty kx^k$. The series
is absolutely convergent (use the ratio test) for $|x| < 1$, so we
can rearrange it and write is as
\begin{align\*}
x          + x^2 + x^3 + x^4 + x^5 + &\dots  \\\
\phantom x + x^2 + x^3 + x^4 + x^5 + &\dots  \\\
      \phantom x + x^3 + x^4 + x^5 + &\dots  \\\
            \phantom x + x^4 + x^5 + &\dots  \\\
                  \phantom x + x^5 + &\dots  \\\
                       \phantom x + &\dots   \\\
            \phantom + &\ddots
\end{align\*}
Each line in the above is the sum of an infinite geometric
progression minus a finite number of terms. We get
\\[
\sum_{k=1}^\infty kx^k =
\sum_{j=0}^\infty
\left( \sum_{k=0}^\infty x^k - \sum_{k=0}^j x^k \right)
\\]
where $j=0$ corresponds to the first line above,
$j=1$ the second line, and so on. Using standard formulae
for geometric progressions we get
\begin{align\*}
\sum_{k=1}^\infty kx^k
&= \sum_{j=0}^\infty
\left( \frac{1}{1-x} - \frac{1-x^{j+1}}{1-x} \right) \\
&= \sum_{j=0}^\infty
\frac{x^{j+1}}{1-x} \\
&= \frac{x}{1-x} \sum_{j=0}^\infty x^j \\
&= \frac{x}{1-x} \frac{1}{1-x} \\
&= \frac{x}{(1-x)^2}
\end{align\*}
which we note is only valid for $|x| < 1$
(the radius of convergence of an infinite geometric series).


<script type="text/x-mathjax-config">
    MathJax.Hub.Config({
        tex2jax: {
            inlineMath: [['$','$'], ['\\(','\\)']],
        }
    });
</script>
<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>
<!-- <script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML"></script> -->
