---
layout: post
title: 프로그래머스 Lv1. 서울에서 김서방 찾기
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### String형 배열 seoul의 element중 Kim의 위치 x를 찾아, 김서방은 x에 있다는 String을 반환하는 함수, solution을 완성하세요. seoul에 Kim은 오직 한 번만 나타나며 잘못된 값이 입력되는 경우는 없습니다.
> 
> 제한 조건
> * seoul은 길이 1 이상, 1000 이하인 배열입니다.
> * seoul의 원소는 길이 1 이상, 20 이하인 문자열입니다.
> * Kim은 반드시 seoul 안에 포함되어 있습니다.

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

string solution(vector<string> seoul) {
    vector<string>::iterator it = find(seoul.begin(), seoul.end(), "Kim");
    int index = distance(seoul.begin(), it); 
    
    string answer = "김서방은 " + to_string(index) + "에 있다";
        
    return answer;
}
```
