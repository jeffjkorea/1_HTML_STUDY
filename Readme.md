https://www.w3schools.com/html/html5_webstorage.asp

**HTML 웹 스토리지; 쿠키보다 낫다.**

# HTML 웹 스토리지란

- 웹 스토리지를 사용하면 웹 애플리케이션이 사용자의 브라우저 내에서 로컬로 데이터를 저장할 수 있습니다.

- HTML5 이전에는 애플리케이션 데이터가 모든 서버 요청에 포함된 쿠키에 저장되어야 했습니다.
- 웹 저장소는 더 안전하며 웹 사이트 성능에 영향을 주지 않고 많은 양의 데이터를 로컬에 저장할 수 있습니다.
- 쿠키와 달리 저장 한도가 훨씬 더 크고(최소 5MB) 정보가 서버로 전송되지 않습니다.
- 웹 저장소는 원본(도메인 및 프로토콜당)별로 제공됩니다. 한 출처의 모든 페이지는 동일한 데이터를 저장하고 액세스할 수 있습니다.

# HTML 웹 스토리지 객체

- HTML 웹 저장소는 클라이언트에 데이터를 저장하기 위한 두 가지 개체를 제공합니다.

- `window.localStorage` - 만료 날짜 없이 데이터를 저장합니다.
- `window.sessionStorage` - 한 세션에 대한 데이터를 저장합니다(브라우저 탭을 닫으면 데이터가 손실됨).

# local storage

- localStorage 객체는 만료 날짜 없이 데이터를 저장합니다. 데이터는 브라우저를 닫아도 삭제되지 않으며 다음 날, 주 또는 연도에 사용할 수 있습니다.

## 데이터 저장, 불러오기

```js
// Store
localStorage.setItem("lastname", "Smith");

// Retrieve
document.getElementById("result").innerHTML = localStorage.getItem("lastname");
```

- 다음과 같이 작성도가능합니다

```js
// Store
localStorage.lastname = "Smith";
// Retrieve
document.getElementById("result").innerHTML = localStorage.lastname;
```

## 데이터 지우기

- `localStorage.removeItem("lastname");`

# ssessionStorage 객체

- 사용자가 특정 브라우저 탭을 닫으면 데이터가 삭제됩니다.
