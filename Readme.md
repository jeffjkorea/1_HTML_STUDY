https://www.w3schools.com/html/html5_canvas.asp

# 웹페이지위에 그래픽을 그릴때 사용한다.

- 자바스크립트를 통해 즉석에서 그래픽을 그리는데 사용됩니다.
- 캔버스는 그래픽을위한 컨테이너일뿐입니다. 실제 그래픽을 그리기위해서는 자바스크립트를 이용해야합니다.
- 캔버스에서 PATH, BOX, CIRCLE, TEXT를 그리는 방법과 이미지추가하는 방법이 여러가지 있습니다.

## CREATE CANVAS

- 캔버스는 HTML 페이지에 직사각형영역입니다.
- 기본값으로 경계선없고, 안에 컨텐츠도 없습니다.
- 항상 ID값을 지정(스크립트에서 참조됨)하고, 너비와 높이를 지정해야합니다.

```html
<canvas
  id="myCanvas"
  width="200"
  height="100"
  style="border:1px solid #000000;"
>
</canvas>
```

## Add javascripts - 그림그리기

- 자바스크립트를 추가해서 그림을 그립니다.
- 첫번째로 캔버스 엘리먼트를 가져와 변수에 담습니다.
- 두번째로, 드로윙객체를 생성합니다. getContext() 메써드는 그리기를 위한 속성과 메써드가 내장된 HTML 객체입니다.
- 세번째로 그리기객체를 이용해 그림을 그립니다.

  - 캔버스 좌표
    - 캔버스는 2차원 그리드입니다. 왼쪽 상단은 좌표가 0,0 입니다.
  - 그리기 객체의 속성 및 메써드

    - 사각형그리기
      - ctx.fillStyle = "#FF0000"; 채울 색상 설정, fillstyle속성은 그라이던트 또는 패턴일수도 있습니다.
      - ctx.fillRect(0, 0, 150, 75); fillRect(x,y,width,height) 채우기스타일로 채워진 사각형을 그립니다.
    - 선그리기
      - moveTo(x,y) - defines the starting point of the line (선의 시작점을 정의합니다)
      - lineTo(x,y) - defines the ending point of the line (선의 끝점을 정의합니다)
      - stroke() - 실제로 선을 그리려면, stroke()와같은 잉크 메써드중 하나를 사용하여야합니다.
    - 원그리기
      - beginPath() - 패스 영역을 선언
      - arc(x,y,r,startangle,endangle) : x,y는 원의 중심점, r은 반지름, 시작각도, 끝나는각도.
        - 각도는 라디안단위로 작성해야합니다 360도 = 2\*pi 라디안
    - 그라디언트
      - 그라디언트생성 - 그라디언트는 색을 채우는데 사용할수있습니다.
        - createLinearGradient(x,y,x1,y1) - creates a linear gradient (그라디언트의 방향지정 x,y에서 → x1,y1으로 가는)
        - createRadialGradient(x,y,r,x1,y1,r1) - creates a radial/circular gradient
      - 정지점추가 - 그라디언트객체는 2개이상의 정지점을 추가해야합니다.
        - addColorStop() - 색상정지점과 색상을 지정합니다. 그라디언트위치는 0과 1사이 일수 있습니다.
        - grd.addColorStop(0, "red"); 위치0(시작점)에서 red로 시작해서
        - grd.addColorStop(1, "white"); 위치1(끝점)에서 흰색으로 끝나는 그라디언트.
      - 그라디언트를 사용하려면 fillstyle 또는 stroke 스타일 속성을 그라디언트로 설정한다음, 모앙(사각,텍스트, 선)을 그립니다.
    - 텍스트 그리기

      - font - 텍스트의 글꼴속성을 정의합니다
      - fillText(text,x,y) 캔버스에 텍스트를 그립니다.
      - strokeText(text,x,y) . 캔버스에 텍스트를 그립니다(채우기없음)
      - 텍스트는 좌측하단을 기준 좌표점으로 사용합니다.

    - 이미지추가
      - drawImage(image,x,y) : 이미지를담은변수, x,y → 이미지삽입좌표(좌측상단을 기준점으로 사용합니다.)

