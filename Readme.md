https://opentutorials.org/course/2039/10954
https://www.w3schools.com/html/html5_semantic_elements.asp

# 의미론적 태그(semantic element)

- 문서의 정보를 보다 잘표현하기위해서 의미에 맞는 태그를 사용해야한다.
- 검색엔진, 시각장애인에게 필요한 스크린리더에게도 좋은 정보로서의 가치부여

## 큰틀의 영역구분

### header

- 화면 상단에 위치하는 사이트나 문서의 전체적인 정보
- 네비게이션을 돕거나 소개를 나타내는 그룹을 표현합니다

### nav

- nav요소는 주요한네비게이션 블럭을 구성하는 섹션

### section

- 문서의 구획들을 정의(어떤 특정역활로 정의하기는 애매한 그룹들을 section으로 묶는다)
- section요소를 사용할 수 있는 예로는 챕터나 탭으로 구분된 대화상자에서 탭된 페이지, 또는 논문의 번호가 매겨진 색션이 될 수 있습니다. 홈페이지에서는 소개, 뉴스 아이템, 연락처등이 섹션으로 분리될 수 있습니다.
- 이치에 맞다면 section요소대신 article요소를 사용할것을 권장합니다.
- 요소가 단순히 스타일링을 위한 목적이나 스크립팅의 편의를 위해서 필요할때 section요소보다는 div요소를 사용할것을 권장

### article

- 문서내에서 독립적인 컨텐츠를 나타냅니다
- article요소는 포럼의 글이 될수도 있고, 잡지나 신문의 기사일 수도 있으며, 블로그의 글이나 사용자가 올린 의견이나 상호작용적인 위젯이나 가젯 또는 다른 어떤 독립적인 아이템등이 될 수 있습니다.

### main

- 문서에서 가장 중심되는 컨텐츠를 정의
- 메인태그 내부의 컨텐츠들은 웹문서가 특별하게 생각합니다. 문서도처에서 반복되는 컨텐츠들은 포함시키면안됩니다.

### aside

- 광고같은 페이지내용과 상관없는 내용, 부수적인 정보들

### footer

- 화면 하단에 위치하는 사이트나 문서의 전체적 정보를 정의
- 주로 저작권 정보나 서비스 제공자 정보등을 나타냅니다.
  주로 사이트 하단에 위치합니다.
- 연락정보는 address요소에 담는것이 적당하며 footer요소안에 포함될 수도 있습니다.

## 기타 semantic

### details & summary

- toggle down 효과
- summary -> details요소는 추가적인 정보를 나타내거나 사용자가 요청하는 정보를 나타냅니다.(토글다운의 제목을 넣는 곳)

```html
<details>
  <summary>Epcot Center</summary>
  <p>
    Epcot is a theme park at Walt Disney World Resort featuring exciting
    attractions, international pavilions, award-winning fireworks and seasonal
    special events.
  </p>
</details>
```

### dailog

- 대화상자처럼, box안에 컨텐츠가 포함된다.
- 대화를 의미하는 tag

```html
<dialog open>This is an open dialog window</dialog>
```

### figure

- 삽화나 다이어그램같은 부가적 요소를 정의

### figcaption

- 삽화,이미지 등을 설명하는 문구

### date

- TEXT가 날자라는 것을 정의 정의

### time

- TEXT가 시간이 라는 것을 정의

### data

```html
<ul>
  <li><data value="21053">Cherry Tomato</data></li>
  <li><data value="21054">Beef Tomato</data></li>
  <li><data value="21055">Snack Tomato</data></li>
</ul>
```
