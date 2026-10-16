# 선택자의 용도와 사용법
HTML 페이지에 CSS를 사용해 꾸밀 수 있다.

CSS로 작성된 코드를 `스타일시트`라고 하며, 현재는 CSS3을 사용중이다.

CSS3에서 특정 HTML 태그를 선택할 때에는 **선택자**를 사용한다.


`h1 { color: red; }`이러한 코드에서 `h1 = 선택자`, `color = 스타일 속성`, `red = 스타일 값`이라 부른다.


## 스타일 선택자 종류( 중요한 것들만 정리 )
- `전체 선택자`: *을 입력하여 사용
- `태그 선택자`: h1과 같은 태그 이름을 입력하여 사용
- `아이디 선택자`: #id 와 같이 #을 붙여서 사용
- `클래스 선택자`: .을 붙여서 사용, ex: `.header`
- `후손 선택자`: 선택자 선택자 <- 이처럼 띄어서 사용, ex: header h1 <- header 아래에 있는 모든 h1 태그를 선택함
- `자손 선택자`: 선택자 > 선택자 <- 이처럼 `>`를 붙여 사용, ex: header > h1 <- header 바로 하위의 h1태그만 선택

# 기본 선택자
본격적으로 선택자를 정리해보자.

기본 선택자는 아래 4종류로 나뉜다.

- `전체 선택자` *
- `태그 선택자` 태그(h1, h2, p 등)
- `아이디 선택자` #아이디(#id_name, #header 등)
- `클래스 선택자` 클래스(특정 클래스가 있는 태그 선택)

## 전체 선택자 예제
```HTML
<head>
    <style>
        * { color: red; } /* 모든 색상을 붉은색으로 설정 */
    </style>
</head>
```

## 태그 선택자 예제
```HTML
<head>
    <style>
        h1 { color: red; } /* h1 태그만 붉은색으로 설정 */
        p { color: blue; } /* p 태그만 푸른색으로 설정 */
    </style>
</head>
```

## 아이디 선택자 예제
```HTML
<head>
    <style>
        #header { color: red; } /* h1을 id로 가진 요소만 붉은색으로 설정 */
        #wrap { color: blue; } /* wrap를 id로 가진 요소만 푸른색으로 설정 */
    </style>
</head>
<body>
    <div id = "header">
        <h1>#header 태그</h1>    
    </div>
</body>
```

## 클래스 선택자 예제
```HTML
<head>
    <style>
        .select { color: red; } /* select 선택자만 붉은색으로 설정 */
    </style>
</head>
<body>
    <ul>
        <li class="select">사과</li> <!--붉은색-->
        <li>바나나</li>
        <li class="select">오렌지</li> <!--붉은색-->
        <li>감</li>
    </ul>
</body>
```

# 속성 선택자
속성 선택자는 특정 속성 또는 값이 있는 태그를 선택할 때 사용한다.

- `선택자[속성]`: 특정한 속성이 있는 태그 선택
- `선택자[속성=값]`: 특정한 속성 내부 값이 특정한 값과 같은 태그 선택

예를 들어 다음과 같이 코딩해볼 수 있다.
```HTML
<head>
    <style>
        input[type="text"] { background-color: red; }
        input[type="password"] {background-color: blue; }
    </style>
</head>
<body>
    <form>
        <input type="text">
        <input type="password">
    </form>
</body>
```

# 후손 선택자와 자손 선택자
후손 선택자와 자손 선택자는 각각 다른 의미를 갖는다.
`div`라는 부모가 있을 때 `h1`, `h2`, `ul`이라는 자손을 가질 수 있고, `ul`이라는 자손이 또 `li`라는 자손을 가질 수 있다.

여기서 `div`의 자손은 `h1`, `h2`, `ul`이고, 자손을 포함한 자손의 자손까지 포함한 범위가 후손이다.


