---
layout: post
title: 프로그래머스 Lv1. 자연수 뒤집어 배열로 만들기
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 자연수 n을 뒤집어 각 자리 숫자를 원소로 가지는 배열 형태로 리턴해주세요. 예를들어 n이 12345이면 [5,4,3,2,1]을 리턴합니다.
> 
> 제한 조건
> * n은 10,000,000,000이하인 자연수입니다.

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

vector<int> solution(long long n) {
    vector<int> answer;
    
    while(n != 0){
        answer.push_back(n%10);
        n = n/10;
    }
    
    return answer;
}
```
