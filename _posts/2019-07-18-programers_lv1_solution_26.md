---
layout: post
title: 프로그래머스 Lv1. 짝수와 홀수
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 정수 num이 짝수일 경우 Even을 반환하고 홀수인 경우 Odd를 반환하는 함수, solution을 완성해주세요.
> 
> 제한 조건
> * num은 int 범위의 정수입니다.
> * 0은 짝수입니다.

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

string solution(int num) {
    string answer = "";
    
    if(num %2 == 0){
        answer = "Even";
    }
    
    else{
        answer = "Odd";
    }
    return answer;
}
```
