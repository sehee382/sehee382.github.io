---
layout: post
title: Stochastic Process
date: 2020-03-14 17:10
summary: 개념 정리
categories: math
---

**1.** 확률변수의 집합 ${X_t \vert t∈[0,∞)}$ 을 **연속적 확률과정**이라고 한다.

**2.** 확률변수의 수열 ${X_n \vert n = 0,1,2,\cdots}$ 을 **이산적 확률과정**이라고 한다.

Gaussian Process(GP), Markov Random Field(MRF), Conditional Random Field(CRF) 등에 반복적으로 등장한다. 시간 t 에 따라 (indexed by time domain) 주어지는 확률 변수의 나열을 생각하면 된다.

MRF, CRF 에 나오는 random field 란 개념은 1-dimension 의 time indexing 을 spatial 한 2D indexing 으로 각 RV node 들을 addressing 한다고 생각하면 된다.
