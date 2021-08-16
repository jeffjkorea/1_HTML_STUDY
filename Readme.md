# text 관련 element

## Text Structure

### h1~6

- 제목글임을 나타냅니다.
- 계층 구조에 맞게 순서대로 작성되어지는것이 좋습니다.
- 원칙적으로 h1요소는 하나의 문서에 한번만 지정하는 것이 좋습니다.
- 여러개의 섹션으로 구성된 문서라면 각 섹션당 한번만 h1을지정하는 것이 좋습니다.
- 이러한 헤딩을 잘 사용하면 검색 엔진의 정보 인식성을 높일 수 있습니다.

### p

- 글의 문단을 나타낸다.

### hr

- 단락들사이에서 주제의 전환을 의미합니다.
- 구분선이 표시됩니다. 스타일시트를이용 다양한 모양으로 대체가능합니다.
- html 페이지의 콘텐츠를 분리(변경, 정의) 하는데 사용됩니다

```html
<h1>This is heading 1</h1>
<p>This is some text.</p>
<hr />
<h2>This is heading 2</h2>
<p>This is some other text.</p>
<hr />
<h2>This is heading 2</h2>
<p>This is some other text.</p>
<hr />
```

### br

- line breaker
- 단순 줄바꿈용 태그이다. 새로운 단락을 시작하지않고 줄바꿈하고싶은경우에 사용

### pre

- 미리형식이 지정된 텍스트를 정의합니다.
- 코드의 공백과 줄바꿈 그대로 유지
- pre태그로 지정된 텍스트는, 보통 고정너비를 가진 폰트(주로courier) 로 표시됩니다.
- 안으로 들여쓰기 됩니다.

```html
<p>
  My Bonnie lies over the ocean. My Bonnie lies over the sea. My Bonnie lies
  over the ocean. Oh, bring back my Bonnie to me.
</p>

<pre>
  My Bonnie lies over the ocean.

  My Bonnie lies over the sea.

  My Bonnie lies over the ocean.

  Oh, bring back my Bonnie to me.
</pre>
```

---

## text formatting (꾸미기 서식)

### b vs strong

- b - bold (단순강조효과)
- strong - Important text(매우중요한 텍스트라는 의미부여, bold효과적용)

### i vs em

- i - italic (대체음성이나 분위기로 텍스트를 정의합니다) , 기술용어, 다른언어의문구, 생각, 선박등의 이름을 나타내는데 사용됩니다.
- em - 이탤릭효과., 강조된 텍스트를 정의합니다. 스크린리더기가 강조해서 발음해준다.

### del vs ins vs u

