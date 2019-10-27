---
layout: post
title: 프로그래머스 Lv2. 주식가격
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 초 단위로 기록된 주식가격이 담긴 배열 prices가 매개변수로 주어질 때, 가격이 떨어지지 않은 기간은 몇 초인지를 return 하도록 solution 함수를 완성하세요.
> 
> 제한 조건
> * prices의 각 가격은 1 이상 10,000 이하인 자연수입니다.
> * prices의 길이는 2 이상 100,000 이하입니다.

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

vector<int> solution(vector<int> prices) {
    vector<int> answer(prices.size());
    
    for(int i = 0; i < prices.size(); i++){
        for(int j = i+1; j < prices.size(); j++){
            answer[i]++;
            if(prices[i] > prices[j])
                break;
        }
    }
    return answer;
}
```
