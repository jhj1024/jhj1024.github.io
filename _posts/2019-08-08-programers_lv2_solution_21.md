---
layout: post
title: 프로그래머스 Lv2. 위장
categories: [solution]
description: "알고리즘 풀이"
date: 2019-08-08
tags: [알고리즘]
share: true
---
위장
===

```cpp
#include <string>
#include <vector>
#include <unordered_map>

using namespace std;

int solution(vector<vector<string>> clothes) {    
    int answer = 1; //곱셈을 하기 때문에 초기값을 1로 선언
    unordered_map<string, int> hash;
        
    for(auto iter : clothes){
        hash[iter[1]]++; //해당 의상 종류에 대한 가지수 증가 
    }
    
    for(auto iter : hash){
        answer *= (iter.second)+1; //아무것도 선택하지 않는 경우까지 포함
    }
    
    return answer-1; //아무것도 입지 않는 경우 제외
}
```