---
layout: post
title: 클로저 함수
date:  2021-10-6 21:10:36 +0530   
categories: Javascript NodeJS
---

### 클로저 함수
클로저 함수는 크게 2가지 특징이 있다

- 함수를 리턴하는 함수이다
```js
const adder = x => y => x + y;
adder(5)(7); // 12

typeof adder(5) // 'function'
adder(5) // y => x + y
```

adder 함수의 리턴 값이 함수이다
함수표현식으로 바꾸면 다음과 같다

```js
const adder = function (x) {
    return function (y) {
      return x + y;
    }
}
```

- 리턴하는 함수에 의해 스코프가 구분됨

![](https://images.velog.io/images/ljy505541/post/11f0cf95-7904-4f57-b6f3-d738491d6e0d/image.png)

외부함수의 변수 x 와 내부함수의 변수 y
클로저함수도 스코프의 규칙에 따라
안쪽 스코프에서 바깥쪽 스코프로는 변수에 접근할 수 있지만
반대(바깥쪽 스코프에서 안쪽스코프로 접근)는 불가능하다

내부함수는 x에 접근가능, 외부함수는 y에 접근불가
즉, 클로저함수의 **내부 함수는 외부 함수에 선언된 변수에 접근 가능**하다