---
layout: post
title: 프로그래머스 Lv1. 문자열 내림차순으로 배치하기
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-11
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 문자열 s에 나타나는 문자를 큰것부터 작은 순으로 정렬해 새로운 문자열을 리턴하는 함수, solution을 완성해주세요.
> ##### s는 영문 대소문자로만 구성되어 있으며, 대문자는 소문자보다 작은 것으로 간주합니다.
> 
> 제한 조건
> * str은 길이 1 이상인 문자열입니다.

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

using namespace std;

string solution(string s) {
    sort (s.begin(), s.end(), greater<char>());
    return s;
}
```
