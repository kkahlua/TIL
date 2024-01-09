# 1월 8일 Today I Learned

---

# 💯 오늘 배운 내용 중에서 몰랐던 부분만 간략히 정리!

## 🔴 일급객체

일급객체란, 다른 객체들에 일반적으로 적용 가능한 연산을 모두 지원하는 객체를 의미한다.

일급객체는 다음과 같은 조건을 만족해야한다.

1. 일급객체는 함수의 실제 매개변수가 될 수 있다.
2. 일급객체는 함수의 반환값이 될 수 있다.
3. 일급객체는 할당명령문의 대상이 될 수 있다.(변수 등에 할당가능)
4. 일급객체는 동일비교의 대상이 될 수 있다. (값으로 표현 가능)

JS에서 함수는 일급객체의 특징을 모두 갖고 있기 때문에 함수로 예시를 들어 위의 조건을 확인해보면

![JS의 함수는 함수의 실제 매개변수가 될 수 있다.](/images/20240108.png)

JS의 함수는 함수의 실제 매개변수가 될 수 있다.

a함수에서 b함수를 매개변수로 받아 b함수가 실행된 것을 확인할 수 있다.

![Untitled](/images/20240108%201.png)

실행 결과가 함수 b인 것을 확인 할 수 있고

![JS의 함수는 함수의 반환값이 될 수 있다.](/images/20240108%202.png)

JS의 함수는 함수의 반환값이 될 수 있다.

한번 더 실행했을 때 b함수가 실행되어 결과 같이 나온 것을 확인할 수 있다.

이처럼 a함수가 반환한 값이 함수b가 된 것을 확인 할 수있다.

![JS의 함수는 할당명령문의 대상이 될 수 있다. / JS의 함수는 동일비교의 대상이 될 수 있다.](/images/20240108%203.png)

JS의 함수는 할당명령문의 대상이 될 수 있다. / JS의 함수는 동일비교의 대상이 될 수 있다.

3,4번 조건도 위와 같이 확인할 수 있다.

## 🔴 표현식

표현식은 **어떤 값으로 이행되는 임의의 유효한 코드 단위**이다.

따라서 **값으로 평가될 수 있는 문은 모두 표현식**이라고 볼 수 있다.

표현식은 개념적으로 2가지 범주로 나뉜다.

1. 부수 효과가 있는 표현식 ex) 변수에 값을 할당
2. 표현식을 평가하면 어떤 값으로 이행하는 표현식

## 🔴 Exception

Exception은 런타임 때 발생할 수 있는 의도치 않은 상황을 뜻한다.

Exception을 핸들링하지 않는다면, 기능이 동작하지 않거나, 어플리케이션이 shout down될 수 있다.

## 🔴 Exception의 원인

- 코드 레벨에서의 문제
- 하드웨어, 디바이스의 문제
- 라이브러리 손상
- 사용자의 입력 실수

## 🔴 Exception의 종류

1. ECMAScript Error: 자바스크립트 언어에서 발생하는 Error Type
2. DOMException: Web API 레벨에서 발생하는 Error Type
3. 그 외 예외

## 🔴 ECMAScript Error

: JS에서 발생하는 Error Type 중 하나이고,

1. RangeError
2. ReferenceError
3. SyntaxError
4. TypeError

등이 발생한다.

![Untitled](/images/20240108%204.png)

RangeError: 값이 집합에 없거나, 허용범위가 아닐 때 발생한다.

![Untitled](/images/20240108%205.png)

ReferenceError: 존재하지 않는 변수 참조 시 발생한다.

![Untitled](/images/20240108%206.png)

SyntaxError: 문법을 지키지 않았을 때 발생한다.

![Untitled](/images/20240108%207.png)

TypeError: 값이 기대한 자료형이 아니여서 연산이 불가능할 때 발생한다.

## 🔴 DOMException Error

: Web API 레벨에서 발생하는 Error Type이고, 다음과 같은 에러가 발생한다.

1. NetworkError : 네트워크 에러 발생 시 발생한다.
2. AbortError : 작업이 중단되었을 때 발생한다.
3. TimeoutError : 작업 시간이 초과되었을 때 발생한다.

## 🔴 Error Object

![Untitled](/images/20240108%208.png)

Error Object에는 name, message 2개의 속성이 존재하고,

사용자가 직접 Error Object를 정의하여 사용할 수 있다.

## 🔴 Call Stack

- JS코드가 실행되며 생성되는 Execution Context를 저장하는 자료구조
- 함수를 호출할 때마다 스택이 쌓이고, 함수의 실행이 종료되면, Call Stack에서 스택을 제거하는 원리이다.
- Error가 throw되면 Call Stack을 확인하여, 핸들링하고 있는 Catch문이 있는 스택에서 처리한다.
