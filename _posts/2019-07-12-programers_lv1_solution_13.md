---
layout: post
title: 프로그래머스 Lv1. 문자열 다루기 기본
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-12
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 문자열 s의 길이가 4 혹은 6이고, 숫자로만 구성돼있는지 확인해주는 함수, solution을 완성하세요. 
> ##### 예를 들어 s가 a234이면 False를 리턴하고 1234라면 True를 리턴하면 됩니다.
> 
> 제한 조건
> * s는 길이 1 이상, 길이 8 이하인 문자열입니다.

<br>

- - -

### 풀이

<br>

- - -

### 코드
```cpp
#include <string>
#include <vector>
#include <regex>

using namespace std;

bool solution(string s) {
    bool answer = false;
    
    regex num("[0-9]+");
    
    if(s.length() == 4 || s.length() == 6){
        if(regex_match(s, num)){
            answer = true;
        }
    }
       
    return answer;
}
```
