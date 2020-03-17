---
layout: post
title: Tensorflow Apple vs Banana
date: 2020-03-17 17:40
summary: 개념 정리
categories: tensorflow
---

tf.name_scope(ops, Variable) vs tf.variable_scope(ops, get_variable, Variable) 

tf.global_variable vs tf.local_variable (check point 에 저장안됨, per process, counter 같은 용도?)

tf.scan(aggregation, context tensor 가 따라다닌다) vs tf.map_fn(단순 iteration)