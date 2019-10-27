---
layout: post
title: 프로그래머스 Lv2. 다리를 지나는 트럭
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 트럭 여러 대가 강을 가로지르는 일 차선 다리를 정해진 순으로 건너려 합니다. 모든 트럭이 다리를 건너려면 최소 몇 초가 걸리는지 알아내야 합니다. 트럭은 1초에 1만큼 움직이며, 다리 길이는 bridge_length이고 다리는 무게 weight까지 견딥니다.
> ##### 트럭이 다리에 완전히 오르지 않은 경우, 이 트럭의 무게는 고려하지 않습니다.

> ##### 예를 들어, 길이가 2이고 10kg 무게를 견디는 다리가 있습니다. 무게가 [7, 4, 5, 6]kg인 트럭이 순서대로 최단 시간 안에 다리를 건너려면 다음과 같이 건너야 합니다.

> ##### 따라서, 모든 트럭이 다리를 지나려면 최소 8초가 걸립니다.

> ##### solution 함수의 매개변수로 다리 길이 bridgelength, 다리가 견딜 수 있는 무게 weight, 트럭별 무게 truckweights가 주어집니다. 이때 모든 트럭이 다리를 건너려면 최소 몇 초가 걸리는지 return 하도록 solution 함수를 완성하세요.
> 
> 제한 조건
> * bridge_length는 1 이상 10,000 이하입니다.
> * weight는 1 이상 10,000 이하입니다.
> * truck_weights의 길이는 1 이상 10,000 이하입니다.
> * 모든 트럭의 무게는 1 이상 weight 이하입니다.

<br>

- - -

### 풀이

<br>

- - -

### 코드
```cpp
#include <string>
#include <vector>
#include <queue>

using namespace std;

int solution(int bridge_length, int weight, vector<int> truck_weights) {
    int ct = 0; //현재 시간
    int cw = 0; //다리 위 트럭 무게 합
    int truck_weight, time;
    
    queue<int> tw; //다리 위 트럭의 무게 
    queue<int> et; //트럭이 다리를 지나간 시점
        
    do{       
        ct++;
        if(!et.empty() && et.front() == ct){
            cw -=tw.front();
            tw.pop();
            et.pop();
        }    
        
        if(truck_weights.size() > 0){
            truck_weight = truck_weights[0];
            
            if(cw + truck_weight <= weight){
                tw.push(truck_weight); //트럭의 무게 저장            
                et.push(ct+bridge_length); //다리를 지나는 시간 저장

                cw += truck_weight; //현재 다리 위 트럭 무게에 더함
                truck_weights.erase(truck_weights.begin()); //벡터에서 제거
            }

        }        
    }while(!et.empty());
    
    return ct;
}
```
