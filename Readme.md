https://www.w3schools.com/html/html5_svg.asp

# SVG란?

- XML형식의 벡터기반 그래픽을 정의합니다.
  - SVG - Scalable Vector Graphic - 확장가능한 벡트그래픽
  - svg는 웹용그래픽을 정의하는데 사용합니다.
  - svg는 w3c권장사항입니다

## svg element

- svg element는 svg그래픽을 위한 콘테이너입니다.
- svg에는 pathes(선), boxes, circles, text, 그래픽이미지를 그리는 다양한 방법이존재합니다.

## 캔버스와 svg의 차이점

- svg는 xml에서 2d그래픽을 설명하기위한 언어입니다.
- 캔버스는 자바스크립트를 사용해 즉성에서 2d그래픽을 그립니다.
- svg는 xml기반이므로 svg dom내의 모든 요소를 사용할수있습니다. 자바스크립트 핸들러를 연결할수 있습니다.
- svg에서 그려진 각각의 모양은 객체로 기억됩니다. svg객체의 속성이 변경되면 브라우저는 자동으로 모양을 다시 렌더링 할수 있습니다.
- 캔버스는 픽셀단위로 렌더링됩니다. 캔버스에서 그래픽은 일단 그려지면 브라우저는 잊어버립니다. 위치를 변경해야하는경우, 전체 장면이 새로 그려져야합니다. (그래픽으로 덮였을수도있는 객체를 포함해서, 모든 장면을 새로 그려야합니다)
- Canvas
  - 픽셀기반이기때문에 해상도에 따라 다르다.
  - 이벤트핸들러에대한 지원이없다.
  - 열악한 텍스트 렌더링기능
  - 결과이미지를 png, jpg로 저장가능하다
  - 그래픽집약적인 게임에 적합하다
- SVG
  - 벡터기반이므로 해상도에 독립적이다.
  - 이벤트핸들러를 지원한다.
  - 렌더링영역이 큰 APP에 적합하다 (구글지도)
  - 복잡한경우(DOM을 많이 사용하면 다 느리다)에 렌더링이 느리다.
  - 게임에 적합하지않다.

# SVG INTRO

## 사전에 알아야할것들

- HTML
- BASIC XML

## WHAT'S SVG

- 확장가능한 벡터그래픽이다. 웹용 벡터기반 그래픽을 정의하는데 사용
- XML형식의 그래픽을 정의합니다.
- SVG파일의 모든요소와 속성에 애니메이션을 적용할수있다.
- SVG는 DOM 및 XSL와 같은 다른 W3C표준과 통합됩니다.

## SVG장점 (다른이미지형식(JPG, GIF)에 비해)

- SVG이미지는 텍스트편집기로 만들고, 편집가능하다.
- SVG이미지는 검색, 인덱싱, 스크립팅, 압축가능하다.
- SVG 이미지는 확장가능하다.
- SVG이미지는 모든해상도에서 고품질이다.
- SVG이미지는 크기조정해도 품질저하되지않는다.
- SVG파일은 순수 XML입니다

# SVG 이미지 만들기

- SVG 이미지생성, 폭과 높이속성은 SVG이미지의 너비와 폭을 정의
- CIRCLE ELEMENT는 원을 그리는데사용
  - CX 및 CY속성은 원중심의 좌표, 설정하지않으면 원중심은 0,0으로 설정됩니다.
  - R은 원의 반지름을 설정합니다.
  - 획 및 획의 너비속성은 윤곽선이 표시되는 방식을 제어합니다. (원의윤곽선을 폭4 녹색테투리로 설정)
  - FILL 속성은 원안의 색상을 나타냅니다.

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>My first SVG</h1>

    <svg width="100" height="100">
      <circle
        cx="50"
        cy="50"
        r="40"
        stroke="green"
        stroke-width="4"
        fill="yellow"
      />
    </svg>
  </body>
</html>
```

## 사각형만들기 rectangle

- 사각형의 폭과 높이를 설정합니다. width, height
- CSS (fill, stroke, stroke-width) 속성으로 채울색상과, 경계선폭, 경계선색상을 정합니다.

```html
<svg width="400" height="110">
  <rect
    width="300"
    height="100"
    style="fill:rgb(0,0,255);stroke-width:3;stroke:rgb(0,0,0)"
  />
