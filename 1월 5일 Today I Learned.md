# 1월 5일 Today I Learned

---

# 💯 오늘 배운 내용 중에서 몰랐던 부분만 간략히 정리!

## 🔴 Hoisting

**Hoisting**은 식별자(변수, 함수, 클래스)를 선언했을 때 scope내의 최상단으로 끌어 올려지는 것처럼 보이는 현상이다.

var, let ,const 모두 hoisting이 발생하지만, let과 const는 초기화 되기 전까지 **TDZ**에 머물러 있기 때문에 hoisting이 발생하지 않는것처럼 보이며 참조가 불가능하다.

## 🔴 Hoisting이 발생하는 이유

**Excution Context**는 **Environment Record**와 **Outer Lexical Environment Reference**로 구성된다.

그 중 **Environment Record**는 유효 범위 안의 식별자와 결과값을 바인드 해서 기록하는 영역이다. 

여기에 함수 선언, 변수명 등이 담기는데, Context내부 전체를 처음부터 끝까지 훑으면서 순서대로 수집한다.

따라서 자바스크립트 엔진은 코드가 실행되기 전에도 이미 해당 환경에 속한 코드 변수명들을 알고 있기 때문에

 **Hoisting**이 일어나는 것이다.

## 🔴 TDZ ( ****Temporal Dead Zone)****

TDZ는 일시적인 사각지대로, 변수를 사용하는 것을 비허용하는 개념상의 공간이다.

TDZ에 있는 값에 접근하게 되면 ***ReferenceError: Cannot access 'xxx' before initialization***에러가 

발생한다. 

## 🔴 변수를 var로 선언하면 안좋은 이유

```jsx
a = 1; // 앞에 var붙이지 않아도 선언이 된다.
var a = "zz"; // 중복 선언이 가능하다.
console.log(window.a); // 전역변수화
```

1. var 키워드는 생략이 가능하다.
2. 중복 선언이 가능하기 때문에 의도치 않게 값이 변경되거나, 값을 추론하기 어려워진다.
3. 변수 Hoisting이 발생한다.
4. 전역 변수화되기 때문에 의도치 않게 값이 변경되거나, 값을 추론하기 어려워진다.

## 🔴 변수 Naming Convention

- **Camel Case** (카멜 표기법) : setTitle

⇒ 첫번째 단어를 제외하고 첫 글자를 대문자로 표기한다.

- **Snake Case** (스네이크 표기법) : set_title
    
    ⇒ 전부 소문자로 표기하고 단어 사이에 _를 표기한다.
    
- **Pascal Case** (파스칼 표기법) : SetTitle
    
    ⇒ 단어 첫 글자를 대문자로 표기한다.
    

- **Constant Case** : SET_TITLE
    
    ⇒ 전부 대문자로 표기하고 단어사이에 _를 표기한다. 주로 상수변수를 사용할 때만 사용한다