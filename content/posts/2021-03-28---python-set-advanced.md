---
title: 파이썬 - Set, 리스트, 튜플, 딕셔너리의 심화
date: '2021-03-28T13:35:37.121Z'
template: 'post'
draft: false
slug: 'python-set-advanced'
category: 'python'
tags:
  - 'python'
  - 'til'
description: '파이썬의 Set과 리스트, 튜플, 딕셔너리의 활용 방법을 알아보자'
socialImage: '/media/image-2.jpg'
---

<img width="665" alt="image" src="https://user-images.githubusercontent.com/71164350/112729002-4ebabc00-8f6d-11eb-9ab4-3b6dd6866c10.png">

### 1. 세트 (set)

키만 모아놓은 딕셔너리의 특수한 형태다.  
딕셔너리의 키는 중복되면 안되므로, **세트에 있는 값은 항상 유일**하다.  
딕셔너리처럼 중괄호 {} 를 사용해서 생성한다.

```python
my_set = { 'name', 'address', 'phone_number' }
```

`set()` 함수를 사용해 리스트나 튜플, 딕셔너리를 세트로 변경시킬 수 있다.

두 세트 사이의 집합을 구할 때도 유용하게 쓰인다.

```python
my_set1 = { 1,2,3,4,5 }
my_set2 = { 4,5,6,7 }

my_set1 & my_set2  # 교집합
my_set1.intersection(my_set2) # 교집합

my_set1 | my_set2 # 합집합
my_set1.union(my_set2) # 합집합

my_set1 - my_set2 # 차집합
my_set1.difference(my_set2) # 차집합

my_set1 ^ my_set2 # 대칭 차집합
my_set1.symmetric_difference(my_set2) # 대칭 차집합
```

### 2. 컴프리헨션

기존에 순차적인 리스트를 한 줄로 만드는 간단한 방법이다.  
여러 줄의 코드를 짧게 줄일 수 있기 때문에 익숙해 지는 것이 좋다!

```python
num_list = []
for num in range(1, 6) :
    num_list.append(num)
print(num_list)
# [1,2,3,4,5,6]
```

```python
num_list = [num for num in range(1, 6)]
print(num_list)
# [1,2,3,4,5,6]
```

컴프리헨션은 다음 형식으로 구성된다.

```
리스트 = [수식 for 항목 in range() if 조건식]
```

### 3. 동시에 여러 리스트를 접근

`zip()` 함수를 사용하면 동시에 여러 리스트에 접근할 수 있다.

```python
foods = ['떡볶이', '짜장면', '라면', '피자' '맥주', '치킨', '삼겹살']
sides = ['오뎅', '단무지', '김치']

for food, side in zip(foods, sides) :
  print(food, '-->', side)
```

개수가 작은 것까지만 접근한 후 종료한다.  
두 리스트를 튜플이나 딕셔너리를 짝지을 때도 간단하게 활용할 수 있다.

```python
foods = ['떡볶이', '짜장면', '라면', '피자' '맥주', '치킨', '삼겹살']
sides = ['오뎅', '단무지', '김치']

tup_list = list(zip(foods, sides))
dic = dict(zip(foods, sides))

print(tup_list)
print(dic)

# [('떡볶이', '오뎅'), ('짜장면', '단무지'), ('라면', '김치')]
# {'떡볶이': '오뎅', '짜장면': '단무지', '라면': '김치'}
```

### 4. 리스트의 복사

```python
old_list = ['짜장면', '짬뽕', '볶음밥']
new_list = old_list

print(new_list)
# ['짜장면', '짬뽕', '볶음밥']

old_list[0] = '탕수육'
old_list.append('깐풍기')

print(new_list)
# ['탕수육', '짬뽕', '볶음밥', '깐풍기']
```

위 코드처럼 리스트를 복사할 때는 주의할 점이 있다.  
`new_list`를 `old_list`에 대입하면서 둘은 동일한 메모리 공간을 공유한다.  
그래서 `old_list` 를 수정해도 결과적으로 `new_list`가 변경된다.

위 같은 현상을 **얕은 복사(Shallow Copy)**라고 한다.  
위를 방지하려면 복사하고 싶은 리스트의 메모리의 공간을 복사해서 새로 만들어야 한다.

```python
old_list = ['짜장면', '짬뽕', '볶음밥']
new_list = old_list[:]
# new_list = old_list.copy()
print(new_list)
# ['짜장면', '짬뽕', '볶음밥']

old_list[0] = '탕수육'
old_list.append('깐풍기')

print(new_list)
# ['짜장면', '짬뽕', '볶음밥']
```

`new_list = old_list[:]` 나, `new_list = old_list.copy()` 를 사용하자.  
위와 같은 방법은 메모리 공간을 공간해서 새로 만든다. 이를 **깊은 복사(Deep copy)**라 한다.
