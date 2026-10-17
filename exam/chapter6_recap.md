# 박스 속성
CSS에서는 각 요소가 박스라는 사각 영역을 생성하고, 이 영역이나 이것을 둘러싼 테두리에 크기, 색상, 위치 등과 관련한 속성을 지정함으로써 스타일을 변경한다.

`margin`, `border`, `padding`, `width`, `height`등이 주요 속성이다.

- `margin`: 테두리와 다른 태그 사이의 테두리 바깥쪽 여백
- `border`: 테두리
- `padding`: 테두리와 글자 사이의 테두리 안쪽 여백, 배경색은 padding 영역까지 적용
- `width`: 글자를 감싸는 영역의 가로 크기
- `height`: 글자를 감싸는 영역의 세로 크기

## 박스 크기와 여백
`width`, `height`속성은 글자를 감싸는 영역 크기를 지정하고, `border` 속성은 테두리 굵기를 지정한다.
`padding` 속성은 테두리와 글자 사이 간격을 지정하고, `margin` 속성은 테두리와 다른 태그 사이 간격을 지정한다.

먼저 아래는 `width`와 `height` 속성을 적용한 예제이다.

```HTML
<head>
    <style>
        div {
            background-color: red;
            width: 100px; height: 100px;
        }
    </style>
</head>
<body>
    <div></div>
</body>
```

이렇게 하면 너비 100px, 높이 100px인 빨간 사각형을 웹 페이지에 생성할 수 있다.
여기에 추가로 `border`와 `margin` 그리고 `padding` 속성을 적용한 예제를 이어서 알아보자

```CSS
div {
    background-color: red;
    width: 100px; height: 100px;
    border: 20px solid black;
    margin: 10px; padding: 30px;
}
```
해당 코드에서 `border: 20px solid black;`을 입력하여 solid(실선)를 검정 색상으로 생성하였고 너비를 20px로 지정하였다.
그리고 `margin: 10px`를 통하여 주변에 있는 요소들러부터 10px 떨어지도록 하였다.
마지막으로 `padding: 30px`를 설정하여 상하좌우로 30px씩 늘어나 100 x 100이던 블록이 160 x 160이 되게 되었다.

또한 태그 전체 크기는 다음 공식으로 구할 수 있다.
- 전체 너비 = width + 2 * (margin + border + padding)
- 전체 높이 = height + 2 * (margin + border + padding)

또한 `margin`과 `padding` 속성은 다음 두 가지 방법으로 상하좌우가 각각 얼마나 늘어날지 정할 수 있다.

### 방법 1. 네 가지 값을 입력하였을 때(상 우 하 좌)
```css
div {
    /* margin, padding: 위쪽 오른쪽 아래쪽 왼쪽 */
    margin: 0 30px 0 30px; /*오른쪽과 왼쪽으로 30px 증가*/
    padding: 30px 30px 30px 30px; /*상하좌우 모두 30px 증가*/
}
```

### 방법 2. 두 가지 값만 입력하였을 때(상하, 우좌)
```css
div {
    /*margin, pading: 위아래 왼오른*/
    margin: 10px 30px; /*상하는 10px, 좌우는 30px 증가*/
    padding: 30px 30px; /*상하좌우 모두 30px 증가*/
}
```

즉 정리해보면, `하나의 값만 입력했을 때 = 상하좌우가 모드 그 값만큼 늘어남`, `두개의 값을 입력했을 때 = 위애라는 첫번째 값, 좌우는 두번째 값만큼 늘어남`, `상 우 하 좌 순서대로 입력했을 때 = 입력한 대로 늘어남`

## 박스 테두리
박스에 테두리를 넣을 때는 굵기, 형태, 색상에 해당하는 속성을 사용해야 한다.
**테두리 굵기는 border-width 속성을 사용하고, 테두리 형태는 border-style속성을 사용하며, 테두리 색상은 border-color 속성을 사용한다.**

### 기본 테두리 만들기
이 세가지 속성을 한번에 사용하는 방법은 `border`속성을 적용하는 방법이 존재한다.
`border`에 속성을 적용하는 방법과 순서는, `border: thick dashed black` 처럼 적용이 가능하며 순서대로 `border-width`, `border-style`, `border-color`를 뜻한다.

