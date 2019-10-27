---
layout: post
title: 프로그래머스 Lv1. 같은 숫자는 싫어
categories: [solution]
description: "알고리즘 풀이"
date: 2019-07-10
tags: [알고리즘]
share: true
---

### 문제 설명

배열 arr가 주어집니다. 배열 arr의 각 원소는 숫자 0부터 9까지로 이루어져 있습니다.   
이때, 배열 arr에서 연속적으로 나타나는 숫자는 하나만 남기고 전부 제거하려고 합니다. 단, 제거된 후 남은 수들을 반환할 때는 배열 arr의 원소들의 순서를 유지해야 합니다. 

예를 들면, arr = [1, 1, 3, 3, 0, 1, 1] 이면 [1, 3, 0, 1] 을 return 합니다.
arr = [4, 4, 4, 3, 3] 이면 [4, 3] 을 return 합니다.

배열 arr에서 연속적으로 나타나는 숫자는 제거하고 남은 수들을 return 하는 solution 함수를 완성해 주세요.

제한 조건
- 배열 arr의 크기 : 1,000,000 이하의 자연수   
- 배열 arr의 원소의 크기 : 0보다 크거나 같고 9보다 작거나 같은 정수

<br>

- - -

### 풀이
'algorithm' 헤더의 unique 함수는 vector 배열에서 연속된 중복 원소를 삭제하는 기능입니다. 
다만 vector의 크기를 같이 조절하지 않기 때문에 만일 원소가 [1,3,3,0,0,2]인 벡터 v를 이용하여 unique(v.begin(), v.end())를 수행하면 [1,3,0,2,0,2]가 됩니다.
불필요한 뒷부분까지 모두 제거하기 위해서는 erase함수가 필요합니다.
v.erase(unique(v.begin(), v.end()), v.end())를 이용하면 중복된 원소를 제외한 벡터만 반환하게됩니다.
<br>

- - -

### 코드
```cpp
#include <vector>
#include <iostream>

using namespace std;

vector<int> solution(vector<int> arr) 
{    
    arr.erase(unique(arr.begin(), arr.end()), arr.end())
    return arr
}
```
