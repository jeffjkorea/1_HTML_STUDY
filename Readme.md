# 웹페이지 내에 웹페이지를 표시하는데 사용

- iframe은 inline element입니다.
- syntax
  - `<iframe src="url" title="description"></iframe>`
- 속성들

  - `title`속성은 스크린리더가 iframe의 내용을 읽는데 사용합니다.
  - `frameborder` - 프레임의 경계선의 폭
    - 기본값으로 경계선이 표시됩니다.
    - css를 활용해 경계선을 정하는것이 더 좋은방법입니다.
  - `height, width` - 프레임의 크기
    - 하지만, css를 활용해 크기를 정하는것이 더 좋은방법입니다.
  - `name`
    - iframe의 name값을 참조해서 a링크의 href값으로 사용할수 있습니다.
      - iframe 동영상삽입 - allowfullscreen (동영상 조작버튼들 popup)
  - `allowfullscreen`

    - iframe 동영상삽입시에 동영상 조작버튼들 popup

      ```html
      <iframe
        width="560"
        height="315"
        src="https://www.youtube.com/embed/jSJM9iOiQ1g"
        frameborder="0"
        allowfullscreen
      ></iframe>
      ```

  -`sandbox` - 신뢰할 수 없는 사이트에서 악성코드 같은 것을 포함하고 있다면 삽입된 외부소스에서 악성코드가 실행될 수 있기 때문에 위험하다. 그래서 sandbox라는 속성을 도입해서 자바스크립트가 실행되지 않도록한다.
