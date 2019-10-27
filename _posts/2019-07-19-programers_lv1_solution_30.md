---
layout: post
title: 프로그래머스 Lv1. 하샤드 수
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 양의 정수 x가 하샤드 수이려면 x의 자릿수의 합으로 x가 나누어져야 합니다. 예를 들어 18의 자릿수 합은 1+8=9이고, 18은 9로 나누어 떨어지므로 18은 하샤드 수입니다. 자연수 x를 입력받아 x가 하샤드 수인지 아닌지 검사하는 함수, solution을 완성해주세요.
> 
> 제한 조건
> * x는 1 이상, 10000 이하인 정수입니다.

<br>

- - -

### 풀이

<br>

- - -

### 코드
```cpp
#include <string>
#include <vector>

using namespace std;

bool solution(int x) {
    bool answer = true;
    
    int n = x;
    int sum = 0;
    
    while(x != 0){
        sum += x%10;
        x = x/10;
    }

    answer = (n%sum == 0) ? true : false;
    
    return answer;
}
```
