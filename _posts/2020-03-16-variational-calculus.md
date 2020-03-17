---
layout: post
title: Stochastic Process
date: 2020-03-14 17:10
summary: 개념 정리
categories: math
---

시작은...
$$
\delta J=\int _{a}^{b}{\frac {\delta J}{\delta f(x)}}{\delta f(x)}\,dx\,.
$$

정의....
$$
{\begin{aligned}\int {\frac {\delta F}{\delta \rho }}(x)\phi (x)\;dx;=\lim _{\varepsilon \to 0}{\frac {F[\rho +\varepsilon \phi ]-F[\rho ]}{\varepsilon }}\\;=\left[{\frac {d}{d\epsilon }}F[\rho +\epsilon \phi ]\right]_{\epsilon =0},\end{aligned}}
$$

열심히 풀어보면 이렇게....
$$
{\frac {\delta F}{\delta \rho ({\boldsymbol {r}})}}={\frac {\partial f}{\partial \rho }}-\nabla \cdot {\frac {\partial f}{\partial \nabla \rho }}
$$

