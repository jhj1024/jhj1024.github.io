---
layout: post
title: 프로그래머스 Lv1. 문자열을 정수로 바꾸기
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 문자열 s를 숫자로 변환한 결과를 반환하는 함수, solution을 완성하세요.
> 
> 제한 조건
> * s의 길이는 1 이상 5이하입니다.
> * s의 맨앞에는 부호(+, -)가 올 수 있습니다.
> * s는 부호와 숫자로만 이루어져있습니다.
> * s는 0으로 시작하지 않습니다.

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

int solution(string s) {
    int answer;
    
    if(s[0] == '-'){
        answer = stoi(s.substr(1,s.size()));
        answer = 0-answer;
    }
    
    else{
        answer = stoi(s);
    }
    return answer;
}
```
