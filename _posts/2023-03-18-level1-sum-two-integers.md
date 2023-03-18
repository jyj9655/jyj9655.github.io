---
layout: post
title: (레벨 1) 두 정수 사이의 합 [자바, 파이썬]
subtitle: 두 정수 사이의 합 (프로그래머스 레벨 1)
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
tags: 프로그래머스 파이썬 자바 코딩테스트 합
sidebar: []
---

---

## 문제

수를 담고 있는 배열 arr의 평균값을 return하는 함수, solution 만들기

### 문제 링크

[[프로그래머스] 레벨1 두 정수 사이의 합](https://school.programmers.co.kr/learn/courses/30/lessons/12912)

### 접근방법

a와 b의 크기를 비교한 뒤 반복문을 통해 answer에 저장

### java

#### Solution 1

```java
class Solution {
    public long solution(int a, int b) {
        long answer = 0;
        if (a<b) {
            for (int i=a; i<=b; i++) {
                answer += i;
            }
        } else {
            for (int i=a; i>=b; i--) {
                answer += i;
            }
        }
        return answer;
    }
}
```

#### Solution 2

```java
class Solution {

    public long solution(int a, int b) {
        return sumAtoB(Math.min(a, b), Math.max(b, a));
    }

    private long sumAtoB(long a, long b) {
        return (b - a + 1) * (a + b) / 2;
    }
}
```

---

### python

#### Solution 1

```python
def solution(a, b):
    answer=0
    if a<b :
        for i in range(a,b+1) :
            answer +=i
    else :
        for i in range(b,a+1) :
            answer +=i
    return answer
```

#### Solution 2

```python
def solution(a, b):
    return sum([i for i in range(min(a,b), max(a,b)+1)])
```

---
