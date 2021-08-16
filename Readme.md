https://www.w3schools.com/html/html_lists.asp

# list

- 목록을 활용하면 여러 관련항목을 그루핑할수있습니다.

## ul - unordered list

- 리스트의 성격을 정의하는 li의 부모 element입니다
- 글머리기호가 검정색 원으로 표시됩니다.

### list-style-type 속성

- disc -> 불렛마커 (default)
- circle -> 원 마커
- square -> 사각형마커
- none -> 마커없음

```html
<ul style="list-style-type:disc;">
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>
```

https://www.w3schools.com/html/html_lists_unordered.asp

## ol - ordered list

- 리스트의 성격을 정의하는 li의 부모 element입니다
- 글머리기호가 숫자로 표시됩니다.

### type 속성

- type='1' -> 1,2,3,... numbers.(default)
- type='A' -> A,B,C,... uppercase letters
- type='a' -> a,b,c,.... lowercase letters
- type='I' -> I,II, III, .... uppercase roman numbers
- type='i' -> i, ii, iii, .... lowercase roman numbers

```html
<ol type="A">
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ol>
```

### start 속성 : control list count

- 기본값으로부터 list는 1(첫번째)부터 카운팅을 시작합니다.
- 만약 list가 특정숫자(특정 번째)부터 카운팅되게하려면 start속성을 쓰세요

```
<ol start="50">
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ol>
```

https://www.w3schools.com/html/html_lists_ordered.asp

## nested list

- 리스트는 내부에 새로운리스트, 혹은 이미지, 링크등등 다른 html 요소를 포함할수 있습니다.

```
<ul>
  <li>Coffee</li>
  <li>Tea
    <ul>
      <li>Black tea</li>
      <li>Green tea</li>
    </ul>
  </li>
  <li>Milk</li>
</ul>
```

## horizontal list

- 리스트는 다양한방식으로 스타일을 지정가능합니다.
- layout기능(float, flex, grid)등을 통해서 수평 nav바를 만들수 있습니다.

```
<ul style="overflow: hidden; list-style-type: none;">
  <li style="float: left; padding: 10px;"><a href="#home">Home</a></li>
  <li style="float: left;padding: 10px;"><a href="#news">News</a></li>
  <li style="float: left;padding: 10px;"><a href="#contact">Contact</a></li>
  <li style="float: left;padding: 10px;"><a href="#about">About</a></li>
</ul>
```

## description list

- dl : 디스크립션 리스트를 묶는 부모태그입니다
- dt : description title 제목을 지정
- dd : description 내용을 지정합니다. (안쪽으로 들여쓰기됩니다.)

```
<dl>
  <dt>Coffee selection</dt>
  <dd>black hot drink</dd>
  <dt>Milk selection</dt>
  <dd>white cold drink</dd>
</dl>
```
