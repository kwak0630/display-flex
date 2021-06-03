# CSS flex

대부분의 사이트는 레이아웃이 수직 구성이며 가장 많이 사용하는 요소들이 기본적으로 dislay:block 개념으로 표시되며 상대적으로 쉽게 구현이 되지만, 수평의 구성일 경우는 상황이 조금 달라집니다.

수평 구성으로 구조를 잡을 경우 Inline-block, float, table, display-cell,flex등이 있습니다.

그 중, Flex(플렉스)란 유연성을 뜻하는데 요소의 크기가 불분명하거나 동적인 경우에도, 각 요소들을 정렬할 수 있는 방법을 제공합니다.



### flex 속성

- 컨테이너에 적용하는 속성
- 아이템에 적용하는 속성

기본적인 html 구조

```
<div class="container">
	<div class="item">item1</div>
	<div class="item">item2</div>
	<div class="item">item3</div>
</div>
```

> 부모 요소인 div.container를 flex container라고 부르고 자식 요소인 div.item을 flex item이라고 부릅니다.



### 컨테이너에 적용하는 속성

#### flex

| 값                             | 의미                                |
| ------------------------------ | ----------------------------------- |
| dispaly: flex                  | block 특성의 flex container를 정의  |
| display: inline-flex           | inline 특성의 flex container를 정의 |
| flex-direction: row            | 아이템들이 행(가로) 방향으로 배치   |
| flex-direction: column         | 아이템들이 열(세로) 방향으로 배치   |
| flex-direction: row-reverse    | 아이템들이 역순으로 가로 배치       |
| flex-direction: column-reverse | 아이템들이 역순으로 세로 배치       |
| flex-wrap: nowrap              | 아이템들을 줄바꿈을 하지 않음       |
| flex-wrap: wrap                | 아이템들이 넘치는 경우 줄바꿈       |
| flex-wrap: wrap-reverse        | 아이템들을 역순으로 줄바꿈 배치     |

#### justify-content

| 값                             | 의미                                         |
| ------------------------------ | -------------------------------------------- |
| justify-content: flex-start    | 아이템들을 시작점으로 정렬                   |
| justify-content: flex-end      | 아이템들을 끝점으로 정렬                     |
| justify-content: flex-center   | 아이템들을 가운데로 정렬                     |
| justify-content: space-between | 아이템들의 사이에 균일한 간격을 만듦         |
| justify-content: space-around  | 아이템들의 둘레에 균일한 간격을 만듦         |
| justify-content: space-evenly  | 아이템들의 사이와 양 끝에 균일한 간격을 만듦 |

#### align-items

| 값                      | 의미                                       |
| ----------------------- | ------------------------------------------ |
| align-items: stretch    | 아이템들이 수직축 방향으로 늘어남          |
| align-items: flex-start | 아이템들을 시작점으로 정렬                 |
| align-items: flex-end   | 아이템들을 끝으로 정렬                     |
| align-items: center     | 아이템들을 가운데로 정렬                   |
| align-items: baseline   | 아이템들을 텍스트 베이스라인 기준으로 정렬 |



#### 아이템에 적용하는 속성

#### flex-basis

아이템의 기본 크기를 설정합니다. flex-direction이 row일 땐 너비, column일 땐 높이. 

| 값                  | 의미                         |
| ------------------- | ---------------------------- |
| flex-basis: auto    | 아이템의 기본 값             |
| flex-basis: 0       |                              |
| flex-basis: 50%     |                              |
| flex-basis: 200px   |                              |
| flex-basis: 10rem   |                              |
| flex-basis: content | 아이템의 기본 점유 크키 설정 |

#### flex-grow

아이템이 flex-basis 의 값보다 커질 수 있는지를 결정하는 속성

| 값           | 의미                    |
| ------------ | ----------------------- |
| flex-grow: 0 | 아이템의 기본값         |
| flex-grow: 1 | 아이템의 비율 1,2,3 ... |

#### flex-shrink

아이템이 flex-basis 의 값보다 작아질 수 있는지를 결정하는 속성

| 값             | 의미            |
| -------------- | --------------- |
| flex-shrink: 1 | 아이템의 기본값 |
| flex-shrink: 0 | 아이템의 고정폭 |

#### flex

flex-grow, flex-shrink, flex-basis를 한번에 쓸 수 있는 축약형 속성

- flex: 1;

  /* flex-grow: 1; flex-shrink: 1; flex-basis: 0% */

- flex: 1 1 auto

  /* flex-grow: 1; flex-shrink: 1; flex-basis: auto; */

- flex: 1 500px

  /* flex-grow: 1; flex-shrink: 1; flex-basis: 500px; */

#### align-self

align-items은 전체 아이템의 수직축 방향 정렬이라면, align-self는 해당 아이템의 수직축 방향 정렬. auto이외에 나머지 값들은 align-items와 동일합니다.

| 값                     | 의미                                       |
| ---------------------- | ------------------------------------------ |
| align-self: auto       | 아이템 수직축 방향 정렬 기본값             |
| align-self: stretch    | 아이템들이 수직축 방향으로 늘어남          |
| align-self: flex-start | 아이템들을 시작점으로 정렬                 |
| align-self: flex-end   | 아이템들을 끝으로 정렬                     |
| align-self: center     | 아이템들을 가운데로 정렬                   |
| align-self: baseline   | 아이템들을 텍스트 베이스라인 기준으로 정렬 |

#### order

각 아이템의 나열 순서를 결정하는 속성

- order: 3; order: 1; order: 2 등등

#### z-index

각 아이템의 우선 순위를 결정하는 속성

기본적으로 z-index 를 설정 안 하면 0 이므로, 1만 설정해도 나머지 아이템보다 위로 설정

- z-index: 1;


TEST url
https://codepen.io/kwak0630/pen/abprBXz?editors=1100
https://codepen.io/kwak0630/pen/xxgNqMQ