아래는 후손 선택자의 예제로, 자손과 후손을 모두 선택하는 것을 볼 수 있다.
```HTML
<head>
    <style>
        #header h1 { color: red; } /* #header의 h1 후손 전체 선택 */
    </style>
</head>
<body>
    <div id="header">
        <h1 class="title">Lorem ipsum</h1> <!--#header의 자손-->
        <div id="nav">
            <h1>Navigation</h1> <!--header의 후손-->
        </div>
    </div>
</body>
```

아래는 자손 선택자의 예제로, 자손인 바로 아래 요소에만 `color: red;`가 적용된다.
```HTML
<body>
    <style>
        #header > h1 { color: red; }
    </style>
</head>
<body>
    <div id="header">
        <h1 class="title">Lorem ipsum</h1>
        <div id="nav">
            <h1>Navigation</h1>
        </div>
    </div>
</body>
```

# 반응·상태·구조 선택자
## 반응 선택자
반응 선택자는 사용한 반응으로 생성되는 특정한 상태를 선택한다.

사용자가 특정 태그 위에 마우스 커서를 올리면 `hover` 상태이고, 특정 태그를 마우스로 클릭하면 `active` 상태이다.

```HTML
<head>
    <style>
        h1:hover {color: red;}
        h1:active {color: blue;}
    </style>
</head>
<body>
    <h1>반응 선택자</h1>
</body>
```
<head>
    <style>
        h3:hover {color: red;}
        h3:active {color: blue;}
    </style>
</head>
<body>
    <h3>여기에 마우스를 올려보세요.</h3>
</body>

다음과 같이 실제로 위 글자에 마우스 포인터를 올리면 붉은색으로 변하고(`h1:hover {color: red;}`), 마우스로 클릭하면 파란색으로(`h1:active {color: blue;}`) 변하게 된다.

## 상태 선택자
상태 선택자는 입력 양식의 상태를 선택할 때 사용한다.

- `:checked`: 체크 상태의 input 태그 선택
- `:focus`: 포커스를 맞춘 input 태그 선택
- `:enabled`: 사용 가능한 input 태그 선택
- `:disabled`: 사용 불가능한 input 태그 선택

상태는 이와 같이 존재하며, `checkbox`, `radio`인 input 태그가 선택된 상태를 `checked`라고 표현한다.

focus는 사용자가 입력할 수 있도록 입력 양식에 포커스를 둔 상태를 의미한다.

`disabled`는 속성값으로 `disabled="disabled"`처럼 사용 가능하며, 해당 속성이 적용된 input 태그는 입력을 받지 못하는 상태가 된다.

## 구조 선택자
구조 선택자는 특정한 위치에 있는 태그를 선태할 때 사용된다.

- `:first-child`: 형제 관계에서 첫 번재로 등장하는 태그 선택
- `:last-child`: 형제 관계에서 마지막으로 등장하는 태그 선택
- `:nth-child(수열)`: 형제 관계에서 앞에서 수열 번째로 등장하는 태그 선택
- `:nth-last-child(수열)`: 형제 관계에서 뒤에서 수열 번재로 등장하는 태그 선

예를 들어 다음 코드처럼 사용이 가능하다

```HTML
<head>
    <style>
        ul {overflow: hidden;}
        li {
            list-style: none;
            float: left; padding: 15px;
        }
        li:first-child {border-radius: 10px 0 0 10px;}
        li:last-child {border-radius: 0 10px 10px 0;}

        li:nth-child(2n) {background-color: brown;}
        li:nth-last-child(2n+1) {background-color: aqua;}
    </style>
</head>
<body>
    <ul>
        <li>one</li> <!--first child-->
        <li>two</li>
        <li>three</li>
        <li>four</li>
        <li>five</li>
        <li>six</li>
        <li>seven</li> <!--last child-->
    </ul>
</body>
```
이러한 코드에서 `ul` overflow: hidden 속성은 순서가 없는 리스트에서 리스트 표시를 제하는 것을 뜻한다.

`li`에는 리스트 스타일을 설정하지 않고, 왼쪽 정렬 후 `padding`값을 15px 주어 서로 떨어질 수 있도록 하였다.

