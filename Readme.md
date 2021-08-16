https://www.w3schools.com/html/html_forms.asp

# form

- 폼태그는 사용자에게 입력을 받아서, 처리를 위해서 서버로 보내는데 사용합니다.
- 폼태그는 사용자입력을 위한 html 양식을 만드는데 사용합니다.
- 폼태그는 input (text fields, checkboxes, radio, buttons, submit, buttons, etc.) textarea-등 다양한 입력요소를 위한 컨테이너입니다.

---

## form attribute

### action

- 액션속성은 form이 제출될때 수행할 작업을 정의합니다.
- 제출버튼을 클릭하면 form 데이터가 전송될 서버의 파일을 지정합니다.
- action속성이 생량되면 action은 현재페이지로 설정됩니다.

```html
<form action="/action_page.php">
  <label for="fname">First name:</label><br />
  <input type="text" id="fname" name="fname" value="John" /><br />
  <label for="lname">Last name:</label><br />
  <input type="text" id="lname" name="lname" value="Doe" /><br /><br />
  <input type="submit" value="Submit" />
</form>
```

### target

- form data를 제출한후, 응답 받은 내용을 어디에 display할지

### method

- form data를 제출할때 사용할 http 메써드를 지정합니다.
- method="get" - 폼데이터를 url변수로 보냅니다 (기본값)
  - 이름/값의 쌍으로 양식테이터를 url이 추가합니다 (쿼리스트링)
  - get을 사용하여 민감한 데이터를 보내지마세요. url에 노출이됩니다.
  - url의 길이가 2048자로 제한됩니다.
  - 사용자가 결과를 책갈피로 지정하려는 양식제출에 유용합니다. Useful for form submissions where a user wants to bookmark the result
  - google의 쿼리문자열과 같은 비보안데이터에 유용합니다.
- method="post' 폼데이터를 post transaction 으로 보냅니다. (url로 안보이도록)
  - http request의 본문안에 양식데이터를 추가합니다 (url에 표시되지않는다)
  - 데이터의 크기제한이 없으며, 많은양의 데이터를 보내는데 사용할수 있습니다.
  - post가 포함된 form제출은 책갈치로 지정할수 없습니다.

### autocomplete

- 양식에 자동완성기능을 설정할지 여부를 지정합니다.
- 자동완성기능이 켜지면, 브라우저는 사용자가 이전에 입력한 값을 기반으로 자동으로 값을 완성합니다.

```
<form action="/action_page.php" autocomplete="on">
```

### novalidate

- 불리언 속성입니다. (입력시 참, 입력없을시 거짓)
- 해당속성이 존재하는경우, 제출시 폼데이터의 유효성을 검사하지 않아야함을 지정합니다.

```
<form action="/action_page.php" novalidate>
  <label for="email">Enter your email:</label>
  <input type="email" id="email" name="email"><br><br>
  <input type="submit">
</form>
```

