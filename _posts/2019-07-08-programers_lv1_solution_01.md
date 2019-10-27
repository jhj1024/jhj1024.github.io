---
layout: post
title: 프로그래머스 Lv1. 소수의 합
categories: [solution]
description: "2부터 N까지의 모든 소수의 합 구하기"
date: 2019-07-08
tags: [vector, 에라토네스의 체]
share: true
---


### 문제 설명
> ##### 2부터 N까지의 모든 소수의 합을 구하세요.
>
> 제한 조건
> * N의 범위: 2이상 10,000,000이하
>* 시간 제한: 1초

<br>

- - -

### 풀이
에라토네스의 체 이용


```CPP
void Eratos(int n) {
    vector<bool> sieve(n+1); //에라토네스의 체(default:false)
    
    for(int i = 2; i <= n; i++){
        if(sieve[i] == false){ //소수인 경우
            //
        }
        
        for(int j = i; j <= n; j+=i) {
            sieve[j] = true;  //i의 배수는 제외시킴
        }
    }
```

<br>
- - -
### 코드
```cpp
#include <vector>

using namespace std;

long long solution(int N) {
    long long answer = 0;
    vector<bool> sieve(N+1); //에라토네스의 체(default:false)
    
    for(int i = 2; i <= N; i++){
        if(sieve[i] == false){ //소수인 경우
            answer += i; //합함
        }
        
        for(int j = i; j <= N; j+=i) {
            sieve[j] = true;  //i의 배수는 제외시킴 
        }
    }
    return answer;
}
```

