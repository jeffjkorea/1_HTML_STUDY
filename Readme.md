https://www.w3schools.com/html/html5_draganddrop.asp

# 요소를 드래그 가능하게 만들기

- 우선: 요소를 드래그 가능하게 만들려면 draggable속성을 true로 설정하십시오 .
- `<img draggable="true">`

# 드래그 가능한 요소를 끌때 발생하는 작업지정

- ondragstart속성은 드래그할 데이터를 지정하는 함수 drag(event)를 호출합니다.
- dataTransfer.setData()메서드는 끌어온 데이터의 데이터 유형과 값을 설정
- `function drag(ev) { ev.dataTransfer.setData("text", ev.target.id); }`

# 드롭가능한 위치지정 - ondragover

- ondragover event는 드래그된 데이터를 어디에 떨궈줄수 있는지 지정한다.
- 기본값으로, 데이터나 elememts는 다른 element에 dropped가 가능하지않습니다.
- 이것을 허용하기위해서는 element의 기본처리를 prevent해야합니다.
- `event.preventDefault()`

# Do the drop - ondrop

- 드롭하면 드롭이벤트가 발생합니다.
- ondrop속성은 함수 drop(event)를 호출합니다.

```js
function drop(ev) {
  ev.preventDefault();
  var data = ev.dataTransfer.getData("text");
  ev.target.appendChild(document.getElementById(data));
}
```

- 데이터의 브라우저 기본처리를 방지하세요(기본값은 드롭시 링크로 열러있다)
- dataTransfer.getData() 메써드로 드래그한 데이터를 가져옵니다. 이 메써드는 setData() 메써드에서 동일유형으로 설정된 모든 데이터를 반환합니다.
- 끌어온 데이터는 id값이 drag1인 요소입니다.
- 끌어온 element를 drop한 element에 추가

# full example

```html
<head>
  <script>
    function allowDrop(ev) {
      ev.preventDefault();
    }

    function drag(ev) {
      ev.dataTransfer.setData("text", ev.target.id);
    }

    function drop(ev) {
      ev.preventDefault();
      var data = ev.dataTransfer.getData("text");
      ev.target.appendChild(document.getElementById(data));
    }
  </script>
</head>
<body>
  <div id="div1" ondrop="drop(event)" ondragover="allowDrop(event)"></div>

  <img
    id="drag1"
    src="img_logo.gif"
    draggable="true"
    ondragstart="drag(event)"
    width="336"
    height="69"
  />
</body>
```