more info about form attribute - Click [here](https://www.w3schools.com/html/html_forms_attributes.asp)

---

## form element 종류

### input

- 인풋태그는 type속성에따라서 다양한방식으로 표시됩니다.

### label ( label, input....etc)

- 레이블태그는 각종입력태그들에게 라벨을 붙이기위해 사용한다.
- 레이블로 인풋과묶어주면, 레이블을 클릭했을때도 인풋태그가 활성화된다.
- 스크린리더기는 레이블영역이 포커스되었을때 크게 읽어준다.
- 체크박스처럼 작은영역을 클릭하는데 어려움을 격는사람들을 위해서 사용하면좋다. 레이블을쓰면 텍스트를 클릭해도 인풋영역을 클릭한것과 같은효과를준다.
- input 태그에 id값을 부여하고, label 태그의 for속성으로 연결해주면 labelling이 된다.
- label 태그는 input태그 앞이나 뒤에 위치시키면된다.

```html
<form action="">
  <input type="radio" id="html" name="fav_lang" value="html" />
  <label for="html">html</label>
</form>
```

### select & option - drop down list

- 옵션태그는 선택가능한 옵션을 정의합니다.
- 기본값으로, 첫번째 옵션의 항목이 선택되어져 있습니다.

```html
<label for="cars">Choose a car:</label>
<select id="cars" name="cars">
  <option value="volvo">Volvo</option>
  <option value="saab">Saab</option>
  <option value="fiat">Fiat</option>
  <option value="audi">Audi</option>
</select>
```

- 미리선택된 옵션을 정의하려면, selected 속성을 option에 추가하세요.

```html
<form action="/action_page.php">
  <label for="cars">Choose a car:</label>
  <select id="cars" name="cars">
    <option value="saab">Saab</option>
    <option value="fiat" selected>Fiat</option>
    <option value="audi">Audi</option>
  </select>
  <input type="submit" />
</form>
```

- size속성을 select태그에 추가해서 화면에 표시되는 option의 숫자를 지정할수있습니다.

```html
<form action="/action_page.php">
  <label for="cars">Choose a car:</label>
  <select id="cars" name="cars" size="3">
    <option value="volvo">Volvo</option>
    <option value="saab">Saab</option>
    <option value="fiat">Fiat</option>
    <option value="audi">Audi</option></select
  ><br /><br />
  <input type="submit" />
</form>
```

- multiple 속성을 select태그에 추가하여, 1개이상의 값을 선택하게할수있습니다.
- 쉬프트나, 컨트롤키와함께 option요소를 클릭하여, 여러옵션을 선택할수 있습니다.

```html
<label for="cars">Choose a car:</label>
<select id="cars" name="cars" size="4" multiple>
  <option value="volvo">Volvo</option>
  <option value="saab">Saab</option>
  <option value="fiat">Fiat</option>
  <option value="audi">Audi</option>
</select>
```

### select & optgroup & option

- optgroup 태그는 셀렉트태그에서 관련된 옵션들을 그루핑하는데 사용합니다.
- 옵션목록이 길면, 관련된목록을 그루핑한것은 사용자들이 좀더 쉽게 다룰수 있을것입니다.
  - label 속성을 이용해서 옵션그룹의 이름을 지정합니다.
  - disabled 속성을 이용해서 옵션그룹을 비활성화할수있습니다.

```html
<label for="cars">Choose a car:</label>
<select name="cars" id="cars">
  <optgroup label="Swedish Cars">
    <option value="volvo">Volvo</option>
    <option value="saab">Saab</option>
  </optgroup>
  <optgroup label="German Cars">
    <option value="mercedes">Mercedes</option>
    <option value="audi">Audi</option>
  </optgroup>
</select>
```

### textarea

- 여러줄의 텍스트 입력을 받는데 사용됩니다.
- rows 속성으로 텍스트영역이 표시되는 줄수를 지정합니다.
- cols 속성으로 텍스트영역의 가시적 너비를 지정합니다.

```html
<form action="/action_page.php">
  <textarea name="message" rows="10" cols="20">
The cat was playing in the garden.</textarea
  >
  <br /><br />
  <input type="submit" />
</form>
```

### button

- 항상 타입속성을 지정해야합니다. 브라우저마다 버튼의 기본타입속성이 다를수있습니다

```html
<button type="button" onclick="alert('Hello World!')">Click Me!</button>
```

### fieldset & legend

- fieldset - 폼태그안에서 유사한 input elements를 묶어주고, box의외곽선을 그린다.
- legend - 필드셋으로 그루핑한 form element의 caption(제목을 표시한다)

```html
<form action="">
  <fieldset>
    <legend>this is caption...</legend>
    <label for="fname">first name:</label>
    <input type="text" id="fname" name="fname" />
    <label for="lname">last name:</label>
    <input type="text" id="lname" name="lname" />
    <input type="submit" value="submit" />
  </fieldset>
</form>
```

### input & datalist & option

- 사용자가 데이터를 입력할때 미리 정의된 옵션의 목록을 드랍다운형태로 볼수있습니다.
- 미리정의된 옵션을 선택하기싫으면 직접 작성해서 제출해도 됩니다.
- 데이터리스트에 id값을 부여하고, input태그에 list속성의 값으로 데이터리스트 id값을 지정해서 사용합니다.

```html
<form action="/action_page.php">
  <input list="browsers" />
  <datalist id="browsers">
    <option value="Internet Explorer"></option>
    <option value="Firefox"></option>
    <option value="Chrome"></option>
    <option value="Opera"></option>
    <option value="Safari"></option>
  </datalist>
</form>
```

### output

- 스크립트에서 수행한 결과같은 계산의 결과를 나타냅니다
- for - 계산결과와 계산에 사용된 요소간의 관계를 지정합니다.

```html
<form
  action="/action_page.php"
  oninput="x.value=parseInt(a.value)+parseInt(b.value)"
>
  0
  <input type="range" id="a" name="a" value="50" />
  100 +
  <input type="number" id="b" name="b" value="50" />
  =
  <output name="x" for="a b"></output>
  <br /><br />
  <input type="submit" />
</form>
```

---

## input element 종류

### 입력타입 text, password, email, url, tel, search, number, img

- text

```html
<form>
  <label for="fname">First name:</label><br />
  <input type="text" id="fname" name="fname" /><br />
  <label for="lname">Last name:</label><br />
  <input type="text" id="lname" name="lname" />
</form>
```

- password : 입력필드가 별표또는 원으로 표시된다

```html
<form>
  <label for="username">Username:</label><br />
  <input type="text" id="username" name="username" /><br />
  <label for="pwd">Password:</label><br />
  <input type="password" id="pwd" name="pwd" />
</form>
```

- email
  - 이메일주소입력에 사용
  - 브라우저지원에따라 제출시 이메일주소가 자동검증될수있다.
  - 일부스마트폰은 이메일유형을 인식하고 키보드에 .com을 추가할수 있습니다.

```html
<form>
  <label for="email">Enter your email:</label>
  <input type="email" id="email" name="email" />
</form>
```

- url
  - url 주소를 포함하는입력에 사용됩니다.
  - 브라우저지원에따라 url필드는 제출시 자동 유효성검사할수있습니다.
  - 일부스마트폰은 url형식을 인식하고 url입력과 일치하도록 키보드이 ".com"을 추가합니다

```html
<form>
  <label for="homepage">Add your homepage:</label>
  <input type="url" id="homepage" name="homepage" />
</form>
```

- search
  - 검색필드에 사용이됩니다. (검색필드는 일반텍스트필드처럼 작동합니다.

```html
<form action="/action_page.php">
  <label for="gsearch">Search Google:</label>
  <input type="search" id="gsearch" name="gsearch" />
  <input type="submit" value="Submit" />
</form>
```

- tel
- 전화번호를 포함하는 입력필드에 사용됩니다.

```html
<form>
  <label for="phone">Enter your phone number:</label>
  <input
    type="tel"
    id="phone"
    name="phone"
    pattern="[0-9]{3}-[0-9]{2}-[0-9]{3}"
  />
  <input
    type="tel"
    id="phone"
    name="phone"
    placeholder="010-xxxx-xxxx"
    pattern="010-[0-9]{4}-[0-9]{4}"
    required
  /><br /><br />
</form>
```

- number
  - 숫자를 입력합니다, 허용가능한 숫자를 제한할수있습니다 max, min 속성이용.
  - 인풋필드에서 화살표를 클릭해서 숫자를 선택합니다... (키보드 입력은안됨)

```html
<form>
  <label for="quantity">Quantity (between 1 and 5):</label>
  <input type="number" id="quantity" name="quantity" min="1" max="5" />
</form>
```

### 버튼타입 submit, reset, button

#### submit

- 데이터제출위한 버튼정의, 데이터를 제출하면, 일반적으로 입력데이터를 처리하기위한 스크립트가있는 서버페이지로 이동됩니다.
- value값을 생략하면 기본택스트가 표시됩니다. "제출"

```html
<form action="/action_page.php">
  <label for="fname">First name:</label><br />
  <input type="text" id="fname" name="fname" value="John" /><br />
  <label for="lname">Last name:</label><br />
  <input type="text" id="lname" name="lname" value="Doe" /><br /><br />
  <input type="submit" value="Submit" />
</form>
```

#### reset

- 입력값을 변경한후 reset버튼을 클릭하면 form data가 기본설정값으로 재설정됩니다.

```html
<form action="/action_page.php">
  <label for="fname">First name:</label><br />
  <input type="text" id="fname" name="fname" value="John" /><br />
  <label for="lname">Last name:</label><br />
  <input type="text" id="lname" name="lname" value="Doe" /><br /><br />
  <input type="submit" value="Submit" />
  <input type="reset" />
</form>
```

#### button

```html
<input type="button" onclick="alert('Hello World!')" value="Click Me!" />
```

### 선택타입 - radio, checkbox, range, color, file

#### radio

- 라디오버튼은 선택항목중 하나만 선택가능할수있습니다

```html
<form>
  <input type="radio" id="html" name="fav_language" value="HTML" />
  <label for="html">HTML</label><br />
  <input type="radio" id="css" name="fav_language" value="CSS" />
  <label for="css">CSS</label><br />
  <input type="radio" id="javascript" name="fav_language" value="JavaScript" />
  <label for="javascript">JavaScript</label>
</form>
```

#### checkbox

- 체크박스를통해서 0 혹은 다수의 옵션을 선택할수 있습니다.

```html
<form>
  <input type="checkbox" id="vehicle1" name="vehicle1" value="Bike" />
  <label for="vehicle1"> I have a bike</label><br />
  <input type="checkbox" id="vehicle2" name="vehicle2" value="Car" />
  <label for="vehicle2"> I have a car</label><br />
  <input type="checkbox" id="vehicle3" name="vehicle3" value="Boat" />
  <label for="vehicle3"> I have a boat</label>
</form>
```

#### color

- 색상을 입력해야하는 입력필드에 사용합니다.

```html
<form>
  <label for="favcolor">Select your favorite color:</label>
  <input type="color" id="favcolor" name="favcolor" />
</form>
```

#### file

- 파일선택 - 업로드를 위한 찾아보기 버튼을 정의합니다.

```html
<form action="/action_page.php">
  <label for="myfile">Select a file:</label>
  <input type="file" id="myfile" name="myfile" /><br /><br />
  <input type="submit" value="Submit" />
</form>
```

#### range

- 정확한 값이 중요치않은 숫자를 입력하기위한 컨트롤러를 생성합니다. 기본범위는 0~100입니다. 그러나 max, min, step 속성으로 허용가능한 숫자에 제한을 설정가능합니다.

```html
<form action="/action_page.php" method="get">
  <label for="vol">Volume (between 0 and 50):</label>
  <input type="range" id="vol" name="vol" min="0" max="50" />
  <input type="submit" value="Submit" />
</form>
```

### 날자관련(date, datetime-local, month, week, time)

- 날자관련입력을 포함해야하는경우 사용됩니다.
- 브라우저지원에따라 날자선택기가 입력필드에 나타날수있습니다.
- max 와 min 속성을통해 날자에 제한을 추가할수 있습니다.

#### datetime-local 연 월 일 시간

```html
<form>
  <label for="birthdaytime">Birthday (date and time):</label>
  <input type="datetime-local" id="birthdaytime" name="birthdaytime" />
</form>
```

#### date - 연 월 일

```html
<form>
  <label for="birthday">Birthday:</label>
  <input type="date" id="birthday" name="birthday" />
</form>
```

#### month 년, 월

```html
<form>
  <label for="bdaymonth">Birthday (month and year):</label>
  <input type="month" id="bdaymonth" name="bdaymonth" />
</form>
```

#### week 년, 주

```html
<form action="/action_page.php">
  <label for="week">Select a week:</label>
  <input type="week" id="week" name="week" />
  <input type="submit" value="Submit" />
</form>
```

#### time 시간입력

```html
<form>
  <label for="appt">Select a time:</label>
  <input type="time" id="appt" name="appt" />
</form>
```

### 기타타입 - image, hidden

#### hidden

- 사용자에게 보이지않는 입력필드입니다.
- 웹개발자가, 숨겨진필드사용해서, 사용자가 볼수없고, 수정할수없는 데이터를 포함해서 제출할수있습니다.
- 숨겨진필드는 주로 form을 제출할때, 업데이트해야하는 **데이터베이스 레코드를 저장**하는 용도로 많이 쓰입니다.
- 히든값은 페이지엔 표시되지않지만, 브라우저개발자도구 또는 소스보기기능을 이용해 볼수있고 편집할수있습니다.

```html
<form>
  <label for="fname">First name:</label>
  <input type="text" id="fname" name="fname" /><br /><br />
  <input type="hidden" id="custId" name="custId" value="3487" />
  <input type="submit" value="Submit" />
</form>
```

---

## inpit tag 속성들

- value
  - 입력필드의 기본값지정
- readonly
  - 인풋필드가 읽기전용임을 지정, 변경할수없다.
  - 제출시 함께 제출된다.
- disabled
  - 비활성화(입력불가, 클릭불가), 전송시 제출안됨
  - 비활성화로, 인풋필드가 보이기는하나 회색으로 변한다.
- size
  - 입력필드의 가시적 너비 지정
- checked
  - 체크박스류에서, 페이지로드시 미리 체크되어있을 항목지정
- maxlength
  - 최대길이값 지정
- max
  - 최대값 지정
- min
  - 최소값 지정
- pattern
  - 입력값을 validate 할때, 정규식을 통한 패턴을 제공
- required
  - 필수적으로 입력해야하는 input 필드를 지정
- step
  - 입력필드의 숫자간격(range에서)
- placeholder
  - 입력필드의 예상값, 예상형식에 대한 설명, 힌트제공
- autofocus
  - 불리언타입, 페이지가 로드될때 자동포커스 되도록 설정
- list
  - datalist 태그의 id값을 참조하여, 미리정의된 입력옵션을 제공할때 사용
- autocomplete
  - 자동완성기능

---

## 재지정 태그들

### input form 속성

- 해당 input요소가 어느 form에 속하는지 지정
- form element에 id값을 부여하고, 이값을 참조해서 연결한다.

```html
<form action="/action_page.php" id="form1">
  <label for="fname">First name:</label>
  <input type="text" id="fname" name="fname" /><br /><br />
  <input type="submit" value="Submit" />
</form>

<label for="lname">Last name:</label>
<input type="text" id="lname" name="lname" form="form1" />
```

### input formaction 속성

- 제출될때, 특정 input필드를 처리할 파일의 url을 재지정합니다.

```html
<form action="/action_page.php">
  <label for="fname">First name:</label>
  <input type="text" id="fname" name="fname" /><br /><br />
  <label for="lname">Last name:</label>
  <input type="text" id="lname" name="lname" /><br /><br />
  <input type="submit" value="Submit" />
  <input type="submit" formaction="/action_page2.php" value="Submit as Admin" />
</form>
```

### input formenctype 속성

- 제출할때 특정 인풋필드의 data를 인코딩하는방법을 지정합니다 (post방식의 전송에만 해당)

```html
<form action="/action_page_binary.asp" method="post">
  <label for="fname">First name:</label>
  <input type="text" id="fname" name="fname" /><br /><br />
  <input type="submit" value="Submit" />
  <input
    type="submit"
    formenctype="multipart/form-data"
    value="Submit as Multipart/form-data"
  />
</form>
```

### input formmethod

- form이 제출될때 특정 인풋필드의 데이터를 보내는 http 메써드를 재정의합니다.

```html
<form action="/action_page.php" method="get">
  <label for="fname">First name:</label>
  <input type="text" id="fname" name="fname" /><br /><br />
  <label for="lname">Last name:</label>
  <input type="text" id="lname" name="lname" /><br /><br />
  <input type="submit" value="Submit using GET" />
  <input type="submit" formmethod="post" value="Submit using POST" />
</form>
```

### input formtarget

- 해당속성은 특정 인풋태그의 target 속성을 재정의합니다.

### input formnovalidate

- 해당속성은 특정 인풋태그의 novalidate 속성을 재정의합니다.

# HTTP란?


- 클라이언트와 서버간의 통신을 규약한것입니다.
- HTTP는 클라이언트와 서버간의 요청-응답 프로토콜로 작동합니다.
- 클라이언트가 서버에 HTTP 요청을합니다. 그러면 서버는 클라이언트에게 응답합니다. 응답에는 요청에대한 상태정보(STATUS INFORMATION)가 포함되며 또한 요청된 콘텐츠도 포함될수도 있습니다.

# HTTP METHODS
https://www.w3schools.com/tags/ref_httpmethods.asp

## GET

- 지정된 리소스에서 데이터를 요청하는데 사용됩니다.
- 쿼리문자열(이름/값) 은 GET요청의 URL속에서 전송됩니다.
    - /test/demo_form.php?name1=value1&name2=value2
- GET요청은 캐시할수있습니다.  GET requests can be cached
- GET요청은 브라우저기록에 남습니다.
- GET요청은 북마크에 추가할수있습니다.
- 민감한 데이터는 GET요청하면 안됩니다.
- GET요청은 길이제한이 있습니다.
- GET요청은 데이터 요청에만 사용됩니다 (수정불가)

## POST

- 리소스를 생성, 업데이트위해 서버에 데이터를 보낼때 사용됩니다.
- POST를 통해 서버로 전송된 데이터는 HTTP REQUEST의 HTTP REQUEST BODY안에 저장됩니다.

    POST `/test/demo_form.php HTTP/1.1`

    Host: `w3schools.com`

    `name1=value1&name2=value2`

- POST요청은 캐시되지않습니다.  POST requests are never cached
- 브라우저 기록에 남지않습니다.
- 북마크 할수없습니다.
- 데이터길이에 대한 제한이 없습니다.

## PUT

- PUT은 리소스를 생성/업데이트하기 위해 서버에 데이터를 보내는 데 사용됩니다.
- POST와 PUT의 차이점은 PUT 요청이 멱등적(IDEMPOTENT)이라는 것입니다. 즉, 동일한 PUT 요청을 여러 번 호출하면 항상 동일한 결과가 생성됩니다.
- 반대로 POST 요청을 반복적으로 호출하면 동일한 리소스를 여러 번 생성하는 부작용이 있습니다.

## HEAD

- HEAD는 GET과 거의 동일하지만 응답 본문(response body)이 없습니다.
- 즉, GET방식을쓰면 /users가 사용자 목록을 반환한다면 HEAD방식은 /users는 동일한 요청을 수행하지만 사용자 목록은 반환하지 않습니다.

## DELETE

- DELETE 메소드는 지정된 자원을 삭제합니다.

## OPTIONS

- OPTIONS 메서드는 대상 리소스에 대한 통신 옵션을 설명합니다.


