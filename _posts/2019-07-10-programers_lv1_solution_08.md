---
layout: post
title: 프로그래머스 Lv1. 나누어 떨어지는 숫자 배열
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-10
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### array의 각 element 중 divisor로 나누어 떨어지는 값을 오름차순으로 정렬한 배열을 반환하는 함수, solution을 작성해주세요.
> ##### divisor로 나누어 떨어지는 element가 하나도 없다면 배열에 -1을 담아 반환하세요.
> 
> 제한 조건
> * arr은 자연수를 담은 배열입니다.
> * 정수 i, j에 대해 i ≠ j 이면 arr[i] ≠ arr[j] 입니다.
> * divisor는 자연수입니다.
> * array는 길이 1 이상인 배열입니다.

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

vector<int> solution(vector<int> arr, int divisor) {
    vector<int> answer;
    
    sort(arr.begin(), arr.end());
    
    for(int i = 0; i < arr.size(); i++)
    {
        if(arr[i]%divisor == 0){
            answer.push_back(arr[i]);
        }
    }
    
    if(answer.size() == 0){
        answer.push_back(-1);
    }
        
    return answer;
}
```
