# Inside head element

More information Click [here](https://www.w3schools.com/html/html_head.asp)

## What's meta information?

- 메타정보란 html문서에대한 설명을 하는 정보이다.
- 검색엔진을 위한 정보를 제공합니다.

## Character set

- html 문서의 문자인코딩을 지정합니다.

```
<meta charset="utf-8'>
```

## 문서의 meta data 입력

- name속성에 meta data의 종류를기입
- content 속성에 meta data에 대한 설명기입

```
<meta name="application-name" content="creative note">
<meta name="author" content="John Doe">
<meta name="description" content="Free Web tutorials for HTML and CSS">
<meta name="keywords" content="HTML, CSS, JavaScript">
```

- application-name - 애플리케이션 이름
- author - 만든사람
- description - 웹페이지설명. 검색엔진에서 요약자료로 사용될가능성이 높은 자료
- keywords - 검색엔진을 위해 검색 키워드설정

## Setting the viewport

- viewport는 웹페이지에서 사용자가 볼수있는영역입니다. 이것은 디바이스에 따라 다릅니다.
- 각 디바이스에서 쓰는 브라우저의 기본세팅값에 맞추어 자동으로 크기를 조절하는 방법을 제공합니다.
- 뷰포트 속성은 페이지의 크기와 배율을 제어하는 방법을 제공합니다.

```
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

- width=device-width 부분은 장치의 화면의 너비를 따르도록 페이지 너비를 자동설정합니다.
- initial-scale=1.0 부분은 브라우저에서 페이지를 처음 로드할때 초기 확대,축소수준을 설정

## http-equiv Setting

- Content 속성에 적은 값을 http header에 제공합니다.
- http response header를 시뮬레이션 할 수 있습니다.

| value                   | description                                                 | exmaple                                                                           | note                                                                                                                                                                |
| :---------------------- | :---------------------------------------------------------- | :-------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| content-security-policy | Specifies a content policy for the document                 | `<meta http-equiv="content-security-policy" content="default-src 'self'">`        | 문서에대한 콘텐츠정책을 지정합니다                                                                                                                                  |
| content-type            | Specifies the character encoding for the document           | `<meta http-equiv="content-type" content="text/html; charset=UTF-8">`             | 문서의문자인코딩을지정합니다.                                                                                                                                       |
| default-style           | Specified the preferred style sheet to use.                 | `<meta http-equiv="default-style" content="the document's preferred stylesheet">` | 사용할기본스타일시트를 지정합니다. content의 값은 동일한 문서에있는 link요소의 title속성값과 일치하거나, 동일한 문서의 style요소에 있는 title속성과 일치해야합니다. |
| refresh                 | Defines a time interval for the document to refresh itself. | `<meta http-equiv="refresh" content="300">`                                       | 몇초마다 화면을 새로고침할지결정, 사용자로부터 페이지제어권을 빼앗기때문에 매우신중하게사용해야한다.                                                                |

More info - Click [Here](https://www.w3schools.com/tags/att_meta_http_equiv.asp)

## title

- 문서의 타이틀을 설정합니다
- 웹브라우저에서 페이지를 나타내는 탭에서 보여질 title을 입력합니다.

```
<title> Meta information</title>
```

## base

- 문서내의 모든 연관된 URL에 대한 기준URL 및 TARGET설정을 한다.
- href or target 속성중 하나는 필수적으로 입력해야한다.
- 문서에는 하나의 base element만 존재할수있다.

```
<base href="https://www.w3schools.com/" target="_blank">
```

- target attribute

| value     | description                                                             |
| :-------- | :---------------------------------------------------------------------- |
| \_blank   | 새창에엽니다                                                            |
| \_parent  | 부모의 창(상위frame)에 엽니다                                           |
| \_self    | 자신의창(frame)에서 엽니다.                                             |
| \_top     | 화면이 여러프레임으로 이뤄진경우, 모든프레임을 지우고 전체화면에 엽니다 |
| framename | 명명된 iframe에서 문서를 엽니다                                         |

more info - Click [here](https://www.w3schools.com/tags/att_a_target.asp)

## link

- 현재문서와 외부 리소스간의 관계를 설정합니다.
- 주로 외부의 스타일시트를 연결하는데 자주사용합니다.

```
<link rel="stylesheet" href="./style.css">
```

- rel : 연결된문서의 종류
- href : 문서의 위치 or URL

more information Click [here](https://www.w3schools.com/tags/tag_link.asp)
