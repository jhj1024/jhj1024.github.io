---
layout: post
title: 프로그래머스 Lv1. 핸드폰 번호 가리기
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 프로그래머스 모바일은 개인정보 보호를 위해 고지서를 보낼 때 고객들의 전화번호의 일부를 가립니다.
> ##### 전화번호가 문자열 phone_number로 주어졌을 때, 전화번호의 뒷 4자리를 제외한 나머지 숫자를 전부 *으로 가린 문자열을 리턴하는 함수, solution을 완성해주세요.
> 
> 제한 조건
> * s는 길이 4 이상, 20이하인 문자열입니다.

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

string solution(string phone_number) {    
    int len = phone_number.length();
    
    for(int i = 0; i < len-4; i++){
        phone_number[i] = '*';
    }

    return phone_number; 
}
    /*
    #include <regex>
    //문자열 길이가 짧기 때문에 정규표현식보다 for문이 더 빠르다
    if(len == 4)
        return phone_number;
    
    string sub = phone_number.substr(0, len-4);
    sub = regex_replace(sub, regex("[0-9]"), "*");
    
    return sub + phone_number.substr(len-4, len-1);
    */
```
