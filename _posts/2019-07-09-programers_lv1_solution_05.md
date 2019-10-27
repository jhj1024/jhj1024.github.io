---
layout: post
title: 프로그래머스 Lv1. 2016년
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 2016년 1월 1일은 금요일입니다.   
> ##### 2016년 a월 b일은 무슨 요일일까요? 
> ##### 두 수 a ,b를 입력받아 2016년 a월 b일이 무슨 요일인지 리턴하는 함수, solution을 완성하세요. 
> ##### 요일의 이름은 일요일부터 토요일까지 각각 [SUN,MON,TUE,WED,THU,FRI,SAT] 입니다.     ##### 
> ##### 예를 들어 a=5, b=24라면 5월 24일은 화요일이므로 문자열 TUE를 반환하세요.
> 
> 제한 조건
> * 2016년은 윤년입니다.
> * 2016년 a월 b일은 실제로 있는 날입니다. (13월 26일이나 2월 45일같은 날짜는 주어지지 않습니다)

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

string solution(int a, int b) {
    vector<int> month = {0,31,29,31,30,31,30,31,31,30,31,30};
    vector<string> dow = {"THU", "FRI", "SAT", "SUN", "MON", "TUE", "WED"};
    int day = 0;
    
    for(auto i = 0; i < a; i++){
        day += month.at(i);
    }
    
    day += b;
    
    int result = day%7;
    
    string answer = dow.at(result);
    return answer;
}
```
