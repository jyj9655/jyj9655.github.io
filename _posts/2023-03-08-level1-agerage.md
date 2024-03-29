---
layout: post
title: (레벨 1) 평균 구하기 [자바, 파이썬]
subtitle: 평균 구하기 (프로그래머스 레벨 1)
author: jyj9655
categories: 코딩테스트
banner:
  loop: true
  volume: 0.8
  start_at: 8.5
  image: https://bit.ly/3xTmdUP
  opacity: 0.618
  background: "#000"
  height: "100vh"
  min_height: "38vh"
  heading_style: "font-size: 4.25em; font-weight: bold; text-decoration: underline"
  subheading_style: "color: gold"
tags: 프로그래머스 파이썬 자바 코딩테스트 평균 레벨1
sidebar: []
---

---

## 문제

수를 담고 있는 배열 arr의 평균값을 return하는 함수, solution 만들기

### 문제 링크

[[프로그래머스] 레벨1 평균구하기](https://school.programmers.co.kr/learn/courses/30/lessons/12944)

### 접근방법

배열의 합을 저장할 변수 만들어서 배열의 길이로 나누기

### java

#### Solution 1

```java
class Solution {
    public double solution(int[] arr) {
        int sum = 0;
        for (int i=0; i<arr.length; i++) {
            sum += arr[i];
        }
        double answer = (double)sum/arr.length;
        return answer;
    }
}
```

#### Solution 2

```java
import java.util.*;
import java.lang.*;

class Solution {
    public double solution(int[] arr) {

        return Arrays.stream(arr).average().getAsDouble();
    }
}
```

---

### python

```python
def solution(arr):
    return sum(arr)/len(arr)
```

---
