---
layout: post
title: 프로그래머스 Lv1. 최대공약수와 최소공배수
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 두 수를 입력받아 두 수의 최대공약수와 최소공배수를 반환하는 함수, solution을 완성해 보세요. 배열의 맨 앞에 최대공약수, 그다음 최소공배수를 넣어 반환하면 됩니다. 예를 들어 두 수 3, 12의 최대공약수는 3, 최소공배수는 12이므로 solution(3, 12)는 [3, 12]를 반환해야 합니다.
> 
> 제한 조건
> * 두 수는 1이상 1000000이하의 자연수입니다.

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
//유클리드 호제법
vector<int> solution(int n, int m) {
    vector<int> answer;
    
    int a = (n > m) ? n : m;
    int b = (n > m) ? m : n;
    
    int r;
    while(b){
        r = a%b;
        a = b;
        b = r;
    }
    
    answer.push_back(a); //최대공약수
    answer.push_back(n*m/a); //최소공배수
        
    return answer;
}
```
