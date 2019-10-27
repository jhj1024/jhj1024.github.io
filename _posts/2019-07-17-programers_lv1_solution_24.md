---
layout: post
title: 프로그래머스 Lv1. 정수 제곱근 판별
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 임의의 정수 n에 대해, n이 어떤 정수 x의 제곱인지 아닌지 판단하려 합니다.
> ##### n이 정수 x의 제곱이라면 x+1의 제곱을 리턴하고, n이 정수 x의 제곱이 아니라면 -1을 리턴하는 함수를 완성하세요.
> 
> 제한 조건
> * n은 1이상, 50000000000000 이하인 정수입니다.

<br>

- - -

### 풀이

<br>

- - -

### 코드
```cpp
#include <string>
#include <vector>
#include <math.h>

using namespace std;

long long solution(long long n) {
    long long answer = 0;
    
    long long sr = sqrt(n); //제곱근
    if(sr*sr == n){
        answer = pow(sr+1,2);
    }
    
    else
        answer = -1;
    
    return answer;
}
```