</svg>
```

- X,Y 위치좌표설정 (왼쪽, 윗쪽의 마진값으로부터 떨어진 위치설정(PX단위))
- CSS (stroke-opacity, stroke-opacity)속성으로 채운색상의 불투명도(0~1), 경계선의 불투명도(0~1)

```html
<svg width="400" height="180">
  <rect
    x="50"
    y="20"
    width="150"
    height="150"
    style="fill:blue;stroke:pink;stroke-width:5;fill-opacity:0.1;stroke-opacity:0.9"
  />
</svg>
```

- CSS - (opacity ) 속성으로 전체요소의 불투명도를 설정

```html
<svg width="400" height="180">
  <rect
    x="50"
    y="20"
    width="150"
    height="150"
    style="fill:blue;stroke:pink;stroke-width:5;opacity:0.5"
  />
</svg>
```

- rx, ry속성으로 사각형의 모서리를 둥글게 만듭니다.

```html
<svg width="400" height="180">
  <rect
    x="50"
    y="20"
    rx="20"
    ry="20"
    width="150"
    height="150"
    style="fill:red;stroke:black;stroke-width:5;opacity:0.5"
  />
</svg>
```

## 원만들기 circle

- cx와 cy 속성은 원의 중심좌표를 설정합니다.
- r은 원의 반지름을 설정합니다.

```html
<svg height="100" width="100">
  <circle cx="50" cy="50" r="40" stroke="black" stroke-width="3" fill="red" />
</svg>
```

## 타원만들기 ELLIPSE

- 원은 반지름이 동일하지만, 타원은 x,y의 반경이 동일하지 않습니다.
- cx cy는 타원의 중심좌표를 설정합니다
- rx와 ry는 각축방향의 반경을 설정합니다.

```html
<svg height="140" width="500">
  <ellipse
    cx="200"
    cy="80"
    rx="100"
    ry="50"
    style="fill:yellow;stroke:purple;stroke-width:2"
  />
</svg>
```

## 겹치는 타원만들기 ellipse

- 겹치는 3개의 타원만들기
- 코드상에서 제일아래에있는것이 겹치는것중 제일상단에 온다. (왜냐하면 코드순서상 제일마지막에 실행되었기때문이다)

```html
<svg height="150" width="500">
  <ellipse cx="240" cy="100" rx="220" ry="30" style="fill:purple" />
  <ellipse cx="220" cy="70" rx="190" ry="20" style="fill:lime" />
  <ellipse cx="210" cy="45" rx="170" ry="15" style="fill:yellow" />
  Sorry, your browser does not support inline SVG.
</svg>
```

- 2개의 타원을 겹치기

```html
<svg height="100" width="500">
  <ellipse cx="240" cy="50" rx="220" ry="30" style="fill:yellow" />
  <ellipse cx="220" cy="50" rx="190" ry="20" style="fill:white" />
</svg>
```

## 라인긋기 line

- x1, y1 - 선이 출발하는 좌표
- x2, y2 - 선이 끝나는 좌표

```html
<svg height="210" width="500">
  <line
    x1="0"
    y1="0"
    x2="200"
    y2="200"
    style="stroke:rgb(255,0,0);stroke-width:2"
  />
</svg>
```

## 다각형만들기 polygon

- points - 다각형의 각모서리에대한 x,y 좌표를 쌍으로 표시합니다. (3면 다각형)
- 포인트위치를 직선으로 연결하며 다각형을 생성합니다

```html
<svg height="210" width="500">
  <polygon
    points="200,10 250,190 160,210"
    style="fill:lime;stroke:purple;stroke-width:1"
  />
</svg>
```

- 4면 다각형

```html
<svg height="250" width="500">
  <polygon
    points="220,10 300,210 170,250 123,234"
    style="fill:lime;stroke:purple;stroke-width:1"
  />
</svg>
```

- 별모양
- fill-rule : nonzero 속성은 전체영역에 모두 색상을 칠합니다.

```html
<svg height="210" width="500">
  <polygon
    points="100,10 40,198 190,78 10,78 160,198"
    style="fill:lime;stroke:purple;stroke-width:5;fill-rule:nonzero;"
  />
