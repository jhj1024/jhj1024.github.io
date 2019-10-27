---
layout: post
title: 프로그래머스 Lv1. 이상한 문자 만들기
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 문자열 s는 한 개 이상의 단어로 구성되어 있습니다. 각 단어는 하나 이상의 공백문자로 구분되어 있습니다. 각 단어의 짝수번째 알파벳은 대문자로, 홀수번째 알파벳은 소문자로 바꾼 문자열을 리턴하는 함수, solution을 완성하세요.
> 
> 제한 조건
> * 문자열 전체의 짝/홀수 인덱스가 아니라, 단어(공백을 기준)별로 짝/홀수 인덱스를 판단해야합니다.
> * 첫 번째 글자는 0번째 인덱스로 보아 짝수번째 알파벳으로 처리해야 합니다.

<br>

- - -

### 풀이

<br>

- - -

### 코드
```cpp
#include <string>
#include <vector>
#include <cctype>

using namespace std;

string solution(string s) {
    string answer = "";

    int ws = 0;
    char alpha;
    for(int i = 0; i < s.size(); i++){
        alpha = s[i];
        
        if(s[i] == ' '){
            ws = 0;
            answer += s[i];
            continue;
        }
        
        if(ws%2 == 0){
            answer += toupper(alpha);//대문자
        }
        
        else{
            answer += tolower(alpha);//소문자
        }
        ws++;        
    }
    
    return answer;
}
```
