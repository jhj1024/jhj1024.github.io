---
layout: post
title: 프로그래머스 Lv2. 최댓값과 최솟값
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 문자열 s에는 공백으로 구분된 숫자들이 저장되어 있습니다. str에 나타나는 숫자 중 최소값과 최대값을 찾아 이를 (최소값) (최대값)형태의 문자열을 반환하는 함수, solution을 완성하세요.
> ##### 예를들어 s가 1 2 3 4라면 1 4를 리턴하고, -1 -2 -3 -4라면 -4 -1을 리턴하면 됩니다.
> 
> 제한 조건
> * s에는 둘 이상의 정수가 공백으로 구분되어 있습니다.

<br>

- - -

### 풀이

<br>

- - -

### 코드
```cpp
#include <string>
#include <vector>
#include <sstream>
#include <cstring>
#include <algorithm>

using namespace std;

string solution(string s) {    
    string answer = "";
    vector<int> nums;
    
    stringstream ss(s);
    string word;
    
    while(ss >> word){
        nums.push_back(stoi(word));
    }
    
    sort(nums.begin(), nums.end());
    answer = to_string(nums[0]) + " " + to_string(nums[nums.size()-1]);
    return answer;
}
```