</svg>
```

- 채우기 규칙을 evenodd로 바꾸면 선들이만나서 생긴 내부다각형에만 색칠을합니다.

```html
<svg height="210" width="500">
  <polygon
    points="100,10 40,198 190,78 10,78 160,198"
    style="fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;"
  />
</svg>
```

## 폴리라인만들기 polyline (여러 직선을 연결한 선)

- 포인트 속성은 폴리라인을 그리는데 필요한 x,y좌표를 정의합니다.

```html
<svg height="200" width="500">
  <polyline
    points="20,20 40,25 60,40 80,120 120,140 200,180"
    style="fill:none;stroke:black;stroke-width:3"
  />
</svg>
```

## Path만들기 (경로)

- 열린경로와, 닫힌경로가있다.
- 패쓰데이터에 대해서 다음 명령을 수행가능하다.
  - M = MOVE TO X, Y 이동해라
  - L = LINE TO X,Y 직선을 그려라 (현재위치에서 X,Y만큼의 방향으로)
  - H = HORIZONTAL LINE TO X 수평선을 그어라
  - V = VERTICAL LINE TO Y 수직선을 그어라
  - C = CURVE TO
  - S = SMOOTH CURVE TO
  - Q = quadratic Bézier curve
  - T = smooth quadratic Bézier curveto
  - A = elliptical Arc
  - Z = closepath

```html
<svg height="210" width="400">
  <path d="M150 0 L75 200 L225 200 Z" />
</svg>
```

- AB를 긋는 라인을 만든다.

```html
<svg height="400" width="450">
  <path
    id="lineAB"
    d="M 100 350 l 150 -300"
    stroke="red"
    stroke-width="3"
    fill="none"
  />
  <path
    id="lineBC"
    d="M 250 50 l 150 300"
    stroke="red"
    stroke-width="3"
    fill="none"
  />
  <path d="M 175 200 l 150 0" stroke="green" stroke-width="3" fill="none" />
  <path
    d="M 100 350 q 150 -300 300 0"
    stroke="blue"
    stroke-width="5"
    fill="none"
  />
  <!-- Mark relevant points -->
  <g stroke="black" stroke-width="3" fill="black">
    <circle id="pointA" cx="100" cy="350" r="3" />
    <circle id="pointB" cx="250" cy="50" r="3" />
    <circle id="pointC" cx="400" cy="350" r="3" />
  </g>
  <!-- Label the points -->
  <g
    font-size="30"
    font-family="sans-serif"
    fill="black"
    stroke="none"
    text-anchor="middle"
  >
    <text x="100" y="350" dx="-30">A</text>
    <text x="250" y="50" dy="-10">B</text>
    <text x="400" y="350" dx="30">C</text>
  </g>
  Sorry, your browser does not support inline SVG.
</svg>
```

## text 텍스트만들기

- X,Y 텍스트의 위치
- 텍스트의 기준좌표점은 좌측하단이다.

```html
<svg height="30" width="200">
  <text x="0" y="15" fill="red">I love SVG!</text>
</svg>
```

- TRANSFORM으로 텍스트회전

```html
<svg height="60" width="200">
  <text x="0" y="15" fill="red" transform="rotate(30 20,40)">I love SVG</text>
</svg>
```

- TEXT요소는 TSPAN요소를 이용하여 여러 하위그룹에 정렬할수있습니다.
  - TSPAN에 위치를 지정하지않으면, 한줄에서 이어서 표시됩니다. 다른꾸미기속성들은 모두 상속됩니다.
- TSPAN요소는 개별적속성값 과 위치를 가질수 있습니다.

```html
<svg height="90" width="200">
  <text x="10" y="20" style="fill:red;">
    Several lines:
    <tspan x="10" y="45">First line.</tspan>
    <tspan x="10" y="70">Second line.</tspan>
  </text>
</svg>
```

```html
<svg height="90" width="200">
  <text x="10" y="20" style="fill:red;">
    Several lines:
    <tspan>First line.</tspan>
    <tspan>Second line.</tspan>
  </text>
  Sorry, your browser does not support inline SVG.
