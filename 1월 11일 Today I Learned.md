# 1월 11일 Today I Learned

---

# 💯 오늘 배운 내용 중에서 몰랐던 부분만 간략히 정리!

## 🔴 Collection

JS에는 2가지 종류의 Collection이 존재한다.

1. Indexed collections
2. Key based collections

## 🟠 Indexed Collection

Index 값을 기준으로 정렬되어있는 데이터 집합이고,

Array와 TypedArray가 해당된다.

```jsx
let arr = [3, 2, 1];
let typedArray1 = new Int8Array(8);
typedArray1[0] = 32;

console.log(arr[1]); // [2]
console.log(typedArray1); // [32,0,0,0,0,0,0,0]
```

위와 같이 index를 이용해 값을 참조할 수 있다.

## 🟠 Key based collection

Key 값을 기준으로 정렬되어있는 데이터 집합이고,

Map 객체와 Set 객체가 해당된다.

```jsx
let max = new Map();
max.set("id", 0);

const numSet = new Set([1, 2, 3]); // Set(3) {1, 2, 3}
for (const num of numSet) {
  console.log(num); //num이라는 Key value를 통해 값을 순회한다.
}
```

key와 value를 mapping하여 저장하게 된다.

key값을 이용해 값을 참조할 수 있다.

## 🔴 Serialization

다양한 환경 간에 데이터를 주고 받기 위해 직렬화 작업이 필요하다.

보통 JSON파일을 해석하기 위해 사용된다.

serialization (직렬화): Object를 문자열로 변환하는것이다.

deserialization (역직렬화): 문자열을 Object로 변환하는 것이다.

```jsx
JSON.stringify(arr); // 직렬화
JSON.parse(arrStr); // 역직렬화
```

## 🔴 DOM

Document Object Model를 줄여서 DOM이라고 부른다.

DOM은 HTML문서와 상호작용 할 수 있는 interface이다.

DOM은 트리구조를 띄기 때문에 node와 Object로 문서를 표현하고,

부모/ 자식 관계를 가지고 있다.

DOM의 최상위 node는 html이다.

![출처 : [https://poiemaweb.com/js-dom](https://poiemaweb.com/js-dom)](/images/20240111.png)

출처 : [https://poiemaweb.com/js-dom](https://poiemaweb.com/js-dom)

## 🔴 Rendering 과정(HTML)

![출처 : [https://d2.naver.com/helloworld/59361](https://d2.naver.com/helloworld/59361)](/images/20240111%201.png)

출처 : [https://d2.naver.com/helloworld/59361](https://d2.naver.com/helloworld/59361)

1. 브라우저가 html 파일을 로드 한 뒤 parsing한다
2. parsing을 통해 DOM tree를 구축하게 된다.
3. css파일을 load 한 뒤 parsing한다.
4. parsing을 통해 CSSOM tree를 구축한다.
5. DOM과 CSSOM을 결합하여 rendering tree를 형성한다.
6. redering tree에 따라 요소를 구성하고 스타일링하여 rendering을 마친다. (배치,페인팅)

## 🔴 Synchronous / Asynchronous

Synchronous : 요청 이후, 응답을 받아야지 다음 동작이 이루어진다. (직렬적)

Asynchronous : 요청 이후, 응답수락 여부와 상관없이 다음 작업이 동작이 이루어진다. (병렬적)