`li:first-child`를 통하여 바로 위의 부모 기준(`ul`)첫번째 값에 위쪽을 10px 둥글게, 왼쪽을 10px 둥글게 설정하였다. 참고로 `border-radius`의 설정값 기준은 **위 -> 오른 -> 아래 -> 왼쪽**순서로 시계방향이다.

이러한 방식으로 `li:last-child`도 설정해주었고, `li:nth-child(2n)`을 통해 2n번째 수열마다 brown 색상을 넣어주게 되었다. 즉, 0번째에는 x, 1번째에는 2번째 블록에, 3번째에는 4번째 블록에 색상을 넣어주어 2의 배수에 색상을 적용해주었다.

그리고 `li:nth-last-child(2n+1)`을 사용하여 뒤에서부터 2n+1번째 수열에 aqua 색상을 적용햊었고, 이는 1, 3, 5, 7, 9와 같은 소수를 의미한다.

# CSS3 단위
스타일 속성을 적용하려면 먼저 스타일 값으로 입력할 수 있는 CSS3 단위를 알아야 한다.

스타일 값으로 입력할 수 있는 단위에는 키워드, 크기, 색상, URL이 있다.

속성별로 한 가지 단위만 사용할 수 있는 것은 아니므로 우선 스타일 값의 단위 종류부터 알아보자.

## 키워드 단위
키워드는 `W3C`단체에서 미리 정의한 단어이다.

예를 들어 `body{ display: }` 까지만 작성한다면 IDE(Integration Development Environment)에서 자동으로 `blocks`, `contents`, `flex` 등 여러 키워드를 제시해준다.

## 크기 단위
크기 단위는 CSS3에서 가장 많이 사용하는 단위로 대표적으로 다음 종류가 존재한다.

- `%`: 백분율 단위
- `em`: 배수 단위
- `px`: 픽셀 단위

예를 들어 백분율 단위는 다음과 같이 사용할 수 있다.
```HTML
<head>
    <style>
        p:nth-child(1) { }
        p:nth-child(2) { font-size: 100%; }
        p:nth-child(3) { font-size: 150%; }
        p:nth-child(4) { font-size: 200%; }
    </style>
</head>
<body>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
</body>
```

이렇게 사용했을 때 첫번째 요소에는 아무런 값을 넣지 않았으므로 브라우저의 기본 값(100%)을 사용하게 되고, 2번째 요소 또한 100%로 브라우저 기본 값, 3번째는 1.5배 4번째는 2배를 뜻한다.

또한 `em`단위도 이와 같으며 배수단위를 뜻한다.

`1.0em` = 1배율, `1.5em` = 1.5배율, `2.0em` = 2배율로 이해하면 된다.

`px`단위는 절대적인 크기를 설정하는 단위로

`16px` = p태그 기본 사이즈, `24px` = p태그의 1.5배 사이즈, `32px` = p태그 2배 사이즈로 이해할 수 있다.

## 색상 단위
색상을 입력하는 가장 간단한 방법은 `h1 {color: red;}`같이 색상에 해당하는 영단어를 입력하는 것이다.
하지만 영단어로 표현할 수 있는 색상은 제한되어 있기 때문에 `rgba(255, 255, 255, 0.25)`단와 `Hex코드-#0094FF`를 지원한다.

rgba는 색의 삼원색인 red, green, blue와 alpha(투명도)를 제공하며, Hex는 16진수로 색상을 표현할 수 있다.

## URL 단위
이미지나 글꼴 파일을 불러올 때는 URL 단위를 사용한다.

`background-image` 속성을 사용하면 배경 이미지를 지정할 수 있다.

`body {background-image: url('test.jpg');}`와 같은 형식으로 사용할 수 있다.

또한 현재 폴더에 있는 이미지를 사용할 때만 /(경로표시자)를 생략할 수 있고, 예를 들어 Other 폴더의 test.jpg를 가져오려면 `background-image: url('Other/test.jpg');`, 루트 경로에 있는 test.jpg를 가져오려면 `background-image: url('/test.jpg');`처럼 사용하면 된다.