- 그려보기

  - 직선그리기

  ```jsx
  <script>
    var c = document.getElementById("myCanvas"); var ctx = c.getContext("2d");
    ctx.moveTo(0, 0); ctx.lineTo(200, 100); ctx.stroke();
  </script>
  ```

  - 원그리기

  ```jsx
  <script>
    var c = document.getElementById("myCanvas"); var ctx = c.getContext("2d");
    ctx.beginPath(); ctx.arc(95, 50, 40, 0, 2 * Math.PI); ctx.stroke();
  </script>
  ```

  - 텍스트 그리기

  ```jsx
  <script>
    var c = document.getElementById("myCanvas"); var ctx = c.getContext("2d");
    ctx.font = "30px Arial"; ctx.fillText("Hello World", 10, 50);
  </script>
  ```

  - Stroke text

  ```jsx
  <script>
    var c = document.getElementById("myCanvas"); var ctx = c.getContext("2d");
    ctx.font = "30px Arial"; ctx.strokeText("Hello World", 10, 50);
  </script>
  ```

  - 그라디언트 그리기

  ```jsx
  <script>
    var c = document.getElementById("myCanvas"); var ctx = c.getContext("2d");
    // Create gradient var grd = ctx.createLinearGradient(0, 0, 200, 0);
    grd.addColorStop(0, "red"); grd.addColorStop(1, "white"); // Fill with
    gradient ctx.fillStyle = grd; ctx.fillRect(10, 10, 150, 80);
  </script>
  ```

  - draw circular gradient

  ```jsx
  <script>
    var c = document.getElementById("myCanvas"); var ctx = c.getContext("2d");
    // Create gradient var grd = ctx.createRadialGradient(75, 50, 5, 90, 60,
    100); grd.addColorStop(0, "red"); grd.addColorStop(1, "white"); // Fill with
    gradient ctx.fillStyle = grd; ctx.fillRect(10, 10, 150, 80);
  </script>
  ```

  - 이미지 추가하기

  ```jsx
  <script>
    var c = document.getElementById("myCanvas"); var ctx = c.getContext("2d");
    var img = document.getElementById("scream"); ctx.drawImage(img, 10, 10);
  </script>
  ```

# Canvas Object Reference

