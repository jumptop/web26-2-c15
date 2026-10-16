# 글자 태그
## 제목과 본문 글자 태그
문서에서 제목은 여섯 가지 제목 글자 태그로 표현함.

제목 글자 태그에서 `h`는 `heading(제목)`을 의미함.

본문 글자를 입력할 때는 `p(paragraph, 단락)`, `br(break, 줄 바꿈)`, `hr(horizontal rule, 수평 줄)` 태그를 사용함.
<table border="1">
    <tr>
        <th colspan="2">태그</th>
        <th>설명</th>
    </tr>
    <tr>
        <td rowspan="6">제목 글자</td>
        <td>h1</td>
        <td>첫 번째로 큰 제목 글자 생성</td>
    </tr>
    <tr>
        <td>h2</td>
        <td>두 번째로 큰 제목 글자 생성</td>
    </td>
    <tr>
        <td>h3</td>
        <td>세 번째로 큰 제목 글자 생성</td>
    </tr>
    <tr>
        <td>h4</td>
        <td>네 번째로 큰 제목 글자 생성</td>
    </tr>
    <tr>
        <td>h5</td>
        <td>다섯 번째로 큰 제목 글자 생성</td>
    </tr>
    <tr>
        <td>h6</td>
        <td>여섯 번째로 큰 제목 글자 생성</td>
    </tr>
        <tr>
        <td rowspan="3">본문 글자</td>
        <td>p</td>
        <td>본문 단락 생성</td>
    </tr>
    <tr>
        <td>br</td>
        <td>줄 바꿈</td>
    </tr>
    <tr>
        <td>hr</td>
        <td>수평 줄 삽입</td>
    </tr>
</table>

## 앵커 태그
HTML(Hyper Text Markup Language)에서 가장 중요한 글자는 하이퍼텍스트를 의미하는 H임.

하이퍼 텍스트는 사용자 선택에 따라 특정 정보로 이동할 수 있도록 조직된 문서를 의미함.

이러한 HTML 페이지가 조직화된 문서 형태가 될 수 있는 이유는 **a**태그 덕분임.

a태그는 anchor를 의미하며, 다른 웹 페이지나 웹 페이지 내부의 특정 위치로 이동할 때 사용함.

### 특정 웹 페이지에 연결하기
```HTML
<a href="https://naver.com">네이버</a>
```

### 웹 페이지 내부에 연결하기(id 속성 추가 사용 필요)
```HTML
<a href="#alpha">Alpha 부분</a>
<h1 id="alpha">Alpha</a> <!-- 여기로 이동 -->
```

## 글자 모양 태그
<table border="1">
    <tr>
        <th>태그</th>
        <th>설명</th>
    </tr>
    <tr>
        <td>b</td>
        <td>굵은 글자<sub>bold</sub></td>
    </tr>
    <tr>
        <td>i</td>
        <td>기울어진 글자<sub>italic</sub></td>
    </tr>
    <tr>
        <td>small</td>
        <td>작은 글자</td>
    </tr>
    <tr>
        <td>sub</td>
        <td>아래 첨자<sub>subscript</sub></td>
    </tr>
    <tr>
        <td>sup</td>
        <td>위 첨자<sub>supscript</sub></td>
    </tr>
        <tr>
        <td>ins</td>
        <td>밑줄 글자<sub>insert</sub></td>
    </tr>
    <tr>
        <td>del</td>
        <td>취소선이 그어진 글자<sub>delete</delete></td>
    </tr>
</table>

# 목록 태그
내비게이션 메뉴를 만들 때 주로 사용하는 목록 태그
<table>
    <tr>
        <th>태그</th>
        <th>설명</th>
    </tr>
    <tr>
        <td>ul</td>
        <td>순서가 없는 목록<sub>unordered list</sub>생성</td>
    </tr>
    <tr>
        <td>ol</td>
        <td>순서가 있는 목록<sub>ordered list</sub>생성</td>
    </tr>
    <tr>
        <td>li</td>
        <td>목록 요소<sub>list item</sub>생성</td>
    </tr>
</table>

- ul의 하위 li로 생성한 리스트 목록
- 순서를 세지 않고 일반 목록을 생성함.

1. ol의 하위 li로 생성한 리스트 목록
2. 순서를 세면서 일반 목록을 생성함.

# 테이블 태그
표를 만들 때에는 테이블 태그를 사용함.
<table border="1">
    <tr>
        <th>태그</th>
        <th>설명</th>
    </tr>
    <tr>
        <td>table</td>
        <td>표 삽입</td>
    </tr>
    <tr>
        <td>tr</td>
        <td>표에 행<sub>table row</sub> 삽입</td>
    </tr>
    <tr>
        <td>th</td>
        <td>표의 제목 셀<sub>table heading</sub> 삽입</td>
    </tr>
    <tr>
        <td>td</td>
        <td>표의 일반 셀<sub>table data</sub> 삽입</td>
    </tr>
</table>

또한 `border` 속성을 사용하여 테이블의 테두리 굵기를 지정할 수 있다.
`th, td` 태그에는 `colspan`을 통해 여러 개의 column을 하나의 column으로 사용하는 것도 가능하고, `rowspan`을 사용하여 여러 행을 하나의 row처럼 사용하는 것도 가능하다.

# 미디어 태그
`image`, `audio`, `video`를 삽입하는 미디어 태그와 그 속성들은 다음과 같다.

## img 태그
img태그는 이미지를 삽입할 수 있는 기능을 가지고 있고 다음과 같은 속성들이 들어간다.
- `src`: 이미지의 경로 지정
- `alt`: 이미지가 없을 때 나오는 글자 지정
- `width`: 이미지의 너비 지정
- `height`: 이미지의 높이 지정

```HTML
<img src="./test/img.png" alt="이미지가 없습니다." width="100", height="100">
```

## audio 및 video 태그
audio 태그는 mp3 파일을, video 태그는 mp4 파일을 나타낼 때 사용한다.

두 태그에 동일하게 들어갈 수 있는 속성들은 다음과 같다.

- `src`: 음악, 비디오 파일의 경로 지정
- `preload`: 음악, 비디오를 준비 중일 때 데이터를 모두 불러올지 여부 결정
- `autoplay`: 음악, 비디오의 자동 재생 여부 지정
- `loop`: 음악, 비디오의 반복 여부 지정
- `controls`: 음악, 비디오 재생 도구 출력 여부 지정

**audio 사용**
```HTML
<audio src="Kalimba.mp3" controls="controls"></audio>
<audio controls="controls">
    <source src="Kalimba.mp3" type="audio/mp3">
</audio>
```

**video 사용**
```HTML
<video controls="controls">
    <source src="Wildlife.mp4" type="video/mp4">
</video>
```
