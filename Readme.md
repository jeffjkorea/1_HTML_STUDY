https://www.w3schools.com/html/html_images.asp

# img

```html
<img src="http://....." alt="tree"  style="width:48px;height:48px;>
```

- src : 주소
- alt : 대체텍스트(이미지가 안나올경우)
- width, height : 이미지의 크기지정

## Common Image Formats

Here are the most common image file types, which are supported in all browsers (Chrome, Edge, Firefox, Safari, Opera):

| Abbreviation | File Format                           | File Extension                   |
| ------------ | ------------------------------------- | -------------------------------- |
| APNG         | Animated Portable Network Graphics    | .apng                            |
| GIF          | Graphics Interchange Format           | .gif                             |
| ICO          | Microsoft Icon                        | .ico, .cur                       |
| JPEG         | Joint Photographic Expert Group image | .jpg, .jpeg, .jfif, .pjpeg, .pjp |
| PNG          | Portable Network Graphics             | .png                             |
| SVG          | Scalable Vector Graphics              | .svg                             |

## background 이미지 (css)

- 배경이미지를 가져오세요
  - `background-image : url('xxxxxx');`
- 배경의 반복을 조절하고싶다면? `background-repeat`
  - 배경이미지가 element보다 작을때는 요소끝에 도착할때까지 기본적으로,가로,세로로 반복됩니다.
  - `background-repeat: no-repeat;`
  - `background-repeat: x-repeat;`
  - `background-repeat: y-repeat;`
- 배경이미지가 원래비율을유지한채, 요소를 꽉 채우고싶다면
  - `background-size: cover`
  - `background-attachment: fixed;`
- 배경이미지가 원래의 비율을 포기한채, 요소를 꽉채우고싶다면, (이미지늘어짐)
  - `background-size: 100% 100%;`
  - `background-attachment: fixed;`

# img & map & area

- 이미지 맵을 통해서, 이미지에 클릭가능한 영역을 생성할수있습니다.
- 이미지 맵의 기본개념은 클릭하는 위치에 따라서 다른 작업을 수행할수 있어야 한다는것이다
- 이미지 맵을 만들려면 이미지와, 클릭가능한영역을 설명하는 HTML코드가 필요하다.

```html
<img src="workplace.jpg" alt="Workplace" usemap="#workmap" />

<map name="workmap">
  <area
    shape="rect"
    coords="34,44,270,350"
    alt="Computer"
    href="computer.htm"
  />
  <area shape="rect" coords="290,172,333,250" alt="Phone" href="phone.htm" />
  <area shape="circle" coords="337,300,44" alt="Coffee" href="coffee.htm" />
</map>
```

## 이미지생성

```html
<img src="workplace.jpg" alt="Workplace" usemap="#workmap" />
```

- 이미지를 만들고, 이미지와 이미지맵을 연결하기위해 usemap 속성을 이용합니다.
- usemap의 값은 해시태그로 시작하고, 이미지맵의 이름을 넣습니다.

## 이미지맵생성

```html
<map name="workmap"> </map>
```

- 이미지 맵을 만드는데 사용되며, name속성에 이름을 적어줍니다. 이름을 통해 이미지와 연결합니다.

## 이미지 영역

- 이미지영역은 클릭가능한 영역을 추가하는것입니다
- 클릭가능한 영역의 모양을 정의해야합니다.
  - `rect` - defines a rectangular region
  - `circle` - defines a circular region
  - `poly` - defines a polygonal region 다각형
  - `default` - defines the entire region 전체지역을 정의
- 또한 클릭가능한 영역을 이미지에 배치할수있도록 좌표를 설정해야합니다.

  - 사각형영역 - 좌측좌표, 우측좌표

    - 사격형영역은, x축과 y축에 대한 좌표가 쌍으로 옵니다. 따라서 좌표 33,44는 왼쪽에서 우측으로 33픽셀, 위에서 아래쪽으로 44픽셀에 위치합니다.
      ```html
      <area shape="rect" coords="34, 44, 270, 350" href="computer.htm" />
      ```

  - 원영역 - 중심좌표, 반지름

    - 원영역은 중심좌표와, 반지름을 통해서 영역을 설정합니다.

    ```html
    <area shape="circle" coords="337, 300, 44" href="coffee.htm" />
    ```

  - 다각형
    - 다각형을 만드는 여러 x,y 좌표점으로 영역을 만듭니다.

## 이미지맵과 자바스크립트

- 요소에 클릭이벤트를 추가해 자바스크립트 기능을 실행합니다.

```html
<map name="workmap">
  <area
    shape="circle"
    coords="337,300,44"
    href="coffee.htm"
    onclick="myFunction()"
  />
</map>

<script>
  function myFunction() {
    alert("You clicked the coffee cup!");
  }
</script>
```

# img & picture & source

- 다양한장치 또는 화면크기에대해 다른그림을 표시할수있다.
- PICTURE는 개발자가 이미지소스를 유연하게 지정할수있도록합니다
- PICTURE는 하나이상의 SOURCE를 포함하며, 각각의 SOURCE는 SRCSET속성을 통해 다른이미지를 참조합니다.
- SOURCE는 이미지가 적합한 시기를 정의하는 미디어 속성이 있습니다.
- 항상 IMG 를 마지막에 추가하세요. IMG는 PICTURE를 지원하지않거나 일치하는 SOURCE MATCH가 없는경우 사용됩니다.

```html
<picture>
  <source media="(min-width: 650px)" srcset="img_food.jpg" />
  <source media="(min-width: 465px)" srcset="img_car.jpg" />
  <img src="img_girl.jpg" />
</picture>
```

## PICTURE를 사용하는 2가지 목적

- 화면이 작거나 기기가 작은경우 다른 이미지 파일을 로드할 필요가 있습니다
- 일부브러우저 또는 장치가 모든 이미지 형식을 지원하지 않을수가 있습니다.
