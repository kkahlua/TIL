# 12월 28일 Today I Learned

---

# 💯 오늘 배운 내용 중에서 몰랐던 부분만 간략히 정리!

## 🔴 flex box

flex box에 크게 2가지 타입이 존재한다.

1. container : item을 담는 box
2. item : container에 포함되는 요소

## 🔴 flex box - container

![Untitled](/images/20231228.png)

container는 다음과 같은 속성을 사용할 수 있다.

- display
- flex-direction
- flex-wrap
- flex-flow
- justify-content
- align-items
- align-content

## 🔴 justify-content

flex box의 가로축을 정렬하는데 사용된다.

justify-content는 다음과 같은 값을 가질 수 있다.

- flex-start (default value)
- flex-end
- space-between
- space-around
- space-evenly

![왼쪽 시작지점 부터 item들이 출력된다.](/images/20231228%201.png)

왼쪽 시작지점 부터 item들이 출력된다.

![오른쪽 끝 부분부터 item들이 출력된다.](/images/20231228%202.png)

오른쪽 끝 부분부터 item들이 출력된다.

![왼쪽 끝과 오른쪽 끝에 붙어서 출력이 되고 그 사이에 있는 item들은 일정한 간격을 유지해서 출력된다.](/images/20231228%203.png)

왼쪽 끝과 오른쪽 끝에 붙어서 출력이 되고 그 사이에 있는 item들은 일정한 간격을 유지해서 출력된다.

![[여백 item 여백]을 한 묶음으로 동일한 크기를 유지해서 출력된다.](/images/20231228%204.png)

[여백 item 여백]을 한 묶음으로 동일한 크기를 유지해서 출력된다.

![item의 크기와는 별개로 여백의 크기가 동일하게 출력된다.](/images/20231228%205.png)

item의 크기와는 별개로 여백의 크기가 동일하게 출력된다.

## 🔴 align-items

flex box의 세로축을 정렬하는데 사용된다.

align-items는 다음과 같은 값을 가질 수 있다.

- stretch (default value)
- flex-start
- flex-end
- center
- baseline

![item의 높이가 container의 높이 만큼 늘려서 출력된다.](/images/20231228%206.png)

item의 높이가 container의 높이 만큼 늘려서 출력된다.

![item이 container의 위쪽에 붙어서 출력된다.](/images/20231228%207.png)

item이 container의 위쪽에 붙어서 출력된다.

![item이 container의 아래쪽에 붙어서 출력된다.](/images/20231228%208.png)

item이 container의 아래쪽에 붙어서 출력된다.

![item이 container의 y축 기준 가운데에 출력된다.](/images/20231228%209.png)

item이 container의 y축 기준 가운데에 출력된다.

![item의 font-size에 따라서 크기가 다르게 출력된다.](/images/20231228%2010.png)

item의 font-size에 따라서 크기가 다르게 출력된다.

## 🔴 item을 지정하는 속성

flex box에서 item을 지정하는 속성은 다음과 같다.

- flex-grow
- flex-shrink
- flex-basis

![flex-grow의 default value는 0이다.](/images/20231228%2011.png)

flex-grow의 default value는 0이다.

![flex-grow는 container의 여유공간이 있을 때 item이 공간을 채우도록 하는 속성이다.](/images/20231228%2012.png)

flex-grow는 container의 여유공간이 있을 때 item이 공간을 채우도록 하는 속성이다.

![flex-shrink의 default value는 1이다.](/images/20231228%2013.png)

flex-shrink의 default value는 1이다.

![flex-shrink는 container의 여유공간이 없을 때 item의 크기를 조절하는 속성이다. flex-grow와 반대되는 속성이다.](/images/20231228%2014.png)

flex-shrink는 container의 여유공간이 없을 때 item의 크기를 조절하는 속성이다. flex-grow와 반대되는 속성이다.

![flex-basis의 default value는 auto이다.](/images/20231228%2015.png)

flex-basis의 default value는 auto이다.

![flex-basis는 container의 크기가 변경될 때 item의 크기를 일정한 비율로 유지하기 위해 사용되는 속성이다.](/images/20231228%2016.png)

flex-basis는 container의 크기가 변경될 때 item의 크기를 일정한 비율로 유지하기 위해 사용되는 속성이다.

```jsx
.container {
	flex : 1 1 auto;
}
```

위의 코드처럼 묶어서 사용할 수 있다.

## 🔴 gap

![ ](/images/20231228%2017.png)

![ ](/images/20231228%2018.png)

```css
.container {
  gap: 10px;
}
```

space-between, space-around, space-evenly와 다르게

여백에 임의의 고정된 값을 주고싶을 때 사용하는 것 같다.

## 🔴 flex-wrap

![Untitled](/images/20231228%2019.png)

![Untitled](/images/20231228%2020.png)

flex-wrap은 한 줄에 item이 많을 때 줄바꿈 여부를 결정해주는 속성이다.

nowrap의 경우 줄바꿈을 허용하지 않고 container를 뚫고 출력되는 것을 볼 수 있다.

wrap의 경우 줄바꿈을 허용하여 container 안에 item들이 줄바꿈 되어 출력되는 것을 볼 수 있다.
