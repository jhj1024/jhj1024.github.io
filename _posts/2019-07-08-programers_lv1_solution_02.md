---
layout: post
title: 프로그래머스 Lv1. 모의고사
categories: [solution]
description: "일정한 패턴으로 답을 찍는 수포자 1,2,3 중 가장 많은 문제를 맞힌 사람 구하기"
date: 2019-07-08
tags: [vector, 최댓값구하기]
share: true
---

### 문제 설명
> ##### 수포자는 수학을 포기한 사람의 준말입니다. 수포자 삼인방은 모의고사에 수학 문제를 전부 찍으려 합니다. 수포자는 1번 문제부터 마지막 문제까지 다음과 같이 찍습니다.
> ##### 1번 수포자가 찍는 방식: 1, 2, 3, 4, 5, . . .
> ##### 2번 수포자가 찍는 방식: 2, 1, 2, 3, 2, 4, 2, 5, . . .
> ##### 3번 수포자가 찍는 방식: 3, 3, 1, 1, 2, 2, 4, 4, 5, 5, . . .
> ##### 1번 문제부터 마지막 문제까지의 정답이 순서대로 들은 배열 answers가 주어졌을 때, 가장 많은 문제를 맞힌 사람이 누구인지 배열에 담아 return 하도록 solution 함수를 작성해주세요.
>
> 제한 조건
> * 시험은 최대 10,000 문제로 구성되어있습니다.   
> * 문제의 정답은 1, 2, 3, 4, 5중 하나입니다.   
> * 가장 높은 점수를 받은 사람이 여럿일 경우, return하는 값을 오름차순 정렬해주세요.   

<br>

- - -

### 풀이
수포자의 패턴(v)의 길이가 n일 때, i번째 문제에 대한 답으로 v[i%n]을 찍는다는 점을 활용합니다.   
answer[i] == v[i%n]이라면 문제를 맞힌 것이므로 1증가하고, 다르면 넘어가는 식으로 수포자 세명 각각이 맞힌 문제 수를 구합니다. 맞힌 문제 수의 최댓값을 구하기 위해 max_element함수를 사용합니다.
문제를 많이 맞힌 사람이 여러명일 때, 수포자 1,2,3 순으로 출력하기 위해 수포자1부터 차례로 맞힌 문제 수와 최대값이 일치하는지 비교한 뒤 결과를 반환합니다.



<br>
- - -

### 코드
```cpp
#include <string>
#include <vector>
#include <algorithm>

using namespace std;

vector<int> one = {1,2,3,4,5};
vector<int> two = {2,1,2,3,2,4,2,5};
vector<int> thr = {3,3,1,1,2,2,4,4,5,5};

vector<int> solution(vector<int> answers) {
    vector<int> answer;
    vector<int> they(3);
    for(int i=0; i<answers.size(); i++) {
        if(answers[i] == one[i%one.size()]) they[0]++;
        if(answers[i] == two[i%two.size()]) they[1]++;
        if(answers[i] == thr[i%thr.size()]) they[2]++;
    }
    int they_max = *max_element(they.begin(),they.end());
    for(int i = 0; i < 3; i++) {
        if(they[i] == they_max) answer.push_back(i+1);
    }
    return answer;
}
```