</svg>
```

```html
<svg height="90" width="200">
  <text x="10" y="20" style="fill:red;">
    Several lines:
    <tspan x="10" y="45">First line.</tspan>
    <tspan x="40" y="70" style="fill:green;">Second line.</tspan>
  </text>
  Sorry, your browser does not support inline SVG.
</svg>
```

## 텍스트 - 링크로 표현

```html
<svg height="30" width="200" xmlns:xlink="http://www.w3.org/1999/xlink">
  <a xlink:href="https://www.w3schools.com/graphics/" target="_blank">
    <text x="0" y="15" fill="red">I love SVG!</text>
  </a>
</svg>
```

## SVG Stroke 속성들

- 모든 stroke(획) 속성은 모든종류의 선, 텍스트 윤곽선에 사용할수 있습니다.
- stroke

```html
<svg height="80" width="300">
  <g fill="none">
    <path stroke="red" d="M5 20 l215 0" />
    <path stroke="black" d="M5 40 l215 0" />
    <path stroke="blue" d="M5 60 l215 0" />
  </g>
</svg>
```

- stroke-width

```html
<svg height="80" width="300">
  <g fill="none" stroke="black">
    <path stroke-width="2" d="M5 20 l215 0" />
    <path stroke-width="4" d="M5 40 l215 0" />
    <path stroke-width="6" d="M5 60 l215 0" />
  </g>
</svg>
```

- stroke-linecap : 열린path에 대해서 그 끝의 모양을 정의합니다.

```html
<svg height="80" width="300">
  <g fill="none" stroke="black" stroke-width="6">
    <path stroke-linecap="butt" d="M5 20 l215 0" />
    <path stroke-linecap="round" d="M5 40 l215 0" />
    <path stroke-linecap="square" d="M5 60 l215 0" />
  </g>
</svg>
```

- stroke-dasharray : 점선을 만드는데 사용합니다. (선의길의, 공백의길이)

```html
<svg height="80" width="300">
  <g fill="none" stroke="black" stroke-width="4">
    <path stroke-dasharray="5,5" d="M5 20 l215 0" />
    <path stroke-dasharray="10,10" d="M5 40 l215 0" />
    <path stroke-dasharray="20,10,5,5,5,10" d="M5 60 l215 0" />
  </g>
</svg>
```

# SVG 필터

- 필터는 SVG그래픽에 특수효과를 추가하는데 사용됩니다.
- 각요소에 여러 필터를 사용할수 있습니다.

## 가능한 필터 목록

```
- <feBlend> - filter for combining images
- <feColorMatrix> - filter for color transforms
- <feComponentTransfer>
- <feComposite>
- <feConvolveMatrix>
- <feDiffuseLighting>
- <feDisplacementMap>
- <feFlood>
- <feGaussianBlur>
- <feImage>
- <feMerge>
- <feMorphology>
- <feOffset> - filter for drop shadows
- <feSpecularLighting>
- <feTile>
- <feTurbulence>
- <feDistantLight> - filter for lighting
- <fePointLight> - filter for lighting
- <feSpotLight> - filter for lighting
```

## 필터 사용 - 블러효과

- defs - 필터를 정의합니다
  - 필터요소 ID값은 필터의 고유한 이름을 정의합니다. (나중에 적용할 SVG요소에 id값을 참조해서 사용한다)
  - 필터효과는 필터요소이름에 의해 정의됩니다. - `<feGaussianBlur>` element
    - in="SourceGraphic" - 전체요소에 대해서 효과가 생성되도록 정의합니다.
    - stdDeviation="15" - 흐림의 정도를 정의합니다.
  - rect 요소에서 filter속성을 이용해서 정의한 필터효과를 적용합니다.

```html
<svg height="110" width="110">
  <defs>
    <filter id="f1" x="0" y="0">
      <feGaussianBlur in="SourceGraphic" stdDeviation="15" />
    </filter>
  </defs>
  <rect
    width="90"
    height="90"
    stroke="green"
    stroke-width="3"
    fill="yellow"
    filter="url(#f1)"
  />
