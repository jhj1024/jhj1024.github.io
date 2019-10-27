---
layout: post
title: 프로그래머스 Lv1. 문자열 내 마음대로 정렬하기
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-11
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 문자열로 구성된 리스트 strings와, 정수 n이 주어졌을 때, 각 문자열의 인덱스 n번째 글자를 기준으로 오름차순 정렬하려 합니다. 예를 들어 strings가 [sun, bed, car]이고 n이 1이면 각 단어의 인덱스 1의 문자 u, e, a로 strings를 정렬합니다.
> 
> 제한 조건
> * strings는 길이 1 이상, 50이하인 배열입니다.
> * strings의 원소는 소문자 알파벳으로 이루어져 있습니다.
> * strings의 원소는 길이 1 이상, 100이하인 문자열입니다.
> * 모든 strings의 원소의 길이는 n보다 큽니다.
> * 인덱스 1의 문자가 같은 문자열이 여럿 일 경우, 사전순으로 앞선 문자열이 앞쪽에 위치합니다.

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

vector<string> solution(vector<string> strings, int n) {
    vector<string> answer;    
    vector<pair<char, int>> alpha;
    
    sort(strings.begin(), strings.end());
    
    for(int i = 0; i < strings.size(); i++)
    {
        string s = strings[i];
        alpha.push_back(make_pair(s[n], i));
    }
    
    sort(alpha.begin(), alpha.end()); //string 사전 순, 그다음 int 오름차순으로 정렬
    
    vector<pair<char, int>>::iterator iter;
    for(iter = alpha.begin(); iter != alpha.end(); iter++)
    {
        answer.push_back(strings[iter->second]);
    }
    
        
    return answer;
}
```
