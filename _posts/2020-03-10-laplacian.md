---
layout: post
title: Laplacian Operator
date: 2020-03-11 02:00
summary: Laplacian 을 잊어먹기전에...
categories: math
---

## Laplacian Operator

$$
\Delta f=\frac{\partial^2 f}{\partial x^2} + \frac{\partial^2 f}{\partial y^2} \\
= \begin{bmatrix} \frac{\partial}{\partial x} & \frac{\partial}{\partial y} \end{bmatrix} \cdot \begin{bmatrix} \frac{\partial f}{\partial x} & \frac{\partial f}{\partial y} \end{bmatrix} \\ 
=\nabla \cdot \nabla f = div(\nabla f) \\
=trace(H(f))
$$

$f$는 scarlar-valued function, $\nabla \cdot$ 는 divergence operator 이다.
주어진 point 에서 볼록할수록 음의 방향의 값을, 오목할수록 양의 방향의 값을 가진다.

gradient의 divergence 로 해석하더라도 비슷한 느낌을 가진다. divergence 는 vector filed 에서 out-flow 의 정도를 나타내는데, gradient 가 확산되는 방향을 가질수록 (=오목할수록) 큰 값을 가진다고 해석할 수 있다.

## Heat Equation in DIP

Digital image processing 의 isotropic diffusion 에 대한 식은 아래와 같이 heat equation 의 형태이다 (상수 생략)

$$
\frac{\partial I(x, y, t)}{\partial t} = \frac{\partial^2 I}{\partial x^2} + \frac{\partial^2 I}{\partial y^2} = \Delta I
$$

시간의 흐름에 따라 (즉 iteration 이 반복됨에 따라), image 를 3차원 공간의 surface 로 표현했을 때 (x=width, y=height, z=intensity) z 방향으로 볼록한 부분을 조금씩 눌러주고 오목한 부분을 조금씩 올려주는 process 를 표현한다.(= Blurring)

위 식은 최종적으로 아래의 optimizing 을 수행하는 것이라고 생각할 수 있다. 
$$
minimize \int \left | \nabla I(x,y) \right | ^2 dxdy
$$

이 목적함수를 gradient descent 로 update 해가는 것이 Heat Equation 과 동일한 형태임을 증명해보자(여기서 gradient 란 spatial 한 $\nabla I$ 를 말하는게 아니라 pixel 값 하나하나에 대한 목적함수 $\sum \left | \nabla I(x,y) \right | ^2$의 gradient 를 말하는 것이다). 즉 우리는 iteration 을 반복하면서(temporal process as $t$ goes on) 주어진 이미지의 pixel 값들(=weights)이 어떻게 update 되어가야할 지가 궁금하다. Discrete 하게 보면, 이미지 pixel 값 하나하나를 변수로 보고 그 하나하나의 변수에 대해서 위 목적함수의 partial derivative 를 구해보면 Laplacian filter 에 해당하는 gradient 를 얻을 수 있다. Continuous 하게는 목적함수를 $I$ 에 대해서 (pixel 값에 대해서) 미분해보는 것이다. 이 방법은 뭔가 variational calculus 스러운데, 아래 유도가 rigorous 한지는 헷갈리지만, 항상 그렇듯이 대략 느낌적으로 어떻게 풀리는지 본다.

$$
\frac{\partial}{\partial I} \sum \left | \nabla I(x,y) \right | ^2 = 
\sum \frac{\partial}{\partial I} \left | \nabla I(x,y) \right | ^2 = \\
\sum \frac{\partial}{\partial I} ((\frac{\partial I}{\partial x})^2 + (\frac{\partial I}{\partial y})^2) = \\
\sum 2 \cdot \frac{\partial I}{\partial x} \cdot \frac{\partial}{\partial I} (\frac{\partial I}{\partial x})  + 2 \cdot \frac{\partial I}{\partial y} \cdot \frac{\partial}{\partial I} (\frac{\partial I}{\partial y}) = \\
2 \sum \frac{\partial^2 I}{\partial x^2} + \frac{\partial^2 I}{\partial y^2}
$$

즉 pixel point 에 대한 gradient (다시 한번, spatial 한 $\nabla I$를 말하는 것이 아니다) 값으로 해당 위치에서의 Laplacian 을 얻으면 된다는 것을 알 수 있다.