[https://www.w3schools.com/graphics/canvas_reference.asp](https://www.w3schools.com/graphics/canvas_reference.asp)

- Colors, Styles, and Shadows
- Line Styles
- Rectangles Paths Transformations
- Text
- Image Drawing Pixel Manipulation
- Compositing
- Other

# canvas expample - 움직이는 시계만들기

https://www.w3schools.com/graphics/canvas_clock_start.asp

# Create the Canvas

- 캔버스 Element생성, 캔버스배경은 검정색으로합니다
- 캔버스 객체생성
- 2d 그리기 객체생성
- 반지름 계산
- 그리기 객체를 원점좌표를 캔버스 중앙으로 옮김니다.
- 반지름을 90% 줄입니다.
- 원을 그립니다. 원은 흰색으로 채웁니다.

```html
<canvas id="canvas" width="400" height="400" style="background-color:#333">
</canvas>

<script>
  var canvas = document.getElementById("canvas");
  var ctx = canvas.getContext("2d");

  var radius = canvas.height / 2;
  ctx.translate(radius, radius);
  radius = radius * 0.9;

  function drawClock() {
    ctx.arc(0, 0, radius, 0, 2 * Math.PI);
    ctx.fillStyle = "white";
    ctx.fill();
  }
</script>
```

# CLOCK FACE drawing

- drawFace함수를 생성합니다.
- 흰색 원을 생성합니다
- 원형그라디언트를 생성합니다( 반지름의 95% ~ 105% 영역에 생성합니다.
- 그라디언트의 정지점을 만들어줍니다 (시작점 검정, 가운데 흰색, 끝부분 검정)
- 그라디언트를 드로윙객체의 스트로크스타일로 지정합니다.
- 드로윙객체의 선폭을 반지름의 10%로 설정합니다.
- 원을 그립니다.

```jsx
function drawClock() {
  drawFace(ctx, radius);
}

function drawFace(ctx, radius) {
  var grad;

  ctx.beginPath();
  ctx.arc(0, 0, radius, 0, 2 * Math.PI);
  ctx.fillStyle = "white";
  ctx.fill();

  grad = ctx.createRadialGradient(0, 0, radius * 0.95, 0, 0, radius * 1.05);
  grad.addColorStop(0, "#333");
  grad.addColorStop(0.5, "white");
  grad.addColorStop(1, "#333");

  ctx.strokeStyle = grad;
  ctx.lineWidth = radius * 0.1;
  ctx.stroke();

  ctx.beginPath();
  ctx.arc(0, 0, radius * 0.1, 0, 2 * Math.PI);
  ctx.fillStyle = "#333";
  ctx.fill();
}
```

# 시계에 숫자를 그려봅시다

- 숫자그리기 함수를 생성합니다.
- 그리기객체의 글꼴크기를 반지름의 15% 설정합니다.
- 텍스트정렬을 프린트위치의 center와 base라인으로 설정합니다.
- 12개의숫자의 프린트위치를 계산합니다 (반경 85%지점에서, 30'마다 숫자가 한번씩 표시됩니다)

```jsx
function drawClock() {
  drawFace(ctx, radius);
  drawNumbers(ctx, radius);
}

function drawNumbers(ctx, radius) {
  var ang;
  var num;
  ctx.font = radius * 0.15 + "px arial";

  ctx.textBaseline = "middle";
  ctx.textAlign = "center";

  for (num = 1; num < 13; num++) {
    ang = (num * Math.PI) / 6;
    ctx.rotate(ang);
    ctx.translate(0, -radius * 0.85);
    ctx.rotate(-ang);
    ctx.fillText(num.toString(), 0, 0);
    ctx.rotate(ang);
    ctx.translate(0, radius * 0.85);
    ctx.rotate(-ang);
  }
}
```

# 시계초침 그리기

- 데이트객체를 생성해서, 시간, 분, 초를 변수에 담습니다.
- 시침의 각도를 계산하고 길이와 너비를 그립니다 (길이=반지름의 50%) (너비 반지름의 7%)

```jsx
function drawClock() {
  drawFace(ctx, radius);
  drawNumbers(ctx, radius);
  drawTime(ctx, radius);
}

function drawTime(ctx, radius) {
  var now = new Date();
  var hour = now.getHours();
  var minute = now.getMinutes();
  var second = now.getSeconds();
  //hour
  hour = hour % 12;
  hour =
    (hour * Math.PI) / 6 +
    (minute * Math.PI) / (6 * 60) +
    (second * Math.PI) / (360 * 60);
  drawHand(ctx, hour, radius * 0.5, radius * 0.07);
  //minute
  minute = (minute * Math.PI) / 30 + (second * Math.PI) / (30 * 60);
  drawHand(ctx, minute, radius * 0.8, radius * 0.07);
  // second
  second = (second * Math.PI) / 30;
  drawHand(ctx, second, radius * 0.9, radius * 0.02);
}

function drawHand(ctx, pos, length, width) {
  ctx.beginPath();
  ctx.lineWidth = width;
  ctx.lineCap = "round";
  ctx.moveTo(0, 0);
  ctx.rotate(pos);
  ctx.lineTo(0, -length);
  ctx.stroke();
  ctx.rotate(-pos);
}
```

# 시계작동시키기

- 시계를 작동시키려면 drawclock함수를 intervals(간격)을 설정해 호출하면 됩니다.

```jsx
var canvas = document.getElementById("canvas");
var ctx = canvas.getContext("2d");
var radius = canvas.height / 2;
ctx.translate(radius, radius);
radius = radius * 0.9;

//drawClock();
setInterval(drawClock, 1000);
```

## more example

https://www.w3schools.com/graphics/game_intro.asp
