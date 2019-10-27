---
layout: post
title: 프로그래머스 Lv2. 
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-09
tags: [알고리즘]
share: true
---

### 문제 설명
> ##### 두 수의 최소공배수(Least Common Multiple)란 입력된 두 수의 배수 중 공통이 되는 가장 작은 숫자를 의미합니다. 예를 들어 2와 7의 최소공배수는 14가 됩니다. 정의를 확장해서, n개의 수의 최소공배수는 n 개의 수들의 배수 중 공통이 되는 가장 작은 숫자가 됩니다. n개의 숫자를 담은 배열 arr이 입력되었을 때 이 수들의 최소공배수를 반환하는 함수, solution을 완성해 주세요.
> 
> 제한 조건
> * arr은 길이 1이상, 15이하인 배열입니다.
> * arr의 원소는 100 이하인 자연수입니다.

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

//두 수의 최소공배수 n1을 구하고, n1과 다음 수의 최소공배수 n2...를 구하는 식
//최소공배수는 유클리드 호제법 이용

int gcdf(int a, int b){
    if(a%b == 0)
        return b;
    else
        return gcdf(b, a%b);
}

int solution(vector<int> arr) {
    sort(arr.begin(), arr.end()); //크기비교를 생략하기 위해 정렬
    
    int a, b, gcd, lcm;
    b = arr[0];
    for(int i = 1; i < arr.size(); i++){
        a = arr[i];
        gcd = gcdf(a, b);
        lcm = a*b/gcd;
        b = lcm;
    }
    
    
    return lcm;
}
```
