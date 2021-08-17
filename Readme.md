https://www.w3schools.com/html/html5_webworkers.asp

**웹 작업자는 페이지 성능에 영향을 주지 않고 백그라운드에서 실행되는 JavaScript입니다.**

# 웹 워커란?

- HTML 페이지에서 스크립트를 실행할 때 스크립트가 완료될 때까지 페이지가 응답하지 않습니다.

- 웹 작업자는 페이지 성능에 영향을 주지 않고 다른 스크립트와 독립적으로 백그라운드에서 실행되는 JavaScript입니다.
- 웹 작업자가 백그라운드에서 실행되는 동안 클릭, 항목 선택 등 원하는 작업을 계속할 수 있습니다.

# 웹작업지 브라우저지원확인

```js
if (typeof Worker !== "undefined") {
  // Yes! Web worker support!
  // Some code.....
} else {
  // Sorry! No Web Worker support..
}
```

# 웹작업자파일만들기

- postMessage method, which is used to post a message back to the HTML page.

```js
var i = 0;

function timedCount() {
  i = i + 1;
  postMessage(i);
  setTimeout("timedCount()", 500);
}

timedCount();
```

참고: 일반적으로 웹 작업자는 이러한 간단한 스크립트가 아니라 CPU 집약적인 작업에 사용됩니다.

# 웹작업자 객체만들기

- 이제 html페이지에서 이를 호출해야합니다.
- 작업자가 이미 존재하는지 확인하고, 없으면 새 웹작업자를 만들어봅시다.

```js
if (typeof w == "undefined") {
  w = new Worker("demo_workers.js");
}
```

- 그런다음 웹작업자로부터 메세지를 주고받을수 있습니다 .
- 웹작업자에 onmessage 이벤트 리스너를 추가합니다.
- 웹작업자가 메세지를 게시하면 이벤트 리스너내의 코드가 실행됩니다.
- 웹작업자의 데이터는 event.data에 저장됩니다.

```js
w.onmessage = function (event) {
  document.getElementById("result").innerHTML = event.data;
};
```

# 웹작업자종료

- 웹 작업자 개체가 생성되면 종료될 때까지 (외부 스크립트가 완료된 후에도) 메시지를 계속 수신합니다.
- 웹 작업자를 종료하고 브라우저/컴퓨터 리소스를 해제하려면 다음 `terminate()`방법을 사용하세요 .

```js
w.terminate();
```

# 웹작업자 재사용

- 작업자 변수를 undefined로 설정하면 종료된 후 코드를 재사용할 수 있습니다.
- `w = undefined;`

# 웹작업자와 DOM

웹 작업자는 외부 파일에 있으므로 다음 JavaScript 개체에 액세스할 수 없습니다.

- 창 개체
- 문서 객체
- 상위 개체

# html page의 code 예시

```html
<body>
  <p>Count numbers: <output id="result"></output></p>
  <button onclick="startWorker()">Start Worker</button>
  <button onclick="stopWorker()">Stop Worker</button>

  <script>
    var w;

    function startWorker() {
      if (typeof Worker !== "undefined") {
        if (typeof w == "undefined") {
          w = new Worker("demo_workers.js");
        }
        w.onmessage = function (event) {
          document.getElementById("result").innerHTML = event.data;
        };
      } else {
        document.getElementById("result").innerHTML =
          "Sorry! No Web Worker support.";
      }
    }

    function stopWorker() {
      w.terminate();
      w = undefined;
    }
  </script>
</body>
```
