---
title: 파이썬 - 리스트, 튜플, 딕셔너리
date: '2021-03-28T01:30:37.121Z'
template: 'post'
draft: false
slug: 'python-list'
category: 'python'
tags:
  - 'python'
  - 'til'
description: '파이썬의 리스트, 튜플, 딕셔너리의 개념과 사용법을 알아보자'
socialImage: '/media/image-2.jpg'
---

<img width="665" alt="image" src="https://user-images.githubusercontent.com/71164350/112729002-4ebabc00-8f6d-11eb-9ab4-3b6dd6866c10.png">

### 1. 리스트

배열과 다르게 정수, 문자열, 실수 등 서로 다른 데이터형도 하나로 묶을 수 있다.  
값이 변할 수 있는 데이터 타입(Mutable Type)을 가졌다.

변수를 선언하기 위해 대괄호 [] 를 사용하고,  
항목은 쉼표 기호(,) 로 구분한다.

```
# 리스트의 선언
cards = [3, 1, 5, 2]
```

<p style="font-size: 18px; font-weight: bold;">(1) 리스트의 사용 </p>

빈 리스트의 생성과 항목 추가 : **리스트명.append(값)**

```python
aa = []
aa.append(1)
aa.append(2)
aa.append(3)
print(aa)
# [1, 2, 3]

bb = []
for i in range(0, 100) :
  bb.append(i)
len(bb)
# 100
```

<p style="font-size: 18px; font-weight: bold;">(2) 리스트 조작 함수 </p>

| 함수        | 설명                               | 사용법                        |
| ----------- | ---------------------------------- | ----------------------------- |
| `append()`  | 리스트 맨 뒤에 항목을 추가         | 리스트명.append(값)           |
| `pop()`     | 리스트 맨 뒤에 항목을 삭제         | 리스트명.pop()                |
| `sort()`    | 리스트 항목을 정렬                 | 리스트명.sort()               |
| `reverse()` | 리스트 항목을 역순으로 정렬        | 리스트명.reverse()            |
| `index()`   | 지정한 값을 찾아 위치를 반환       | 리스트명.index(찾을값)        |
| `insert()`  | 지정된 위치에 값을 삽입            | 리스트명.insert(위치, 값)     |
| `remove()`  | 지정한 값을 삭제                   | 리스트명.remove(지울값)       |
| `extend()`  | 리스트 뒤에 리스트를 추가          | 리스트명.extend(추가할리스트) |
| `count()`   | 해당 값의 개수를 센다              | 리스트명.count(찾을값)        |
| `clear()`   | 리스트의 내용을 모두 지운다        | 리스트명.clear()              |
| `del()`     | 리스트에서 해당 위치의 항목을 삭제 | del(리스트명[위치])           |
| `len()`     | 리스트의 전체 항목 개수            | len(리스트명)                 |

### 2. 튜플(Tuple)

튜플은 리스트와 사용법이 비슷하면서도 다르다.  
리스트는 대괄호 [] 로 생성하지만, 튜플은 소괄호 () 로 생성한다.  
튜플은 값을 **수정할 수 없고, 읽기만 가능**하다. 괄호를 생략해도 튜플이 생성된다.

```python
tt1 = (10, 20, 30); tt1
tt2 = 40, 50, 60

tt1.append(40)
# 오류 발생!
# AttributeError: 'tuple' object has no attribute 'append'
```

<p style="font-size: 18px; font-weight: bold;">(1) 튜플 <-> 리스트 </p>

```python
my_tuple = (1, 2, 3)
my_list = list(my_tuple)
my_list.append(4)
my_tuple = tuple(my_list)
print(my_tuple)
# (1, 2, 3, 4)
```

### 3. 딕셔너리 (Dictionary)

전체 항목이 정렬되지 않은 **키와 쌍(key: value)**으로 구성된 데이터 모음  
변경할 수 있는 데이터 타입으로 각 쌍은 쉼표 기호로 구분하고, 전체 집합은 중괄호 {} 기호로 감싼다.
딕셔너리의 **키는 유일**해야 하므로 동일한 키를 갖을 땐, 마지막의 키가 적용된다.

```python
my_dic = { 'a' : 1, 'b' : 2, 'c' : '3' }
# { 'a' : 1, 'b' : 2, 'c' : '3' }
```

학생의 정보를 담는 딕셔너리를 만들어보자.  
학생의 학번, 이름, 학과가 포함되어야 한다.

```python
student_sim = { '학번' : 2021, '이름' : '심은지', '학과' : '미디어경영학과' }
student_sim['연락처'] = '010-1111-2222' # 연락처 추가 수정
```

딕셔너리의 키 값을 확인하고 싶을 땐, `keys()`를 사용한다.  
반환 값은 `dict_keys()` 타입으로 반환되며, 리스트 함수를 사용할 수 있다.

```python
student_sim.keys()
list(student_sim.keys())
list(student_sim.values())

# dict_keys(['학번', '이름', '학과', '연락처'])
# ['학번', '이름', '학과', '연락처']
# [2021, '심은지', '미디어경영학과', '010-1111-2222']
```

특정 키워드를 확인할 경우에는 `in` 을 사용한다.

```python
'학번' in student_sim
True

'주소' in student_sim
False
```

특정 항목을 삭제하고 싶을 때 `del`, 전체 항목을 사용하고 싶을 때는 `clear()`를 사용한다.

```python
del student_sim['연락처']
student_sim.clear()
```

딕셔너리의 키로 값을 접근하려면 `딕셔너리명.get(키)`, `딕셔너리명[키]` 결과는 같다.  
`딕셔너리명[키]` 는 없는 키를 호출하면 에러가 나지만, `딕셔너리명.get(키)` 일때는 아무것도 반환하지 않는다.

```python
student_sim['학번']
student_sim.get('학번')

# 2021
# 2021
```

`딕셔너리명.items()` 함수를 구현하면 **튜플** 형태로 구할 수 있다.

```python
student_sim.items()
# dict_items([('학번', 2021), ('이름', '심은지'), ('학과', '미디어경영학과'), ('연락처', '010-1111-2222')])
```
