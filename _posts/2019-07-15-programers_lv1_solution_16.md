---
layout: post
title: 프로그래머스 Lv1. 수박수박수박수박수박수?
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 길이가 n이고, 수박수박수박수....와 같은 패턴을 유지하는 문자열을 리턴하는 함수, solution을 완성하세요. 예를들어 n이 4이면 수박수박을 리턴하고 3이라면 수박수를 리턴하면 됩니다.
> 
> 제한 조건
> * n은 길이 10,000이하인 자연수입니다.

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

string solution(int n) {
    string answer = "";
    
    for(int i = 0; i<n/2; i++){
        answer += "수박";
    }
    
    if(n%2 != 0)
        answer += "수";
    
    return answer;
}
```
