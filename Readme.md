[https://www.w3schools.com/html/html_urlencode.asp](https://www.w3schools.com/html/html_urlencode.asp)

- URL은 웹의 주소입니다.
- url은 도메인주소 또는 인터넷프로토콜(ip) 주소가 될수있습니다.
- 웹브라우저는 url을 통해 웹서버에 페이지요청을합니다.

# syntax

scheme://prefix.domain:port/path/filename

- **scheme** - defines the **type** of Internet service (most common is **http or https**)
- **prefix** - defines a domain **prefix** (default for http is **www**)
- **domain** - defines the Internet **domain name** (like w3schools.com)
- **port** - defines the **port number** at the host (default for http is **80**)
- **path** - defines a **path** at the server (If omitted: the root directory of the site)
- **filename** - defines the name of a document or resource

# url schemes

- http : 암호화안됨, 보통 웹페이지에서 사용됨
- https : 암호화됨, 보안웹페이지에서 사용
- ftp : file transfer protocol 파일 다운, 업로드
- file : 당신의 컴포터에 파일

# url encoding

- url은 ascii문자집합을 사용하여 인테넷을 통해서만 보낼수있습니다.
- 만약 url에 ascii집합 이외의 문자가 포함되있으면 url을 변환해야합니다.
- url 인코딩은 ascii가 아닌 문자를 16진수가 뒤따르는 %로 바꿉니다.
- url은 공백을 포함할수없습니다. url인코딩은 공백을 + 기호 또는 %20으로 바꿉니다.

# url encoding function

- JS, PHP, ASP에 URL 인코딩할때 사용가능한 함수가 있다.
- PHP has the `rawurlencode()` function,
- ASP has the `Server.URLEncode()` function.
- In JavaScript, `encodeURIComponent()` function.
