---
layout: post
title: 프로그래머스 Lv2. 가장 큰 수
categories: [solution]
description: "알고리즘 풀이"
date: 2019-08-08
tags: [알고리즘]
share: true
---
가장 큰 수
===
```cpp
#include <string>
#include <vector>
#include <algorithm>

using namespace std;

bool order(int a, int b){
    string s1 = to_string(a);
    string s2 = to_string(b);
    
    return s1+s2 > s2+s1 ? true : false;
}
string solution(vector<int> numbers) {
    string answer = "";

    sort(numbers.begin(), numbers.end(), order);
    
    for(auto i : numbers){
        answer += to_string(i);
    }
    
    return answer[0] == '0' ? "0" : answer;
}
```