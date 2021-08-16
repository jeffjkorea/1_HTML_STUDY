today i leaned about ...
**table, tr, th tr td thead tbody tfoot
caption
colgroup, col**

# table

## tr, th, td

- tr : 각각의 테이블행은 tr태그로 정의됩니다 table row
- th : 테이블의 header는 th로 정의됩니다.
  - 기본값으로 bold, 중앙정렬됩니다.
- td : 테이블의 data/cell 은 td로 정의됩니다.
  - 기본값으로 좌측정렬됩니다.
  - td값은 모든html elemet를 포함할수있습니다 (텍스트, 이미지, 리스트, other tables)

```html
<table style="width:100%">
  <tr>
    <th>Firstname</th>
    <th>Lastname</th>
    <th>Age</th>
  </tr>
  <tr>
    <td>Jill</td>
    <td>Smith</td>
    <td>50</td>
  </tr>
  <tr>
    <td>Eve</td>
    <td>Jackson</td>
    <td>94</td>
  </tr>
</table>
```

## semantic - thead, tbody, tfoot

- 테이블 헤더(title)와, 테이블 값(data) , tfoot(합계정보) 들을 구분해 정보로서의 가치를 높힌다.

```html
<table border="2">
  <thead>
    <tr>
      <th>이름</th>
      <th>성별</th>
      <th>주소</th>
      <th>회비</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>최진혁</td>
      <td>남</td>
      <td>청주</td>
      <td>1000</td>
    </tr>
    <tr>
      <td>최유빈</td>
      <td>여</td>
      <td>청주</td>
      <td>500</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>합계</td>
      <td></td>
      <td></td>
      <td>1500</td>
    </tr>
  </tfoot>
</table>
```

## table style

### border

- 표(table)와 데이블셀(th, td) 모두에 테두리를 지정해야합니다

```css
table,
th,
td {
  border: 1px solid black;
}
```

### boder-collapse

- 테두리가 하나의 테두리로 표현하려면 border-collapse 속성을 추가합니다

```css
table {
  border-collapse: collapse;
}
```

### add cell-padding

- 셀패딩은 셀내용과 테두리사이의 공간을 지정합니다.
- 패딩을 지정하지않으면, 패딩값이 없이 표시됩니다.

```css
th,
td {
  padding: 15px;
}
```

### table header - align

- 기본값으로 table header는 중앙정렬됩니다.

```css
th {
  text-align: left;
}
```

### border-spacing - 셀사이의 간격을 지정합니다.

```
table {
  border-spacing: 5px;
}
```
