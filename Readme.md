# WHAT'S PLUG IN

- 플러그인은 브라우저의 표준기능을 확장시키는 외부 컴퓨터 프로그램입니다.
- 플러그인은 다양한 용도로 사용하도록 설계되었습니다.
  - To run Java applets - 자바 애플릿실행
  - To run Microsoft ActiveX controls 액티브엑스 컨트롤실행
  - To display Flash movies 플래쉬동영상 표시
  - To display maps 지도표시
  - To scan for viruses 바이러스검사
  - To verify a bank id 은행아이디확인
- 대부분의 브라우저는 자바 애플릿을 지원하지않습니다.
- 액티브X컨트롤은 더이상 브라우저에서 지원되지않습니다.
- FLASH에 대한 지원되 최신브라우저에서는 해제되었습니다.

# The `<object>` Element

- 모든 브라우저에서 지원됩니다
- 오브젝트 요소는 HTML문서내에 포함된 객체를 정의합니다. (defines an embedded object within an HTML document.)
- 웹페이지에 플러그인을 추가할때 사용하도록 설계되었지만, HTML에 HTML을 포함하는데 사용할수도 있습니다.

```jsx
<object width="100%" height="500px" data="snippet.html"></object>
```

- 이미지를 포함할수도 있습니다

```jsx
<object data="audi.jpeg"></object>
```

# The <embed> Element

- 주요 브라우저에서 지원됩니다.
- HTML문서내에 포함된 객체를 정의하는데 사용합니다. (defines an embedded object within an HTML document.)
- 해당 태그는 닫는태그가 없습니다. 그렇기에 대체텍스트를 표시할수없습니다.

```jsx
<embed src="audi.jpeg">
```

- HTML안에 HTML을 포함하는데 사용할수 있습니다.

```jsx
<embed width="100%" height="500px" src="snippet.html">
```