### 둥근 테두리 만들기
둥근 테두리는 해당 속성으로 `border-radius`속성을 적용하여 가능하고, 크기 단위 4가지를 순차적으로 입력하면 각 테두리에 둥글기가 적용된다.
`border-radius: 50px 40px 30px 20px;`로 입력하면, 순서대로 왼쪽 위, 오른쪽 위, 오른쪽 아래, 왼쪽 아래 순서대로 둥글어진다.

만약 **테두리의 전체가 둥글어지는 것을 원한다면** `border-radius: 20px;`처럼 하나의 값만 입력하는 방법도 존재한다.

## 가시 속성
가시 속성은 태그가 화면에 보이는 방식을 지정하며, 대표적으로 `display` 속성이 존재한다.
대표적인 `display`속성에 입력할 수 있는 키워드의 예제로는 `none: 보이지 않음`, `block: 블록 박스 형식 지정`, `inline: 인라인 박스 형식으로 지정`, `inline-block: 블록과 인라인의 중간 형태로 지정`이 존재한다.

### display 속성 적용하기
`display`에 `none` 키워드를 적용하면 태그가 화면에서 보이지 않는다.
즉, 중간에 있는 div 태그 전체가 사라지게 된다.

```html
<style>
	#box {
		display: none;
	}
</style>
<body>
	<span>더미 객체</span>
	<span id="box">대상 객치</span> /*보이지 않음*/
	<span>더미 객체</span>
</body>
```

`display`에 `block` 키워드를 적용하면 인라인 태그인 span이 block처럼 적용된다. 이를 통하여 한 줄에 출력되던 `더미 객체 대상 객체 더미 객체`가

더미 객체<br>
대상 객체<br>
더미 객체

로 표시되게 된다.

이와 반대로 `display`에 `inline` 키워드를 적용하면 블록 태그인 div가 inline처럼 작용하게 된다. 아래와 같이 코드를 작성하였을 때 `더미 객체 대상 객체 더미 객체`로 표시된다.

```html
<head>
    <style>
        div {
            display: inline;
        }
    </style>
</head>
<body>
    <div>더미 객체</div>
    <div id="box">대상 객체</div>
    <div>더미 객체</div>
</body>
```

마지막으로 `inline-block` 태그는 inline과 block의 특징을 섞어둔 블록으로 `width`나 `height` 값을 지정할 수 없었던 `inline` 태그와 다르게 `width`와 `height` 값을 지정할 수 있다.

```html
<head>
    <style>
        .a { display: inline;       width: 100px; height: 50px; background: yellow; margin: 20px; }
        .b { display: inline-block; width: 100px; height: 50px; background: skyblue; margin: 20px; }
    </style>
</head>
<body>
    <span class="a">인라인</span>
    <span class="b">인라인블록</span>
</body>
```

이러한 코드를 작성했을 때 `inline` 속성을 적용받은 태그는 `background-color: yello;`만 적용되지만, `inline-block`을 속성을 적용받은 태그는 `width`, `height`, `margin`, `background-color` 모두 적용받는 것을 확인할 수 있다.

## 배경 속성
배경에 이미지나 색상은 아래와 같은 배경 속성을 사용해 지정한다.

- `background-image`: 배경 이미지 삽입
- `background-size`: 배경 이미지의 크기 지정
- `background-repeat`: 배경 이미지의 반복 형태 지정
- `background-attachment`: 배경 이미지의 부착 형태 지정
- `background-position`: 배경 이미지의 위치 지정
- `background`: 한 번에 모든 배경 속성 입력

### 배경 이미지 삽입과 크기 지정
`background-image` 속성은 배경 이미지를 지정하는 속성으로 스타일 값에는 URL 단위나 그레이디언트를 입력한다.
배경 이미지 크기는 `background-size`속성으로 조정하고 크기 단위나 키워드를 입력할 수 있다.

