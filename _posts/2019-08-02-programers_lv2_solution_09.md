---
layout: post
title: 프로그래머스 Lv2. 전화번호 목록
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 전화번호부에 적힌 전화번호 중, 한 번호가 다른 번호의 접두어인 경우가 있는지 확인하려 합니다.
전화번호가 다음과 같을 경우, 구조대 전화번호는 영석이의 전화번호의 접두사입니다.

구조대 : 119
박준영 : 97 674 223
지영석 : 11 9552 4421
> ##### 전화번호부에 적힌 전화번호를 담은 배열 phone_book 이 solution 함수의 매개변수로 주어질 때, 어떤 번호가 다른 번호의 접두어인 경우가 있으면 false를 그렇지 않으면 true를 return 하도록 solution 함수를 작성해주세요.
> 
> 제한 조건
> * phone_book의 길이는 1 이상 1,000,000 이하입니다.
> * 각 전화번호의 길이는 1 이상 20 이하입니다.

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

bool solution(vector<string> phone_book) {
    bool answer = true;
    
    sort(phone_book.begin(), phone_book.end());
    
    int i  = 0;
    string value;
    
    while(i < phone_book.size())
    {
        value = phone_book[i];
        phone_book.erase(phone_book.begin()+i);
        for(string phone : phone_book){
            if(phone.find(value) != string::npos){
                return false;
            }   
        } 
    }
    return answer;
}
```
