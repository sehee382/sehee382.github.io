---
layout: post
title: Laplacian Operator
date: 2020-03-11 02:00
summary: Pixyll is available to you under the MIT license.
categories: math
---

## Laplacian Operator

$$
\Delta F=\frac{\partial^2 F}{\partial x^2} + \frac{\partial^2 F}{\partial y^2} \\
= \begin{bmatrix} \frac{\partial}{\partial x} & \frac{\partial}{\partial y} \end{bmatrix} \cdot \begin{bmatrix} \frac{\partial F}{\partial x} & \frac{\partial F}{\partial y} \end{bmatrix} \\ 
=\nabla \cdot \nabla F \\
= div(\nabla F)
$$

$F$는 Scarlar-Valued function, $\nabla \cdot$ 는 divergence operator 이다.
주어진 point 에서 볼록할 수록 음의 방향의 값을, 오목할 수록 양의 방향의 값을 가진다.

gradient의 divergence 로 해석하더라도 비슷한 느낌을 가진다. divergence 는 vector filed 에서 out-flow 의 정도를 나타내는데, gradient 가 확산되는 방향을 가질수록 (=오목할수록) 큰 값을 가진다고 해석할 수 있다.

## Heat Equation 

Digital Image Processing 의 Isotropic Diffusion 에 대한 식은 아래와 같이 Heat Equation 의 형태이다 (상수 생략)

$$
\frac{\partial I(x, y, t)}{\partial t} = \frac{\partial^2 F}{\partial x^2} + \frac{\partial^2 F}{\partial y^2} = \Delta F
$$

즉 시간의 흐름에 따라 (즉 iteration 이 반복됨에 따라), 오른쪽 항은 image 를 3차원 형태로 표현할때 (x=width, y=height, z=intensity) z 방향으로 볼록한 부분을 눌러주고 오목한 부분을 올려주는 것을 표현한다.(= Blurring)

위 식은 최종적으로 아래의 optimizing 을 수행하는 것이라고 생각할 수 있다.

$$
minimize \int \left | \nabla I(x,y) \right | ^2 dxdy
$$
