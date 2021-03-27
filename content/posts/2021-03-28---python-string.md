---
title: 파이썬 - 문자열 활용 메서드
date: '2021-03-28T01:30:37.121Z'
template: 'post'
draft: false
slug: 'python-string'
category: 'python'
tags:
  - 'python'
  - 'string'
  - 'til'
description: '파이썬의 다양한 문자열 활용 '
socialImage: '/media/image-2.jpg'
---

### 2. 문자열

문자열은 작은따옴표로 묶어 출력한다.

```python
aa = [10, 20, 30, 40, 50]
aa[0]
aa[1:3]
# 10
# [20, 30]

ss = "파이썬최고"
ss[0]
ss[1:3]
ss[3:]
# 파
# 이썬
# 최고
```

<p style="font-size: 18px; font-weight: bold;">(1) 문자열의 대소문자 변환 </p>

- `s.upper()` : 문자열 소문자를 대문자로 변환
- `s.lower()` : 문자열 대문자를 소문자로 변환
- `s.swapcase()` : 소문자를 대문자로, 대문자를 소문자로 변환
- `s.capitalize()` : 문자열의 첫문자를 대문자로 변환
- `s.title()` : 각 단어의 앞글자만 대문자로 변환

<p style="font-size: 18px; font-weight: bold;">(2) 문자열 검색 </p>

- `s.count('찾을값')` : 문자열 s 에서 찾을 값의 문자열이 발생한 횟수 리턴
- `s.find('찾을값')` : 문자열 s 에서 찾을 값의 첫번째 인덱스 리턴. 없으면 -1
- `s.find('찾을값', 3)` : 문자열 3번의 위치부터 검색
- `s.rfind('찾을값')` : 문자열의 오른쪽부터 검색
- `s.index('찾을값')` : `find`와 동일, 문자열 검색, 없으면 예외 오류 발생
- `s.startswith('찾을값')` : 찾을 값으로 시작하는 문자열인지 확인 맞으면 true, 아니면 false
- `s.endswith('찾을값')` : 찾을 값으로 끝나는 문자열인지 확인 맞으면 true, 아니면 false

<p style="font-size: 18px; font-weight: bold;">(3) 문자열 편집/치환 </p>

<p style="font-size: 18px; font-weight: bold;">(4) 문자열 분리/결합 </p>

<p style="font-size: 18px; font-weight: bold;">(5) 문자열 정렬/채우기 </p>

<p style="font-size: 18px; font-weight: bold;">(6) 문자열 구성 파악 </p>
