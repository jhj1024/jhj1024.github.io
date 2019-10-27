---
layout: post
title: 프로그래머스 Lv1. 평균 구하기
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 정수를 담고 있는 배열 arr의 평균값을 return하는 함수, solution을 완성해보세요.
> 
> 제한 조건
> * arr은 길이 1 이상, 100 이하인 배열입니다.
> * arr의 원소는 -10,000 이상 10,000 이하인 정수입니다.

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

double solution(vector<int> arr) {
    double answer = 0;
    
    vector<int>::iterator it;
    double sum = 0;
    for(it = arr.begin(); it != arr.end(); ++it){
        sum += *it;
    }
    
    answer = sum/arr.size();
    
    return answer;
}
```
