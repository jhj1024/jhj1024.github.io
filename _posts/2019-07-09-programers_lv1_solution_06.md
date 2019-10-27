---
layout: post
title: 프로그래머스 Lv1. 가운데 글자 가져오기
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 단어 s의 가운데 글자를 반환하는 함수, solution을 만들어 보세요. 단어의 길이가 짝수라면 가운데 두글자를 반환하면 됩니다.
> 
> 제한 조건
> * s는 길이가 1 이상, 100이하인 스트링입니다.

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

string solution(string s) {
    string answer = "";
    int len = s.length();
        
    if(len%2 == 0){
        answer = s.substr(len/2-1,2);
    }
    else{
        answer = s.substr(len/2,1);
    }
        
    return answer;
}
```
