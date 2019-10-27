---
layout: post
title: 프로그래머스 Lv2. 더 맵게
categories: [solution]
description: "알고리즘 풀이"
date: 2019-08-08
tags: [알고리즘]
share: true
---
더 맵게
===

```cpp
#include <string>
#include <vector>
#include <queue>

using namespace std;

int solution(vector<int> scoville, int K) {
    int answer = 0;
    priority_queue<int, vector<int>, greater<int>> heap;
    
    for(auto i : scoville)
        heap.push(i);
    
    while(1){
        int min1 = heap.top(); heap.pop();
        if(min1 >= K) break;
        if(heap.empty()){
            answer = -1;
            break;
        }
        int min2 = heap.top(); heap.pop();
        
        heap.push(min1+ (min2*2));
        answer++;
    }
    return answer;
}
```