- del : 텍스트가준데 줄을긋는효과. (문서에서 삭제된 텍스트를 정의합니다- 브라우저는 일반적으로 삭제된 텍스트에 줄을긋습니다)
- ins - 도큐먼트에 삽입된 택스트라는것을 정의해줍니다. (브라우저는 일반적으로 삽입된 텍스트에 밑줄을 긋습니다.
- u - underline 단순 밑줄효과

### mark

- 하이라이트효과 (형광펜색칠) 효과를 준다.

### small vs sub vs sup

- small : 텍스트를 작게 표시해준다
- sub : 아래첨자표시 subscribe text
- sup : 윗첨자표시 superscribe text

### bdo

- 텍스트의 방향을 재설정하는데 사용
- dir -> direction, rtl -> right to left

```html
<bdo dir="rtl">This text will be written from right to left</bdo>
```

---

## text Quotation and Citation

### blockquote & cite

- 다른소스에서 인용된섹션을 정의
- 브라우저는 일반적으로 들여쓰기합니다

```html
<p>Here is a quote from WWF's website:</p>
<blockquote cite="http://www.worldwildlife.org/who/index.html">
  For 50 years, WWF has been protecting the future of nature. The world's
  leading conservation organization, WWF works in 100 countries and is supported
  by 1.2 million members in the United States and close to 5 million globally.
</blockquote>
```

### q

- 짧은 인용문을 정의한다, 브라우저는 ""로 문장을 감쌉니다

```html
<p>
  WWF's goal is to:
  <q>Build a future where people live in harmony with nature.</q>
</p>
```

### abbr

- 텍스트를 생략어(abbreviation)로 지정 (생략어는 한스펠링씩 발음 W.H.O 더블유에이치오)
- 약어를 표시하면 브라우저, 번역시스템 검색엔진에 유용한 정보를 제공할수있습니다.
- title속성을사용하여 약어에 대한 설명을 해보세요.
- 약어로 지정하면, 글하단에 점선표시가됩니다.

```html
<p>
  The <abbr title="World Health Organization">WHO</abbr> was founded in 1948.
</p>
```

### acronym

- 두문자어(initial letter)로 지정 (두문자어는 한단어처럼 발음 FANG 팽 )

```html
The <acronym title="facebook, amazon, netflix, google">FANG</acronym> means IT
giants.
```

### address

- 주소정보를 정의합니다, 이탤릭효과가 적용됩니다.
- 주소정보는 이메일, url, 실제주소, 전화번호, 등등이 될수있습니다.
- 브라우저는 address요소 앞뒤로 항상 줄바꿈을 합니다.

```html
<address>
  Written by John Doe.<br />
  Visit us at:<br />
  Example.com<br />
  Box 564, Disneyland<br />
  USA
</address>
```

### cite

- 창작물(creative work)의 제목을 표시합니다. 이탤릭효과가 적용됩니다.
- 사람의 이름은 작품의 제목이 될순 없습니다.

```html
<p><cite>The Scream</cite> by Edvard Munch. Painted in 1893.</p>
```

### time

- 시간을 표시하는 영역을 정의한다 (웹표준화)

```html
<p>Open from <time>10:00</time> to <time>21:00</time> every weekday.</p>

<p>I have a date on <time datetime="2008-02-14 20:00">Valentines day</time>.</p>
```

---

## 컴퓨터 코드를 의미하는 텍스트

### code

- 컴퓨터코드를 정의하는데 사용됩니다. 모노스페이스폰트로 나옵니다. 추가공백과 줄바꿈을 유지하지 않습니다.
- `<pre>` 요소를 함께쓰면 공백과 줄바꿈을 유지할수 있습니다.

```html
<pre>
<code>
x = 5;
y = 6;
z = x + y;
</code>
</pre>
```

### kbd

- 키보드의 입력을 정의, 폰트는 모노스페이스 폰트입니다

```html
<p>Save the document by pressing <kbd>Ctrl + S</kbd></p>
```

### samp

- 문서내에서 컴퓨터 프로그램의 샘플출력 텍스트를 정의합니다. 모노스페이스폰트로 나옵니다.

```html
<p>Message from my computer:</p>
<p>
  <samp>File not found.<br />Press F1 to continue</samp>
</p>
```

---

## 특수기호

### Entities

- 특수문자를 대체하는 특수한 문자열을 의미합니다.
- 몇몇문자는 html에 예약되어있습니다. 그래서 문자 엔티티로 변경해야합니다
- 문자 엔티티는 다음과같이 표현할수있습니다 **&엔티티 이름** or **&#엔티티번호**
- 문자엔티티 이름형식은 기억하기좋다, 모든브라우저에서 지원하지않을수있다,
- 엔티티번호형식은 브라우저호환이 매우좋다.
- 예시)
  - <는 html태그기호와 겹치기때문에 이것을 텍스트로 표현하기위해서 **&lt** or **&#60** 을 사용해야합니다.
  - **&nbsp** 줄바꿈하지않는 공백 → 브라우저는 줄바꿈할때 공백기준으로 줄바꿈을 하는데, 10 km 같이 연결된정보들은 줄바꿈 되지않는것이 좋습니다. - 브라우저가 공백을 자르지 않도록 특수기호를 사용합니다.

### 발음기호결합 (diacritical marks)

- 발음구별기호는 문자에 추가된 상형문자입니다.
- 여러 발음기호들을 엑센트라고 부릅니다.
- 발음기호에해당하는 코드를 문자 다음에 써주면 혼합할수 있습니다. (**&#768 ~ 771**)

More Info - Click [here](https://www.w3schools.com/html/html_entities.asp)

### symbol Entities

- 많은 수학, 기술, 통화기호는 일반 키보드엔 없습니다.
- 이런 기호를 추가하려면, 기호에 대한 엔티티를 사용할수 있습니다.

More info - click [here](https://www.w3schools.com/charsets/ref_utf_math.asp)

### 그리스어 Entities

- 알파, 베타, 감마,....

more info - click [here](https://www.w3schools.com/charsets/ref_utf_greek.asp)

### 통화, 화살표, 특정모양 entities

More info click -> [currency entity](https://www.w3schools.com/charsets/ref_utf_currency.asp)

More info click -> [arrow entity](https://www.w3schools.com/charsets/ref_utf_arrows.asp)

More info click -> [symbol entity](https://www.w3schools.com/charsets/ref_utf_symbols.asp)

### 이모지

- 이모지는 utf-8문자집합에 있는 문자입니다.
- 이모지는 이미지나 아이콘처럼 보이지만 실제로는 문자입니다.
- utf-8은 세계의 거의 모든 문자와 기호를 포함합니다.
- 많은 UTF-8 문자는 키보드로 입력할 수 없지만,, 항상 숫자(엔티티 번호라고 함)를 사용하여 표시할 수 있습니다.
- 이모지는 문자이기때문에, 복사(컨트롤씨), 표시 및 크기조정이 가능합니다

```html
<p>I will display A B C</p>
<p>I will display &#65; &#66; &#67;</p>
<p style="font-size:48px">&#128512; &#128516; &#128525; &#128151;</p>
```

More info - Cilck [here](https://www.w3schools.com/charsets/ref_emoji.asp)