</svg>
```

## 필터사용 - 쉐도우 효과

- defs : 모든 필터요소는 defs요소내에서 정의됩니다. def요소는 필터같은 특수요소의 정의를 위한 element입니다.
- filter요소는 svg필터를 정의하는데 사용합니다. 필터를 식별하는 필수 id속성을 입력해야합니다.
- feOffset 요소는 그림자효과를 만드는데 사용합니다. svg그래픽이지미 또는 요소를 가져와 xy평면에서 약간 이동하는것입니다.
- 직사각형을 오프셋한 다음, 오프셋이미지위에 원본을 혼합합니다(febelend) . dx,dy요소로 얼만큼 이동할지 정합니다.

```html
<svg height="120" width="120">
  <defs>
    <filter id="f1" x="0" y="0" width="200%" height="200%">
      <feOffset result="offOut" in="SourceGraphic" dx="20" dy="20" />
      <feBlend in="SourceGraphic" in2="offOut" mode="normal" />
    </filter>
  </defs>
  <rect
    width="90"
    height="90"
    stroke="green"
    stroke-width="3"
    fill="yellow"
    filter="url(#f1)"
  />
</svg>
```

- 오프셋이미지를 흐리게할수있습니다. (with `<feGaussianBlur>`)
- `<feGaussianBlur>` element 의 stdDeviation속성은 흐림의 정도롤 결정합니다

```html
<svg height="140" width="140">
  <defs>
    <filter id="f2" x="0" y="0" width="200%" height="200%">
      <feOffset result="offOut" in="SourceGraphic" dx="20" dy="20" />
      <feGaussianBlur result="blurOut" in="offOut" stdDeviation="10" />
      <feBlend in="SourceGraphic" in2="blurOut" mode="normal" />
    </filter>
  </defs>
  <rect
    width="90"
    height="90"
    stroke="green"
    stroke-width="3"
    fill="yellow"
    filter="url(#f2)"
  />
</svg>
```

- 그림자를 검정색으로 만듭니다.
- feOffset 요소의 in속성은 전체 RGBA픽셀대신 흐림효과를 위한 알파채널을 사용하는 SOURCEALPHA로 변경됩니다.

```html
<svg height="140" width="140">
  <defs>
    <filter id="f3" x="0" y="0" width="200%" height="200%">
      <feOffset result="offOut" in="SourceAlpha" dx="20" dy="20" />
      <feGaussianBlur result="blurOut" in="offOut" stdDeviation="10" />
      <feBlend in="SourceGraphic" in2="blurOut" mode="normal" />
    </filter>
  </defs>
  <rect
    width="90"
    height="90"
    stroke="green"
    stroke-width="3"
    fill="yellow"
    filter="url(#f3)"
  />
</svg>
```

- 그림자를 색상으로 처리하기
- FECOLORMATRIX필터는 오프셋이미지의 색상을 검정색에 더가깝게 변환하는데 사용됩니다.
- 행렬(매트릭스)에서 세번나오는 0.2의 값은 모두 빨간색, 녹색, 파란색 채널로 곱해집니다.
- 값을 줄이면 색상이 검정색에 가까워집니다 (검정색은 0)

```html
<svg height="140" width="140">
  <defs>
    <filter id="f4" x="0" y="0" width="200%" height="200%">
      <feOffset result="offOut" in="SourceGraphic" dx="20" dy="20" />
      <feColorMatrix
        result="matrixOut"
        in="offOut"
        type="matrix"
        values="0.2 0 0 0 0 0 0.2 0 0 0 0 0 0.2 0 0 0 0 0 1 0"
      />
      <feGaussianBlur result="blurOut" in="matrixOut" stdDeviation="10" />
      <feBlend in="SourceGraphic" in2="blurOut" mode="normal" />
    </filter>
  </defs>
  <rect
    width="90"
    height="90"
    stroke="green"
    stroke-width="3"
    fill="yellow"
    filter="url(#f4)"
  />
