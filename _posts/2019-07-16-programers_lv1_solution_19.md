---
layout: post
title: 프로그래머스 Lv1. 약수의 합
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 자연수 n을 입력받아 n의 약수를 모두 더한 값을 리턴하는 함수, solution을 완성해주세요.
> 
> 제한 조건
> * n은 0 이상 3000이하인 자연수입니다.

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

int solution(int n) {
    int i;
    int answer = 0;
    
    for(i = 1; i*i < n; i++){
        if(n%i == 0){
            answer += i;
            answer += n/i;
        }
    }
    if(i*i == n)
        answer += i;
    
    return answer;
}
```