크기 단위로는 퍼센트를 많이 사용하고, 너비와 높이 값 2개를 입력할 수 있다.
먼저 배경 이미지를 삽입하는 방법은 `background-image: url('image.png')`가 있으며, 만약 현재 폴더 아래의 Other/image.png를 가져오고 싶다면 `./Other/image.png`로 입력, pc 루트 폴더 아래에 있다면 `/image.png`처럼 입력할 수 있다.
또한 `background-image: url('backgroundFront.png'), url('backgroundBack.png');`이렇게 입력할 수 있으며 왼쪽에 입력된 속성이 앞에 위치한다.

배경 이미지의 크기는 `background-size` 속성을 사용해 조절할 수 있으며 크기 단위는 `background-size: 가로, 세로`로 지정할 수 있다. 여기서 주의해야 할 점은 아래와 같다.
```css
body {
	background-image: url('BackgroundFront.png'), url('BackgroundBack.png');
	background-size: 100%, 250px; /*첫 번째 이미지의 너비 100%, 두 번째 이미지의 너비 250px*/
}
```

### 배경 이미지의 반복과 부착 형태, 위치
배경 이미지의 반복 형태는 `background-repeat`속성을 통하여 설정하고, `background-attachment`는 배경 이미지를 화면에 고정하는 속성이다. `background-position` 속성은 배경 이미지의 배치 위치를 지정하는 속성이다.

`background-repeat`속성은 다음과 같은 속성들을 가지고 있으며, 배경 이미지가 어떻게 반복될지를 지정하는 속성이다.
- `background-repeat: repeat`: 가장 기본 속성, 무한 반복의 특성을 가진다.
- `background-repeat: repeat-x`: 가로로만 이미지 반복, 세로축은 비어있음
- `background-repeat: repeat-y`: 세로로만 이미지 반복, 가로축은 비어있음
- `background-repeat: no-repeat`: 가로, 세로방향 모두 반복 X

`background-attachment`는 배경 이미지를 화면에 고정하는 속성이다.
- `background-attachment: scroll`: 가장 기본 속성, 페이지와 함께 배경 이미지가 스크롤되는 형식
- `background-attachemnt: fixed`: 화면에 고정, 스크롤하여도 따라오지 않고 그 자리에 멈추어있음
- `background-attachment: local`: 요소 내부  스크롤에 따라  배경도 함께 이동함

여기서 `scroll`과 `local`의 차이는 배경이 박혀서 고정되는지(scroll), 혹은 스크롤에 따라서 같이 글자와 이동하는지(local) 여부의 차이이다.

`background-position`은 배경 이미지의 배치 위치를 지정하는 속성으로 키워드를 통해 위치를 지정할 수도 있고, X축 위치나 Y축 위치를 입력하여 위치를 지정해줄 수도 있다.
- `background-position: center`: 사이트의 중앙에 이미지를 삽입하는 방법
- `background-position: 50px 20px`: 사이트의 왼쪽에서 50px 위에서 20px 떨어진 곳에 삽입

## 글자 속성
### 글자 크기와 글꼴
글자 크기를 지정하는 속성은 `font-size`속성이다. 해당 속성에는 여러 키워드를 입력할 수 있으며 대표적으로 아래와 같은 속성들이 존재한다.
- `font-size: large/medium/small`: 폰트의 크기를 작게/보통/크게 설정한다.
- `font-size: 50px`: 폰트의 크기를 50px로 설정한다.

또한 글꼴을 지정하는 `font-family`속성이 존재하며 다양한 글꼴을 입력하여 사용할 수 있다.
- `font-family: 'Times New Roman', Arial;`: Times New Roman 폰트를 사용하되 없을 시에는 Arial 폰트 사용

### 글자 스타일과 굵기
글자의 굵기와 기울기는 `font-style`과 `font-weight`속성으로 조정한다.
`font-style`속성은 글자의 스타일(기울기 등)을 지정하며, `font-weight` 속성은 글자 굵기를 지정한다.

`font-style`의 대표적인 키워드는
- `italic`: 기울임꼴
- `normal`: 기본 값
- `oblique`: 일반 글자를 기계적으로 기울인 모양
등이 존재한다.

`font-weight`의 대표적인 키워드는
- `normal`: 기본 값(400)
- `bold`: 굵게(700)
- 실제 숫자 입력
등이 존재한다.

