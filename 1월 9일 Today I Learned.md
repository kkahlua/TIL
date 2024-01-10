# 1월 9일 Today I Learned

---

# 💯 오늘 배운 내용 중에서 몰랐던 부분만 간략히 정리!

## 🔴 Object의 static method

: static method는 object의 호출 없이 바로 사용할 수 있는 method를 의미한다.

static method는 크게

- 객체 자체와 관련된 method
- 객체 속성과 관련된 method
- 객체 속성의 값과 관련된 method

로 나뉜다.

## 🟠 객체 자체와 관련된 method

- 객체 복사 : assign
- 객체 신규 생성 : Create
- 객체 고정 : freeze, preventExtensions, seal
- 객체 상태 확인: isExtensible, isFrozen, isSealed
- 객체를 배열로 반환 : entries, fromEntries
- 객체 prototype : getOwnPropertyOf, setOwnPropertyOf

## 🟠 객체 속성과 관련된 method

- 객체 속성 추가 : defineProperty, defineproperties
- 객체 속성 서술자 : getownpropertyDescriptor, getOwnPropertyDescriptors
- 객체 속성 열거 : getOwnPropertyNames, keys, getOwnPropertySymbols

## 🟠 객체 속성의 값과 관련된 method

- 객체 값 비교 : is
- 객체 값 열거 : values

## 🔴 객체 속성을 나열하는 방법

1. for...in

   : 객체의 프로토타입 체인의 속성을 포함한 모든 열거 가능한 속성을 순회한다.

2. Object.keys

   : 객체 자신의 열거 가능한 속성 이름을 배열로 반환

3. Object.getownPropertyNames

   : 객체 자신만의 모든 속성을 배열로 반환

```jsx
const student = {
  gender: "male",
  grade: "A+",
  age: "20",
};

function Freshman(name) {
  this.name = name;
}

Freshman.prototype = student;

const minsu = new Freshman("Kim");
```

![Untitled](/images/20240109.png)

for… in을 통해 객체를 나열했을 때만 prototype으로 지정했던 gender, grade, age를 확인할 수 있다.

## 🔴 Object의 비교

Object는 Reference type이다.

따라서 모든 연산이 메모리 주소값으로 처리된다.

```jsx
const func1 = {
  value: "abc",
};

const func2 = {
  value: "abc",
};
```

![Untitled](/images/20240109%201.png)

func1과 func2는 같은 “abc”라는 value값을 가졌지만 객체끼리 비교했을 때는 false값을 가진다.

같은 value값을 가졌다고 해도 func1객체의 주소값과 func2객체의 주소값은 다르기 때문에

위와 같은 결과가 나왔다.

## 🔴 Object에서의 Shallow Copy

복사된 Object의 속성 중 하나라도 같은 참조를 하고 있게되면 Shallow Copy가 된다.

```jsx
const food = {
  name: "---",
  price: {
    weekDay: 100,
    weekEnd: 150,
  },
};

let pizza = Object.assign({}, food);
let burger = { ...food };

pizza.name = "potato";
burger.name = "bulgogi";
```

Object.assign을 이용하거나 Spread 연산자를 이용하여 Shallow Copy할 수 있다.

![Untitled](/images/20240109%202.png)

![Untitled](/images/20240109%203.png)

![Untitled](/images/20240109%204.png)

pizza와 burger는 food 객체에서 같은 price 속성을 참조하고 있기 때문에 shallow copy가 되었고,

pizza의 price.weekDay를 변경했을 때 burger의 price.weekDay도 변경된 것을 통해 확인할 수 있다.

## 🔴 Object에서의 Deep Copy

복사된 Object의 속성 중 하나라도 같은 참조를 하고 있게되면 Deep Copy가 된다.

```jsx
import _ from "lodash";

const food = {
  name: "---",
  price: {
    weekDay: 100,
    weekEnd: 150,
  },
};

const pizza = cloneDeep(food);
let str = JSON.stringify(food);
let burger = JSON.parse(str);

pizza.name = "potato";
burger.name = "bulgogi";
```

lodash 모듈에서 제공하는 cloneDeep함수를 사용하는 방법과

JSON.stringify를 이용하여 객체를 문자열로 변환하고, 그 문자열을 다시 객체로 변환하는 방법을 사용하여

Deep Copy를 할 수 있다.

![Untitled](/images/20240109%205.png)

Shallow Copy와는 다르게 pizza만 바뀐 것을 확인할 수 있다.
