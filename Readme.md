Reference Site
https://www.w3schools.com/html/html_links.asp
https://opentutorials.org/course/1058/4786

# anchor element

- 문서를 연결하는데 사용되는 하이퍼링크를 정의합니다.
- 링크내부에는 꼭 텍스트일 필요는 없습니다.
- 링크내부에는 이미지 등 다른 html element가 올수있습니다.
- 링크내부에 버튼이나 링크등 인터렉티브한 요소가 포함되면 안됩니다.

## default style

- 방문치않으면 파란색 밑줄
- 방문하면 보라색 밑줄
- 현재링크 빨간색 밑줄
- 마우스를 올리면 커서가 손모양으로 변합니다.

## href 속성

- 링크할 파일의 위치 or 연결할 url주소

## title 속성

- 링크가 어떤 내용을 담고 있는지를 툴팁으로 보여주는 기능 (링크에 마우스올리면 나오는글)

## target 속성

- 페이지를 어떻게 열것인지 설정
  - \_blank : 새창에 오픈
  - \_parent : 부모창에 엽니다.(상위프레임)
  - \_self : 자신의 창에 엽니다.(현재프레임)
  - \_top : 화면이 여러 프레임으로 이루어져있는 경우 모든 프레임을 지우고 전체 화면에 엽니다.
  - framename : 지정된 iframe에 링크를 엽니다.

More attribute - Click [here](https://www.w3schools.com/tags/tag_a.asp)

---

## 전화번호, 이메일링크

```html
<a href="tel:+4733378901">+47 333 78 901</a>
<a href="mailto:someone@example.com">Send email</a>
```

## 이미지링크

```html
<a href="https://www.w3schools.com">
  <img
    border="0"
    alt="W3Schools"
    src="https://image.flaticon.com/icons/png/512/490/490091.png"
    width="100"
    height="100"
  />
</a>
```

## 버튼링크

```html
<button onclick="document.location='default.asp'">HTML Tutorial</button>
```

---

## URL

- url 은 웹페이지의 주소를 말한다.

### Absolte URL

- 메인주소

### relative URL

- 로컬링크(동일한 웹사이트내에 특정페이지에 대한링크는 https://www 부분은 제외합니다)

```html
<h2>Absolute URLs</h2>
<p><a href="https://www.w3.org/">W3C</a></p>
<p><a href="https://www.google.com/">Google</a></p>

<h2>Relative URLs</h2>
<p><a href="html_images.asp">HTML Images</a></p>
<p><a href="/css/default.asp">CSS Tutorial</a></p>
```

### full url

- . 은 현재폴더를 의미한다.
- ..은 상위 폴더를 의미한다.

```html
<a href="https://www.w3schools.com/html/default.asp">HTML tutorial</a>
<a href="/html/default.asp">HTML tutorial</a>
<a href="default.asp">HTML tutorial</a>
<a href="./default.asp">HTML tutorial</a>
<a href="../html1/default.asp">HTML tutorial</a>
```

### hash url

- element에 id값을 부여하고, a태그의 주소로 #id값을 부여하여, 클릭하면 해당 요소로 이동하는 북마크효과를 줄수 있습니다.

```html
<a href="html_demo.html#C4">Jump to Chapter 4</a>
<a href="#C4">Jump to Chapter 4</a>

<h2 id="C4">Chapter 4</h2>
```