### 글자 정렬
`text-align`속성은 글자 정렬을 지정한다.
text-align 속성에는 다음과 같은 키워드를 지정할 수 있다.

- `center`: 중앙
- `left`: 왼쪽 
- `right`: 오른쪽
- `start`: 언어의 시작 지점
- `end`: 언어의 끝 지점

### 링크 글자의 밑줄
`text-decoration`을 통하여 글자의 여러 꾸밈 속성을 지정하고 편집할 수 있다.

예를 들어 `a`태그에 `href`속성을 지정하면 글자에 밑줄이 생기면서 파란색으로 변경된다.
하지만 일반 웹 페이지에는 링크에 밑줄이 없는 경우가 많은데, 이는 `text-decoration`속성을 적용해서 밑줄을 제거했기 때문이다.

`text-decoration: none;`속성을 지정하면 밑줄을 제거할 수 있다.

## 위치 속성
### 요소의 고정 위치와 상대 위치 지정
요소의 위치 지정 형식을 설정할 때는 `position`속성을 사용한다.
예를 들어 절대 위치 좌표를 사용하려면 `position`속성에 `absolute`나 `fixed` 키워드를 입력하고 상대 위치 좌표를 사용하려면 `static`이나 `relative`키워드를 입력한다.

- `position: absolute`: 절대 위치 좌표 설정
- `position fixed`: 화면을 기준으로 절대 위치 좌표 설정
- `position: relative`: 초기 위치에서 상하좌우로 위치 이동
- `position static`: 위쪽에서 아래쪽으로 순서대로 배치

하지만 position만 사용하면 웹 브라우저마다 출력 형태가 다를 수 있으므로 이를 통일하기 위해 스타일 속성을 함께 사용해야 한다. 그리고 요소의 위치를 변경하고 싶을 때에는 `z-index`라는 속성을 사용해야 한다.

예를 들어 3개의 박스가 존재한다고 할 때 `position: absolute`를 설정했다고 하면, 세가지 박스가 모두 고정 위치를 사용하여 겹처 보이게 될 것이다. 여기서 각 박스에 `left`값과 `top`값을 다르게 해준다면 위치가 달라져서 세가지 박스가 모두 보이게 된다.(top값이 양수쪽으로 크면 클수록 아래로 내려감)

또한 이 3가지 박스에 모두 `z-index`를 적용해준다면 어떤 박스를 가장 위에 올릴지 여부도 변경할 수 있으며, `z-index`값이 양수쪽으로 크면 클수록 다른 요소들보다 위로 올라와 보이게 된다.

### div같은 블록에서 범위를 벗어난 요소의 처리
이렇게 스타일을 지정해 위치를 설정해줄 수 있는 것을 알게 되었다. 하지만 이러한 요소를 div같은 블록 형식의 요소에서 사용하게 된다면 정해진 크기를 넘어서는 디자인이 나올 수 있다. 이를 처리하는 방법을 알아보자.

먼저 이를 처리하는 방법은 `overflow`속성을 적용해주는 방법이 있고, 대표적으로 2가지 방법으로 처리할 수 있다.
- `overflow: hidden`: 영역을 벗어나는 부분을 숨기기
- `overflow: scroll`: 영역을 벗어나는 부분을 스크롤로 만들기

## 그림자와 그레이디언트 속성
### 그림자 속성
그림자 속성에는 글자에 그림자를 부여하는 `text-shadow`속성과 박스에 그림자를 부여하는 `box-shadow`속성이 존재한다.
각각 사용 방법은 다음과 같다.
- `text-shadow: 5px 5px 5px black`: 각각 오른쪽, 아래, 흐림도, 그림자 색상을 지정
- `box-shadow: 5px 5px 5px black`: 각각 오른쪽, 아래, 흐림도, 그림자 색상을 지정

### 그레이디언트 속성
그레이디언트는 두 가지 이상의 색상을 혼합하는 채색 기능이다.
사용 방법은 `linear-gradient(45deg, #f85032 0%, #e73827 100%)`처럼 사용하고, 각각 각도, 색상과 위치, 색상과 위치를 의미한다.