# 12월 27일 Today I Learned

---

# 💯 오늘 배운 내용 중에서 몰랐던 부분만 간략히 정리!

## 🔴 margin, padding

- margin과 padding은 박스의 내부와 외부의 여백을 지정하는 css 속성이다.
- 인라인 요소에서 사용할 경우 left,right에만 적용할 수 있다.
- 상, 하, 좌, 우 4방향의 여백을 지정할 수 있다.
- 음수 값도 들어갈 수 있다.

```css
div {
  margin: 10px 20px 30px 40px; /* 위, 오른쪽, 왼쪽,아래 */
  margin: 10px 20px 30px; /* 위, 왼쪽/오른쪽, 아래 */
  padding: 10px 20px; /* 위, 아래 */
  padding: 10px; /* 위, 아래, 왼쪽, 오른쪽 */
}
```

## 🔴 opacity

- 박스의 투명도를 조절하는 css 속성이다.
- default value는 1이고, 0 ~ 1 사이의 값을 적용할 수 있다.
- 0에 가까울 수록 투명해진다.
- 투명도가 적용되면 자식 요소도 투명해진다. (부모의 opacity값이 자식요소에게 상속되는 것은 아니다.)

## 🔴 **문자열과 숫자의 사칙연산 결과**

![Untitled](/images/20231227.png)

```jsx
function solution(s) {
  return +s;
}
```

매개변수 s가 맨 앞만 +또는 -로 구성되어 있고, 그 이후로는 숫자로 구성되어 있는 문자열이라면

앞에 +붙여주면 숫자로 파싱되는 사실을 알고 있어서 위와 같은 방법으로 풀었는데

또 다른 방법이 있는걸 배웠습니다.

```jsx
function solution(s) {
  return s * 1;
  return s / 1;
}
```

문자열과 \*1, /1과 같은 사칙연산을 수행 할 경우

JS는 문자열을 숫자로 파싱하여 계산하게 되기 때문에

위와 같은 답도 가능하다는 사실을 배웠습니다.

문제를 풀면서 가진 궁금한 점은

```jsx
function solution(s) {
  return -s;
}
```

위에 코드는 왜 되지 않는지 입니다.
