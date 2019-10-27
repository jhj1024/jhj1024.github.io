---
layout: post
title: 프로그래머스 Lv1. 소수 찾기
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 1부터 입력받은 숫자 n 사이에 있는 소수의 개수를 반환하는 함수, solution을 만들어 보세요.
> ##### 소수는 1과 자기 자신으로만 나누어지는 수를 의미합니다.
> ##### (1은 소수가 아닙니다.)
> 
> 제한 조건
> * n은 2이상 1000000이하의 자연수입니다.

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

int solution(int n) {
    vector<bool> vec(n+1); //default=false
    int answer = 0;
    
    for(int i = 2; i <= n; i++){
        if(vec[i] == true)
            continue;
        
        answer++;
        
        for(int j = i; j <= n; j=j+i){
            vec[j] = true;
        }
    }
    
    return answer;
}
```