</svg>
```

# SVG 그라디언트

- 그라디언트는 한색상에서 다른색으로 부드럽게 전환되는것

## 선형 LINEAR 그라디언트

- 선형그라디언트는 DEFS 태그안에서 그룹으로 묶어야(nested) 합니다.
- 태그는 정의의 약자이며 특수 요소(예: 그래디언트)에 대한 정의를 포함합니다.
- 선형그라디언트는 수평, 수직, 또는 각도 그라디언트로 정의할수있습니다.

- 수평그라디언트
  - linearGradient -선형그라디언트 태그의 id 속성은 그라디언트의 고유한 이름을 정의합니다.
  - linearGradient -태그의 x1, x2, y1,y2 속성은 그래디언트의 시작 및 끝 위치를 정의합니다. (y축의 변화없이 x축방향으로만 변화하는 수평그라디언트)
  - Stop 태그 - 그라디언트의 색상 범위는 두 가지 이상의 색상으로 구성될 수 있습니다. 각 색상은 stop 태그로 지정이됩니다.
    - offset 속성은 그래디언트 색상이 시작하고 끝나는 위치를 정의하는 데 사용됩니다.
  - 채우기 속성fill은 타원 요소를 그라디언트에 연결합니다.

```html
<svg height="150" width="400">
  <defs>
    <linearGradient id="grad1" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" style="stop-color:rgb(255,255,0);stop-opacity:1" />
      <stop offset="100%" style="stop-color:rgb(255,0,0);stop-opacity:1" />
    </linearGradient>
  </defs>
  <ellipse cx="200" cy="70" rx="85" ry="55" fill="url(#grad1)" />
</svg>
```

- 수직그라디언트
  - x값은 변화가 없고 y값의 변화만 있을때 수직그라디언트가 됩니다

```html
<svg height="150" width="400">
  <defs>
    <linearGradient id="grad2" x1="0%" y1="0%" x2="0%" y2="100%">
      <stop offset="0%" style="stop-color:rgb(255,0,0);stop-opacity:1" />
      <stop offset="100%" style="stop-color:rgb(255,255,0);stop-opacity:1" />
    </linearGradient>
  </defs>
  <ellipse cx="200" cy="70" rx="85" ry="55" fill="url(#grad2)" />
</svg>
```

- 그라디언트 타원 내부에 텍스트를 추가합니다

```html
<svg height="150" width="400">
  <defs>
    <linearGradient id="grad3" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" style="stop-color:rgb(255,255,0);stop-opacity:1" />
      <stop offset="100%" style="stop-color:rgb(255,0,0);stop-opacity:1" />
    </linearGradient>
  </defs>
  <ellipse cx="200" cy="70" rx="85" ry="55" fill="url(#grad3)" />
  <text fill="#ffffff" font-size="45" font-family="Verdana" x="150" y="86">
    SVG
  </text>
</svg>
```

## 원형 RADIAL 그라디언트

- 흰색에서 파란색으로 방사형 그라데이션으로 타원을 정의합니다
- radialGradient 요소에서 cx,cy,r 은 가장바깥쪽원을 정의하고, fx및 fy는 가장안쪽원을 정의합니다

```html
<svg height="150" width="500">
  <defs>
    <radialGradient id="grad1" cx="50%" cy="50%" r="50%" fx="50%" fy="50%">
      <stop offset="0%" style="stop-color:rgb(255,255,255); stop-opacity:0" />
      <stop offset="100%" style="stop-color:rgb(0,0,255);stop-opacity:1" />
    </radialGradient>
  </defs>
  <ellipse cx="200" cy="70" rx="85" ry="55" fill="url(#grad1)" />
</svg>
```

- 흰색에서 파란색으로 방사형 그라디언트로 다른 타원 정의

```html
<svg height="150" width="500">
  <defs>
    <radialGradient id="grad2" cx="20%" cy="30%" r="30%" fx="50%" fy="50%">
      <stop
        offset="0%"
        style="stop-color:rgb(255,255,255);
      stop-opacity:0"
      />
      <stop offset="100%" style="stop-color:rgb(0,0,255);stop-opacity:1" />
    </radialGradient>
  </defs>
  <ellipse cx="200" cy="70" rx="85" ry="55" fill="url(#grad2)" />
</svg>
```

# SVG MORE EXAMPLES

[https://www.w3schools.com/graphics/svg_examples.asp](https://www.w3schools.com/graphics/svg_examples.asp)

# SVG 레퍼런스

[https://www.w3schools.com/graphics/svg_reference.asp](https://www.w3schools.com/graphics/svg_reference.asp)
