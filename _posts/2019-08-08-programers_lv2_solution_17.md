---
layout: post
title: 프로그래머스 Lv2. 행렬의 곱셈
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 2차원 행렬 arr1과 arr2를 입력받아, arr1에 arr2를 곱한 결과를 반환하는 함수, solution을 완성해주세요.
> 
> 제한 조건
> * 행렬 arr1, arr2의 행과 열의 길이는 2 이상 100 이하입니다.
> * 행렬 arr1, arr2의 원소는 -10 이상 20 이하인 자연수입니다.
> * 곱할 수 있는 배열만 주어집니다.

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

vector<vector<int>> solution(vector<vector<int>> arr1, vector<vector<int>> arr2) {
    vector<vector<int>> answer;
    answer.assign(arr1.size(), vector<int>(arr2[0].size(), 0));
    
    for(int i = 0; i < arr1.size(); i++){
        for(int j = 0; j < arr2[0].size(); j++){
            for(int k = 0; k < arr1[0].size(); k++){
                answer[i][j] += arr1[i][k]*arr2[k][j];
            }
        }
    }
    
    return answer;
}
```
