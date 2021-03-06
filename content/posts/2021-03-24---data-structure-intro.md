---
title: 자료구조 Intro
date: '2021-03-24T10:00:37.121Z'
template: 'post'
draft: false
slug: 'data-structure-intro'
category: '자료구조'
tags:
  - '자료구조'
  - '알고리즘'
description: '더 이상 미룰 수 없다. 자료구조와 알고리즘 '
socialImage: '/media/image-2.jpg'
---

## 자료구조의 필요성

1. 데이터를 효과적으로 저장하고, 처리하는 방법에 대해서 바르게 이해할 필요가 있다.
2. 자료구조를 제대로 이해하지 못하면 불필요하게 메모리와 성능을 낭비할 여지가 있다.

## 기본적인 자료구조들

1. 선형 구조

- 배열 (Array)
- [연결 리스트 (Linked List)](Data-Structures/Linked-List)
- 스택 (Stack)
- 큐 (Queue)

2. 비선형 구조

- 트리 (Tree)
- 그래프 (Graph)

## 자료구조와 알고리즘의 상관관계

1. 효율적인 자료구조 설계를 위해 알고리즘 지식이 필요하다.
2. 효율적인 알고리즘을 작성하기 위해서는 문제 상황에 맞는 적절한 자료구조가 사용되어야 한다.
3. 따라서 자료구조론과 알고리즘 이론은 모두 동일 선상에 놓을 수 있다.

## 프로그램의 성능 측정 방법론

1. `시간 복잡도 (Time Complexity)` 란 알고리즘에 사용되는 연산 횟수
2. `공간 복잡도 (Space Complexity)` 란 알고리즘에 사용되는 메모리의 양

-> 효율적인 알고리즘을 사용한다는 가정하에, 시간과 공간은 **반비례 관계**이다.

### 시간 복잡도

시간 복잡도를 표현할 때는 최악의 경우를 나타내는 **Big-O 표기법**을 사용

시간복잡도에서 중요하게 보는것은 가장 큰 영향을 미치는 n의 단위이다.

아래 표는 입력 N값에 따른 알고리즘의 시간 복잡도이다.

| Complexity | 1   | 10      | 100                             |
| ---------- | --- | ------- | ------------------------------- |
| O(1)       | 1   | 1       | 1                               |
| O(log N)   | 0   | 2       | 5                               |
| O(N)       | 1   | 10      | 100                             |
| O(N log N) | 0   | 20      | 461                             |
| O(N^2)     | 1   | 100     | 10000                           |
| O(2^N)     | 1   | 1024    | 1267650600228229401496703205376 |
| O(N!)      | 1   | 3628800 | 너무 많아!                      |

### O(1)의 시간복잡도; 상수

입력에 관계없이 복잡도는 동일하게 유지된다.

```javascript
function print(n) {
  console.log('hello!')
}
```

### O(n)의 시간복잡도; 선형

입력이 증가하면 처리 시간또는 메모리 사용이 선형적으로 증가한다.

```javascript
function print(arr) {
  for (let item in arr) {
    console.log(item)
  }
}
```

### O(n^2)의 시간복잡도; Square

반복문이 2번있는 케이스

```javascript
function print(arr) {
  for (let i in arr) {
    for (let j in arr) {
      console.log(j)
    }
  }
}
```

시간 복잡도를 표기할 때는 항상 큰 항과 계수만 표시한다.

```
𝑂(3𝑛2 + 𝑛) = 𝑂(𝑛2)
```

## 시간복잡도를 구하는 요령

각 문제의 시간복잡도 유형을 빨리 파악할 수 있도록 아래 예를 통해 빠르게 알아 볼수 있다.

    하나의 루프를 사용하여 단일 요소 집합을 반복 하는 경우 : O (n)
    컬렉션의 절반 이상 을 반복 하는 경우 : O (n / 2) -> O (n)
    두 개의 다른 루프를 사용하여 두 개의 개별 콜렉션을 반복 할 경우 : O (n + m) -> O (n)
    두 개의 중첩 루프를 사용하여 단일 컬렉션을 반복하는 경우 : O (n²)
    두 개의 중첩 루프를 사용하여 두 개의 다른 콜렉션을 반복 할 경우 : O (n * m) -> O (n²)
    컬렉션 정렬을 사용하는 경우 : O(n*log(n))
