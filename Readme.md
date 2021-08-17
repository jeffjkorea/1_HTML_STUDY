# 사용자의 위치를 찾는데 사용합니다.

- 지리적 위치를 얻는데 사용됩니다.
- 이는 개인정보를 침해할수있기에, 사용자승인을 통해 사용가능합니다.
- gps가 있는 스마트폰과 같은 장치에 적합합니다.
- 크롬50부터 이 api는 https와 같은 보안 컨텍스트에서만 작동합니다. 당신의 사이트가 비보안출처(예 http) 에서 호스팅되는경우 사용자위치를 가져오는 요청이 작동하지 않습니다.

# html geolocation 사용하기

- getCurrentPosition() 메써드를 통해서 유저의 위치를 받아옵니다.
- 아래예제는 사용자의 위도와 경도를 반환합니다.

- 로직설명
  - 지오로케이션이 지원되는 브라우저인지 확인.
  - 지원된다면, getCurrentPosition() 메써드를 실행, 아니라면 메세지 출력
  - getCurrentPosition() 메써드가 성공하면 매개변수(showposition)에 지정된 함수에 좌표객체를 반환합니다.
  - showposition() 함수는 위도와 경도를 출력합니다.

```jsx
<!DOCTYPE html>
<html>
<body>

<p>Click the button to get your coordinates.</p>

<button onclick="getLocation()">Try It</button>

<p id="demo"></p>

<script>
var x = document.getElementById("demo");

function getLocation() {
  if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(showPosition);
  } else {
    x.innerHTML = "Geolocation is not supported by this browser.";
  }
}

function showPosition(position) {
  x.innerHTML = "Latitude: " + position.coords.latitude +
  "<br>Longitude: " + position.coords.longitude;
}
</script>

</body>
</html>
```

# 오류 및 거부처리 errors and rejections

- getcurrentposition() 메써드의 두번째 파라미터는 오류를 처리하는데 사용됩니다.
- 사용자의 위치를 가져오지못할경우 실행할 함수를 지정합니다

```jsx
function showError(error) {
  switch (error.code) {
    case error.PERMISSION_DENIED:
      x.innerHTML = "User denied the request for Geolocation.";
      break;
    case error.POSITION_UNAVAILABLE:
      x.innerHTML = "Location information is unavailable.";
      break;
    case error.TIMEOUT:
      x.innerHTML = "The request to get user location timed out.";
      break;
    case error.UNKNOWN_ERROR:
      x.innerHTML = "An unknown error occurred.";
      break;
  }
}
```

# 결과를 지도에 표시하는 방법

- 결과를 구글지도같은 지도에 표시하려면 해당 지도서비스에 엑세스해야합니다.
- 아래예에서 반환된 위도와 경도는 구글지도에서 위치를 표시하는데 사용됩니다(정적이미지사용)

```jsx
function showPosition(position) {
  var latlon = position.coords.latitude + "," + position.coords.longitude;

  var img_url = "https://maps.googleapis.com/maps/api/staticmap?center=
  "+latlon+"&zoom=14&size=400x300&sensor=false&key=YOUR_KEY";

  document.getElementById("mapholder").innerHTML = "<img src='"+img_url+"'>";
}
```

# location-specific information(특정위치의정보)

- 지리적정보는 또한 특정위치에대한 정보를 표시하는데에도 유용합니다.
  - Up-to-date local information 지역최신정보
  - Showing Points-of-interest near the user 사용자 주변의 관심지점표시
  - Turn-by-turn navigation (GPS) 턴바이턴 네비게이션

# getcurrentpositon() 메써드의 리턴데이터

- 해당메써드는 성공시 객체를 반환합니다.
- 위치, 경도, 정확도 속성은 항상 반환됩니다.
- 다른 속성들은 사용가능하다면 반환됩니다.

| Property                | Returns                                                                 |
| ----------------------- | ----------------------------------------------------------------------- |
| coords.latitude         | The latitude as a decimal number (always returned)                      |
| coords.longitude        | The longitude as a decimal number (always returned)                     |
| coords.accuracy         | The accuracy of position (always returned)                              |
| coords.altitude         | The altitude in meters above the mean sea level (returned if available) |
| coords.altitudeAccuracy | The altitude accuracy of position (returned if available)               |
| coords.heading          | The heading as degrees clockwise from North (returned if available)     |
| coords.speed            | The speed in meters per second (returned if available)                  |
| timestamp               | The date/time of the response (returned if available)                   |

# geolocation 객체 - 다른 흥미로운 methods

## watchposition()

- `watchPosition()` - Returns the current position of the user and continues to return updated position as the user moves (like the GPS in a car). -사용자의 현위치를 반환하고 사용자가 이동함에따라 업데이트된 위치를 반환합니다.
- `clearWatch()` - Stops the `watchPosition()` method.
- 이를 사용하려면 정확한 gps장치가 필요합니다.

```jsx
<script>
var x = document.getElementById("demo");
function getLocation() {
  if (navigator.geolocation) {
    navigator.geolocation.watchPosition(showPosition);
  } else {
    x.innerHTML = "Geolocation is not supported by this browser.";
  }
}
function showPosition(position) {
  x.innerHTML = "Latitude: " + position.coords.latitude +
  "<br>Longitude: " + position.coords.longitude;
}
</script>
```
