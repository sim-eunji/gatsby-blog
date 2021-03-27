---
title: (책리뷰) 객체지향의 사실과 오해
date: '2021-03-26T14:00:37.121Z'
template: 'post'
draft: false
slug: 'review-essence-of-object-orientation'
category: 'review'
tags:
  - 'review'
  - 'object-orientation'
description: '역할, 책임, 협력 관점에서 본 객체지향'
socialImage: '/media/image-2.jpg'
---

![F4BCA130-79B2-45F6-B39A-792987319382_1_105_c](https://user-images.githubusercontent.com/71164350/112560543-cfb36f80-8e16-11eb-94e4-1edd2315fcd5.jpeg)

내 책상에 아주 오랫동안 꽂혀있던 책 ㅎㅎ  
객체지향이라 말은 많이 해왔지만 실은 객체지향? 클래스! 캡슐화!  
이런식만으로 알고 있어서 책에서 말하고자 하는 객체지향은 무엇일까.. 궁금해져 읽기 시작했다.

책에서 말하는 객체 지향은 현실 속에 존재하는 사물에 대한 추상화고,  
객체 자체를 스스로 생각하는 생명체에 비유하라고 얘기한다.

실세계의 우리 생활 모습이나 책을 인용해서 말해서 좀 더 알기 쉽고 생생하게 다가온다.

### 챕터 1. 협력하는 객체들의 공동체

이번 챕터에서는 커피를 주문하는 과정에서 객체지향의 기본 내용을 말해준다.  
~~  
출근 하기 전, 나는 카페에 가서 주문대에서 캐시어에게 아메리카노 한 잔을 주문했다.  
캐시어는 주문을 받아 바리스타에게 전달했고,  
바리스타는 주문 순서대로 커피를 만들어서 캐시어에게 전달한다.  
캐시어는 진동벨을 울렸고, 나는 커피를 받아서 맛있게 마셨다.  
~~

위와 같이 모든 과정속에서는 손님, 캐시어, 바리스타의 각각의 **역할**이 있고, **협력 관계**가 존재한다.  
여기에 나오는 사람을 객체라고 빗대서 생각해보자.

손님이 캐시어에게 커피를 요청하고, 캐시어는 바리스타에게 커피를 만들라고 요청하고,  
요청을 받은 사람들은 주어진 책임을 다하기 위해 서비스를 제공한다.  
바리스타는 커피를 만들고, 캐시어는 손님에게 전달해준다.

일상에서 발생하는 대부분의 문제는 다수의 **요청과 응답**으로 구성된 협력으로 해결된다.  
사람과 유사한 객체의 특징은 다음과 같다.

- 여러 객체가 동일한 역할을 수행할 수 있다.
- 역할은 대체 가능성을 의미한다.
- 각 객체는 책임을 수행하는 방법을 자율적으로 선택할 수 있다.
- 하나의 객체가 동시에 여러 역할을 수행할 수 있다.

객체는 애플리케이션의 기능을 구현하기 위해 존재하지만, 모든 기능을 혼자 감당하기는 어렵다.  
그래서 객체들은 다른 객체와 조화를 이루면서 협력 해야 한다.  
객체는 **협력적**이여야하고, **자율적**인 존재여야 한다.

**상태와 행동을 함께 지닌 자율적인 객체**

객체는 **상태(state)**와 **행동(behavior)**를 함께 지닌 실체로,
스스로 결정하는 자율적인 존재로 남기 위해서는 필요한 행동과 상태를 함께 지녀야 한다.

자율성은 객체 내부와 외부를 구분하면서 나오는데,
외부에서 간섭할수 없도록 차단해야 하며, 접근이 허락된 수단을 통해서만 의사소통을 한다.  
**객체가 '무엇(what)'을 수행하는지는 알 수 있지만, '어떻게(how)'를 수행하는지는 알수없다.**

**협력과 메세지**

객체지향의 세계에서는 오직 한 가지 의사소통 수단만 존재한다. 이를 **메세지**라고 한다. 메시지를 전송하는 객체를 **송신자(sender)**라고 부르고, 수신하는 객체를 **수신자(receiver)**라고 한다.

**메세드와 자율성**

객체가 수신된 메시지를 처리하는 방법을 **메서드(method)**라 부르고, 메서드를 분리하는 것은 객체의 자율성을 높이는 핵심 매커니즘이다.
이 개념은 **캡슐화** 개념과 깊이 관련되있다.

### 챕터 2. 이상한 나라의 객체

객체는 **상태, 행동, 식별자**를 가진 실체다.  
이 챕터에서 말하고 싶은 중요한 개념은 아래와 같다.

- 객체는 상태를 가지며 변경 가능하다.
- 객체의 상태를 변화 시키는 건 행동이다.
  - 행동은 상태에 의존적이다.
  - 행동의 순서는 결과에 영향을 미친다.
- 어떤 상태에 있어도 객체는 식별 가능하다.

**(1) 상태**  
상태가 필요한 이유는, 과거 발생한 행동의 이력으로 현재 행동의 결과를 비교해서 객체가 가진 값을 비교하기 어렵기 때문이다.
상태를 이용하면 현재를 기반으로 행동 방식을 이해할 수 있다

상태를 구성하는 모든 특징을 **프로퍼티**라 한다. 그 중 숫자, 문자열, 양, 속도, 시간, 날짜 등 상태를 표현하기 위해 사용되는 걸 **속성(attribute)**라 부르고,
객체와 객체 사이의 의미 있는 연결을 **링크**라 한다.  
객체와 객체사이는 링크가 존재해야 요청(메세지)를 주고 받을 수 있다.

**(2) 행동**  
객체의 행동은 객체 자신의 상태를 변경한다.  
외부 요청이나 수신된 메세지에 응답하기 위해 동작하고 반응한다.

모든 객체는 자율적인 존재여서, 다른 객체의 상태에 직접적으로 접근 할 수 없고, 변경 할 수도 없다.  
이러한 객체의 특징은 **캡슐화**를 잘 나타낸다.

**(3) 식별자**  
식별자는 객체를 서로 구분 가능 할 수 있는 특정한 프로퍼티다.

상태를 먼저 결정하고 행동을 나중에 결정하는 방법은 설계에 나쁜 영향을 끼친다.

- 상태를 먼저 결정할 경우 캡슐화가 저해된다.
- 객체를 협력자가 아닌 고립되게 만든다.
- 객체의 재사용성이 저하된다.

객체지향 설계는 애플리케이션에 필요한 협력을 생각하고 협력에 참여하는 데 필요한 행동을 생각한 후 행동을 수행할 객체를 선택하는 방식으로 수행된다.  
행동을 결정한 후에야 행동에 필요한 정보가 무엇인지를 고려하며 이 과정에서 필요한 상태가 결정된다.