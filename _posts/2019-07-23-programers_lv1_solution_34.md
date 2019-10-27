---
layout: post
title: 프로그래머스 Lv1. 직사각형 별찍기
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 이 문제에는 표준 입력으로 두 개의 정수 n과 m이 주어집니다.
> ##### 별(*) 문자를 이용해 가로의 길이가 n, 세로의 길이가 m인 직사각형 형태를 출력해보세요.
> 
> 제한 조건
> * n과 m은 각각 1000 이하인 자연수입니다.

<br>

- - -

### 풀이

<br>

- - -

### 코드
```cpp
#include <iostream>

using namespace std;

int main(void) {
    int a, b;
    cin >> a >> b;
    
    for(int i = 0; i < b; i++){
        for(int j = 0; j < a; j++){
             cout << "*";
        }
        cout << endl;
    }
    
    return 0;
}
```
