# 기본 구글지도만들기

- 아리코드는 런던의 중심부에 위치한 구글맵입니다
- div를 통해서 구글지도의 크기를 정합니다.
- 지도속성을 설정하는 함수를 만듭니다.
  - The mapProp variable 는 지도의 속성을 정의합니다
    - center속성은 지도의 중심위치를 지정합니다(위도 및 경도좌표사용) latitude and longitude coordinates
    - 줌속성은 지도의 확대,축소수준을 지정합니다(scale수준)
  - 전달된 매개변수 mapProp을 사용하여, id=googlemap인 div요소내부에 새 지도객체를 만듭니다.
- Google API KEY
  - 구글은 웹사이트가 GOOGLE APIs를 하루에 수천번 무료로 호출할수있도록 허용합니다.
  - Go to [https://developers.google.com/maps/documentation/javascript/get-api-key](https://developers.google.com/maps/documentation/javascript/get-api-key) to learn how to get an API key. API키를 얻으려면 다음주소로 이동해보세요
  - 구글지도는 API를 로드할때 키 매개변수(쿼리스트링)에서 당신의 API키값을 찾을것을 기대합니다.

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>My First Google Map</h1>

    <div id="googleMap" style="width:100%;height:400px;"></div>

    <script>
      function myMap() {
        var mapProp = {
          center: new google.maps.LatLng(51.508742, -0.12085),
          zoom: 5,
        };
        var map = new google.maps.Map(
          document.getElementById("googleMap"),
          mapProp
        );
      }
    </script>

    <script src="https://maps.googleapis.com/maps/api/js?key=YOUR_KEY&callback=myMap"></script>
  </body>
</html>
```

# 구글 OVERLAYS 객체

- 구글오버레이는 위도,경도좌표에 바인딩된 지도 객체입니다.
- 구글지도에는 여러유형의 오버레이가 있습니다.
  - MARKER : 맵상의 단일위치표시, 마커는 사용자정의 아이콘이미지를 표시할수도 있습니다.
  - POLYLINE : 지도에서 일련의 직선들
  - POLYGON : 지도에서 일련의 직선이 있고 모양이 닫힌 모양
  - CIRCLE AND RECTANGLE : 원과 직선
  - INFO WINDOWS - 지도상단의 팝업풍선안에 콘텐츠를 표시합니다.
  - CUSTOM OVERLAY - 맞춤 오버레이

## ADD a marker

- marker 생성자는 마커를 만듭니다. 마커를 표시하려면 position속성을 설정해야합니다.
- setmap() 메써드를 사용하여 지도에 마커를 추가합니다.

```jsx
var marker = new google.maps.Marker({ position: myCenter });

marker.setMap(map);
```

## Animate The Marker

- 아래는 animation 속성을 사용해 마커에 에니메이션을 적용하는 방법을 보여줍니다.

```jsx
var marker = new google.maps.Marker({
  position: myCenter,
  animation: google.maps.Animation.BOUNCE,
});

marker.setMap(map);
```

## Icon instead of Marker

- 기본 마커대신 사용할 이미지, 아이콘을 선택합니다.

```jsx
var marker = new google.maps.Marker({
  position: myCenter,
  icon: "pinkball.png",
});

marker.setMap(map);
```

## polyline

- 폴리라인은 정렬된순서로 일련의 좌표를 통해 그려지는 선입니다.
- 폴리라인은 다음속성을 지원합니다.
  - path - specifies several latitude/longitude coordinates for the line(선에대한 여러 위도,경도좌표)
  - strokeColor - specifies a hexadecimal color for the line (format: "#FFFFFF") 색상지정
  - strokeOpacity - specifies the opacity of the line (a value between 0.0 and 1.0) 선불투명도
  - strokeWeight - specifies the weight of the line's stroke in pixels - 선의 획두께를 픽셀단위지정
  - editable - defines whether the line is editable by users (true/false) - 사용자가 라인을 편집할수있는지 여부정의

```jsx
var myTrip = [stavanger, amsterdam, london];
var flightPath = new google.maps.Polyline({
  path: myTrip,
  strokeColor: "#0000FF",
  strokeOpacity: 0.8,
  strokeWeight: 2,
});
```

## polygon

- 폴리곤은 순서가 지정된 일련의 좌표로 구성된다는 점에서 폴리라인과 유사합니다.
- 그러나 폴리곤은 닫힌 루프 내에서 영역을 정의하도록 설계되었습니다.
- 다각형은 직선으로 이루어지며 모양은 "닫힌" 상태입니다(모든 선이 연결됨).
- 폴리곤은 다음의 속성을 지원합니다
  - path - specifies several LatLng coordinates for the line (first and last coordinate are equal) (latLag좌표지정)
  - strokeColor - specifies a hexadecimal color for the line (format: "#FFFFFF") -선색지정
  - strokeOpacity - specifies the opacity of the line (a value between 0.0 and 1.0) - 선투명도지정
  - strokeWeight - specifies the weight of the line's stroke in pixels - 선두께지정
  - fillColor - specifies a hexadecimal color for the area within the enclosed region (format: "#FFFFFF") - 채울색지정
  - fillOpacity - specifies the opacity of the fill color (a value between 0.0 and 1.0) - 채움투명도지정
  - editable - defines whether the line is editable by users (true/false) - 사용자가 편집여부지정

```jsx
var myTrip = [stavanger, amsterdam, london, stavanger];
var flightPath = new google.maps.Polygon({
  path: myTrip,
  strokeColor: "#0000FF",
  strokeOpacity: 0.8,
  strokeWeight: 2,
  fillColor: "#0000FF",
  fillOpacity: 0.4,
});
```

## 원 circle

- 원은 다음 속성을 지원합니다.
  - center - specifies the google.maps.LatLng of the center of the circle (원의 중심좌표)
  - radius - specifies the radius of the circle, in meters (완의 반지름 미터단위)
  - strokeColor - specifies a hexadecimal color for the line around the circle (format: "#FFFFFF")
  - strokeOpacity - specifies the opacity of the stroke color (a value between 0.0 and 1.0)
  - strokeWeight - specifies the weight of the line's stroke in pixels
  - fillColor - specifies a hexadecimal color for the area within the circle (format: "#FFFFFF")
  - fillOpacity - specifies the opacity of the fill color (a value between 0.0 and 1.0)
  - editable - defines whether the circle is editable by users (true/false)

```jsx
var myCity = new google.maps.Circle({
  center: amsterdam,
  radius: 20000,
  strokeColor: "#0000FF",
  strokeOpacity: 0.8,
  strokeWeight: 2,
  fillColor: "#0000FF",
  fillOpacity: 0.4,
});
```

## info window

- 마커에 대한 일부 텍스트콘텐츠가 있는 정보박스표시

```jsx
var infowindow = new google.maps.InfoWindow({
  content: "Hello World!",
});

infowindow.open(map, marker);
```

# 구글맵 이벤트

## 확대하려면 구글마커를 클릭! Click The Marker to Zoom

- 사용자가 마커를 클릭할 때 확대, 축소하고싶다. 클릭하면 지도를 확대 축소하는 마커에 이벤트핸들러를 연결합니다.

```jsx
// Zoom to 9 when clicking on marker
google.maps.event.addListener(marker, "click", function () {
  map.setZoom(9);
  map.setCenter(marker.getPosition());
});
```

## 마커로 돌아가기 (pan back to marker)

- 여기서, 확대 축소 변경사항을 저장하고 3초후에 지도를 다시 이동합니다.

```jsx
google.maps.event.addListener(marker, "click", function () {
  var pos = map.getZoom();
  map.setZoom(9);
  map.setCenter(marker.getPosition());
  window.setTimeout(function () {
    map.setZoom(pos);
  }, 3000);
});
```

## 마커를 클릭시 infowindow 열기

- 마커를 클릭하면 일부 텍스트가 포함된 정보창이 표시됩니다.

```jsx
var infowindow = new google.maps.InfoWindow({
  content: "Hello World!",
});

google.maps.event.addListener(marker, "click", function () {
  infowindow.open(map, marker);
});
```

## 각 마커에 대한 마커설정 및 infowindow 열기

- 사용자가 지도를 클릭하면 함수를 실행합니다.
- placemaker() 함수는 사용자가 클릭한 위치에 마커를 배치하고 마커의 위도 경도가 포함된 정보창을 표시합니다.

```jsx
google.maps.event.addListener(map, "click", function (event) {
  placeMarker(map, event.latLng);
});

function placeMarker(map, location) {
  var marker = new google.maps.Marker({
    position: location,
    map: map,
  });
  var infowindow = new google.maps.InfoWindow({
    content: "Latitude: " + location.lat() + "<br>Longitude: " + location.lng(),
  });
  infowindow.open(map, marker);
}
```

## 지도 control

## 지도 컨트롤러 종류

- 구글맵 기본 컨트롤 - 표준 구글지도를 표시할때 기본컨트롤세트가 함께 제공됩니다
  - Zoom - displays a slider or "+/-" buttons to control the zoom level of the map(확대축소제어하는 버튼)
  - Pan - displays a pan control for panning the map (지도를 패닝하기위한 팬컨트롤표시)
  - MapType - lets the user toggle between map types (roadmap and satellite) (사용자가 지도유형-로드맵,위성 을 선택가능)
  - Street View - displays a Pegman icon which can be dragged to the map to enable Street View (스트리트뷰활성화위한 지도로 드래그할수있는 팩맨아이콘)
- 기본컨트롤외에도 다음의 컨트롤러기능이 있습니다.
- 지도를 만들때 (mapoption 내부) 또는 setoption()을 호출해 지도의 옵션을 변경할때, 표시할 컨트롤을 지정할수 있습니다.
  - Scale - displays a map scale element 지도축척요소표시
  - Rotate - displays a small circular icon which allows you to rotate maps 지도를 회전할수있는 작은 원형아이콘
  - Overview Map - displays a thumbnail overview map reflecting the current map viewport within a wider area 더 넓은 영역내에서 현재 맵 뷰포트를 반영하는 썸네일 개요맵을 표시

## 기본 컨트롤 비활성화

```jsx
var mapOptions {disableDefaultUI: true}
```

## 모든 컨트롤러 켜기

- 몇몇 컨트롤은 기본값으로 지도에 표기됩니다. 몇몇은 당신이 세팅하지않는한 나타나지않습니다.
- 지도에서 컨트롤 추가, 제거 하는것은 지도옵션객체에서 지정됩니다.
- 컨트롤을 표시하려면 참, 숨기려면 false로설정

```jsx
var mapOptions {
  panControl: true,
  zoomControl: true,
  mapTypeControl: true,
  scaleControl: true,
  streetViewControl: true,
  overviewMapControl: true,
  rotateControl: true
}
```

## 컨트롤 수정하기

- 몇몇 컨트롤은 세부설정이 가능합니다. Several of the map controls are configurable.
- control option필드를 지정하여 control을 수정할수 있습니다.
- zoom 컨트롤러 수정
  - 예를들어 확대 축소컨트를을 수정하기위한 옵션은 zoomControlOptions필드에 지정됩니다.
    - google.maps.ZoomControlStyle.SMALL - displays a mini-zoom control (only + and - buttons) 미니줌컨트롤을 표시합니다.
    - google.maps.ZoomControlStyle.LARGE - displays the standard zoom slider control - 표준 확대,축소 슬라이터 컨트를을 표시합니다.
    - google.maps.ZoomControlStyle.DEFAULT - picks the best zoom control based on device and map size - 기기 및 지도크기에따라 최적의 zoom 컨트롤 선택
  - 컨트롤을 수정하는경우 항상 컨트롤을 먼저 활성화합니다, 트루설정

```jsx
zoomControl: true,
zoomControlOptions: {
    style: google.maps.ZoomControlStyle.SMALL
}
```

- maytype 컨트롤러 수정
  - 컨트롤 수정옵션은 **maptypecontroloptions**필드에서 지정됩니다. 해당필드는 다음이 포함될수있습니다.
    - google.maps.MapTypeControlStyle.HORIZONTAL_BAR - display one button for each map type - 각 지도유형에 대해 하나의 버튼표시
    - google.maps.MapTypeControlStyle.DROPDOWN_MENU - select map type via a dropdown menu - 드랍다운메뉴를 통해 지도유형선택
    - google.maps.MapTypeControlStyle.DEFAULT - displays the "default" behavior (depends on screen size) - 기본동작을 표시합니다(화면크기에따라)
  - **컨트롤 포지션**속성을 사용해 컨트롤 위치를 지정할수도있습니다.

```jsx
mapTypeControl: true,
mapTypeControlOptions: {
  style: google.maps.MapTypeControlStyle.DROPDOWN_MENU
	position: google.maps.ControlPosition.TOP_CENTER
}
```

## 지도타입

- 구글 api에서는 다음지도유형이 지원됩니다.
  - ROADMAP (normal, default 2D map) - 로드맵
  - SATELLITE (photographic map) - 위성맵
  - HYBRID (photographic map + roads and city names)- 사진지도 + 도로및 도시이름
  - TERRAIN (map with mountains, rivers, etc.) - 산, 강등의 지도
- 지도유형은 maptypeid속성을 이용해여 map속성 객체내에서 지정됩니다.

```jsx
var mapOptions = {
  center: new google.maps.LatLng(51.508742, -0.12085),
  zoom: 7,
  mapTypeId: google.maps.MapTypeId.HYBRID,
};
```

- 또는 지도의 setMapTypeip() 메쏘드를 호출해서 지정가능합니다

```jsx
map.setMapTypeId(google.maps.MapTypeId.HYBRID);
```

## 구글지도 45° Perspective View 45도 투시도

- 위성지도유형 및 하이브리드지도유형은 특정위치에서 45도 투시이미지보기를 지원합니다. (높은확대 수준에서만)
- 45' 이미지 보기로 위치를 확대하면 지도가 자동으로 투시보기를 변경합니다.
  - A compass wheel around the Pan control, allowing you to rotate the image(팬컨트롤주위의 나침판휠로 이미지를 회전할수있습니다)
  - A Rotate control between the Pan and Zoom controls, allowing you to rotate the image 90° (이미지를 90도회전할수있는 팬 및 확대컨트롤사이의 회전컨트롤)
  - A toggle control for displaying the 45° perspective view, under the Satellite control/label(위성 제어/라벨 아래에 45도 투시도 표시위한 토글제어)
- 45도 이미지가 있는 지도에서 축소하면 이러한 각 변경하항이 되돌려지고 원래지도가 표시됩니다.
- 다음은 이탈리아 베니스의 두칼레궁전의 45도 투시도를 보여줍니다.

```jsx
var mapOptions = {
  center: myCenter,
  zoom: 18,
  mapTypeId: google.maps.MapTypeId.HYBRID,
};
```

- 45도 투시도 비활성화하기

```jsx
map.setTilt(0);
```

- 나중에 45도 투시도 호라성화하려면 다음을 호출하세요

```jsx
map.setTilt(0);
```

# 구글맵스 레퍼런스

[https://www.w3schools.com/graphics/google_maps_reference.asp](https://www.w3schools.com/graphics/google_maps_reference.asp)
