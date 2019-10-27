---
layout: post
title: 프로그래머스 Lv2. 쇠막대기
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 여러 개의 쇠막대기를 레이저로 절단하려고 합니다. 효율적인 작업을 위해서 쇠막대기를 아래에서 위로 겹쳐 놓고, 레이저를 위에서 수직으로 발사하여 쇠막대기들을 자릅니다. 쇠막대기와 레이저의 배치는 다음 조건을 만족합니다.
> 
> ##### 아래 그림은 위 조건을 만족하는 예를 보여줍니다. 수평으로 그려진 굵은 실선은 쇠막대기이고, 점은 레이저의 위치, 수직으로 그려진 점선 화살표는 레이저의 발사 방향입니다.
> 
> ##### 이러한 레이저와 쇠막대기의 배치는 다음과 같이 괄호를 이용하여 왼쪽부터 순서대로 표현할 수 있습니다.
> 
> ##### 위 예의 괄호 표현은 그림 위에 주어져 있습니다.
> ##### 쇠막대기는 레이저에 의해 몇 개의 조각으로 잘리는데, 위 예에서 가장 위에 있는 두 개의 쇠막대기는 각각 3개와 2개의 조각으로 잘리고, 이와 같은 방식으로 주어진 쇠막대기들은 총 17개의 조각으로 잘립니다.
>
> ##### 쇠막대기와 레이저의 배치를 표현한 문자열 arrangement가 매개변수로 주어질 때, 잘린 쇠막대기 조각의 총 개수를 return 하도록 solution 함수를 작성해주세요.
> 
> 제한 조건
> * arrangement의 길이는 최대 100,000입니다.
> * arrangement의 여는 괄호와 닫는 괄호는 항상 쌍을 이룹니다.

<br>

- - -

### 풀이

<br>

- - -

### 코드
```cpp
#include <string>
#include <vector>
#include <stack>

using namespace std;

int solution(string arrangement) {
    stack<char> st;
    int answer = 0;
    
    for(int i = 0; i < arrangement.size(); i++){
        if(arrangement[i] == '(')
            st.push(arrangement[i]); //여는 괄호이면 스택에 추가
        else{
            st.pop();
            
            if(arrangement[i-1] == '(') //레이저이면 저장한 '(' 갯수만큼 더함
                answer += st.size();
            else //막대의 끝이면 하나 추가
                answer++;            
        }            
    }
    return answer;
}
```
