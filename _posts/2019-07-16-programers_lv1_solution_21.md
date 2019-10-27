---
layout: post
title: 프로그래머스 Lv1. 자릿수 더하기
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 자연수 N이 주어지면, N의 각 자릿수의 합을 구해서 return 하는 solution 함수를 만들어 주세요.
> ##### 예를들어 N = 123이면 1 + 2 + 3 = 6을 return 하면 됩니다.
> 
> 제한 조건
> * N의 범위 : 100,000,000 이하의 자연수

<br>

- - -

### 풀이

<br>

- - -

### 코드
```cpp
#include <iostream>

using namespace std;
int solution(int n)
{
    int answer = 0;

    while(n != 0){
        answer += n%10;
        n = int(n/10);
    }

    return answer;
}
```
