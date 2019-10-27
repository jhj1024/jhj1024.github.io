---
layout: post
title: 프로그래머스 Lv1. 정수 내림차순으로 배치하기
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 함수 solution은 정수 n을 매개변수로 입력받습니다. n의 각 자릿수를 큰것부터 작은 순으로 정렬한 새로운 정수를 리턴해주세요. 예를들어 n이 118372면 873211을 리턴하면 됩니다.
> 
> 제한 조건
> * n은 1이상 8000000000 이하인 자연수입니다.

<br>

- - -

### 풀이

<br>

- - -

### 코드
```cpp
#include <string>
#include <vector>
#include <algorithm>
#include <math.h>

using namespace std;

long long solution(long long n) {
    long long answer = 0;
    vector<int> tmp;
    
    while(n != 0){
        tmp.push_back(n%10);
        n = n/10;
    }
    
    sort(tmp.begin(), tmp.end());
    
    long long num;
    for(int i = 0; i < tmp.size(); i++){
        num = tmp[i] * pow(10, i);
        answer += num;
    }   
    
    return answer;
}
```
