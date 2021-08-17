https://www.w3schools.com/html/html_media.asp

# 멀티미디어란?

- 사운드, 음악, 영화 및 애니메이션을 말합니다.
- 멀티미디어는 다양한형식으로 제공됩니다.
  - 이미지, 음악, 사운드, 비디오, 레코드, 영화, 애니메이션 등과 같이 듣거나 보거나 할수있는 모든것이 될수있습니다.
- 웹페이지는 다양한 유형과 형식의 멀티미디어 요소가 포함된 경우가 많습니다.

## Common video format

- 다양한 포멧이 있습니다. MP4, webm, ogg형식은 html에서 지원됩니다.
- 유투브에서는 mp4형식을 권장합니다.

## common audio format

- mp3는 압축된 녹음음악에 가장 적합한 형식입니다.
- 웹사이트가 음악에 관한것이라면 mp3가 적합한 선택입니다
- mp3, wav, ogg 오디오만 html표준에서 지원됩니다.

# video & source element

- 웹페이지에 비디오를 표시하는데 사용됩니다.
- **controls 속성**은 재생, 일시중지, 볼륨조절같은 컨터롤을 추가합니다.
- **너비와 폭**을 항상 포함하는것이 좋습니다. 설정되지않으면 동영상이 로드되면서 페이지가 깜빡일수있습니다.
- source element를 사용하면 브라우저에서 선택할수있는 대체비디오 파일을 지정할수있습니다.
- 텍스트는 비디오element를 지원하지않는 브라우저에서 표시됩니다.

```jsx
<video width="320" height="240" controls>
  <source src="movie.mp4" type="video/mp4">
  <source src="movie.ogg" type="video/ogg">
Your browser does not support the video tag.
</video>
```

## video 속성들

- controls - 재생, 일시중지, 볼륨조절같은 컨터롤을 추가합니다.
- autoplay - 동영상을 자동으로 시작합니다.
  - Chromium browsers do not allow autoplay in most cases. However, muted autoplay is always allowed.
- muted - 자동재생후에 음소거를 추가하면 동영상이 자동 재생되지만 소리는 안납니다.

```jsx
<video width="320" height="240" autoplay muted>
  <source src="movie.mp4" type="video/mp4">
  <source src="movie.ogg" type="video/ogg">
Your browser does not support the video tag.
</video>
```

## HTML VIDEO - Media types

| file format | media type |
| ----------- | ---------- |
| mp4         | video/mp4  |
| webm        | video/webm |
| ogg         | video/ogg  |

## Track element - 자막을 설정할수 있습니다.

- 미디어가 재생될때 표시되는 자막, 캡션파일, 또는 텍스트가 포함된 기타파일을 지정하는데 사용합니다.
- Tracks are formatted in WebVTT format (.vtt files). 트랙은 vtt파일 형식으로 지정됩니다.

```jsx
<video width="320" height="240" controls>
  <source src="forrest_gump.mp4" type="video/mp4">
  <source src="forrest_gump.ogg" type="video/ogg">
  <track src="fgsubtitles_en.vtt" kind="subtitles" srclang="en" label="English">
  <track src="fgsubtitles_no.vtt" kind="subtitles" srclang="no" label="Norwegian">
</video>
```

## html video - 메써드, 속성, 이벤트

- html dom은 비디오 엘리먼트에 대한 메쏘드, 속성, 이벤트를 정의합니다.
- 이를 통해 비디오를 로드 , 재생, 일시중지하고, 재생시간과 볼륨을 설정할수 있습니다.
- 비디오가 재생되거나 중지될때 사용할수있는 dom 이벤트도 있습니다.

## html video dom reference

[https://www.w3schools.com/tags/ref_av_dom.asp](https://www.w3schools.com/tags/ref_av_dom.asp)

# audio & source element

- 웹상에서 오디오파일을 재생하는데 사용됩니다.

```jsx
<audio controls>
  <source src="horse.ogg" type="audio/ogg">
  <source src="horse.mp3" type="audio/mpeg">
Your browser does not support the audio element.
</audio>
```

## audio element attribute - autoplay, muted

```jsx
<audio controls autoplay>
  <source src="horse.ogg" type="audio/ogg">
  <source src="horse.mp3" type="audio/mpeg">
Your browser does not support the audio element.
</audio>
```

## html 오디오 - midea types

- mp3 -> audio/mpeg
- ogg -> audio/ogg
- wav -> audio/wav

## html 오디오 - 메써드, 속성, 이벤트

- dom을 사용하면, 오디오를 로드, 재생, 일시중지, 지속시간, 볼륨설정가능
- 재생시작, 일시중지될때 사용가능한 dom 이벤트도 있다.

## html audio dom reference

[https://www.w3schools.com/tags/ref_av_dom.asp](https://www.w3schools.com/tags/ref_av_dom.asp)

# 유투브비디오 넣기

# 동영상을 재생하는 가장쉬운방법은 유투브사용

- 비디오를 웹에맞게 형식변환하는것은 시간도 많이걸리고 번거롭습니다.
- 쉬운방법은 유투브를 통해서 웹페이지에 비디오를 재생시키는 것입니다.

# 유투브 비디오 ID

- 유투브는 동영상을 저장또는 재생할때 ID를 표시합니다. (tgbNymZ7vqY)
- 이 ID를 사용하고 HTML코드에서 동영상을 참조할수있습니다.

# 웹페이지에서 유투브비디오 재생하기

- Upload the video to YouTube (유투브에 비디오 업로드)
- Take a note of the video id (비디오ID기억, )
- Define an `<iframe>` element in your web page (IFRAME을 통해 동영상재생공간만들기)
- Let the `src` attribute point to the video URL (SRC속성을통해 URL로 비디오 연결)
- Use the `width` and `height` attributes to specify the dimension of the player (폭과, 높이를 설정해서 플레이어의 크기지정)
- Add any other parameters to the URL (see below) (URL에 다른 매개변수을 추가합니다.)

```jsx
<iframe
  width="420"
  height="315"
  src="https://www.youtube.com/embed/tgbNymZ7vqY"
></iframe>
```

# OTHER PARAMETERS TO THE URL (속성설정)

- controls=0 플레이어 컨트롤 나타나지않음, constrols=1 플레이어 컨트롤 나타남 (기본값)
- mute=1 after autoplay=1

```jsx
<iframe
  width="420"
  height="315"
  src="https://www.youtube.com/embed/tgbNymZ7vqY?autoplay=1&mute=1"
></iframe>
```

- PLAYLIST
  - playlist parameter에 콤마로 동영상의 ID값을 추가해서 리스트를 만듭니다

```jsx
<iframe
  width="420"
  height="315"
  src="https://www.youtube.com/embed/tgbNymZ7vqY?autoplay=1&mute=1&playlist=tgbNymZ7vqY,tgbNymZ7vqY"
></iframe>
```

- loop=1 (무한반복) LOOP=0 (한번만재생)

```jsx
<iframe
  width="420"
  height="315"
  src="https://www.youtube.com/embed/tgbNymZ7vqY?playlist=tgbNymZ7vqY&loop=1"
></iframe>
```
