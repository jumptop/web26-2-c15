# 입력 양식 태그
입력 양식은 사용자에게 정보를 입력받는 요소<br>
## 입력 양식 개요
입력 양식은 from 태그로 영역을 생성하고, form 태그 내부에 input 태그를 넣어 만듦
```HTML
<body>
    <form>
        <input type="text" name="search">
        <input type="submit">
    </form>
</body>
```
# 입력 양식 종류
HTML5에서 다양한 입력 양식 태그를 지원함<br>
`form`태그는 속성이 없으며 모양이 보이지 않음, 입력 양식의 시작과 끝을 표시하는 태그
## input 태그
input태그는 사용자의 입력을 받기 위한 가장 일반적인 입력값의 형태이다.<br>
아래 속성을 보며 input태그의 여러 속성을 확인해보자.

- `text`: 글자 입력 양식 생성
- `button`: 버튼 생성
- `checkbox`: checkbox 생성
- `hidden`: 보이지 않음
- `image`: 이미지 형태 생성
- `password`: 비밀번호 입력 양식 생성
- `reset`: 초기화 버튼 생성
- `submit`: 제출 버튼 생성
- `textarea`: 여러 행의 글자 입력 양식 생성, cols 속성은 너비를 지정하고 rows 속성은 높이를 지정

```HTML
<body>
	<!--입력양식 종류-->
	<!--사용자가 입력하는 입력 양식-->
	<input type="text", name="text", value="text"><br>
	<input type="password", name="password", value="value"><br>
	<input type="file", name="file", value="file"><br>
	<input type="checkbox", name="checkbox", value="checkbox"><br>
	<input type="radio", name="radio", value="radio"><br>
	
	<!--보이지 않는 양식-->
	<input type="hidden", name="hidden", value="hidden">
	
	<!--버튼-->
	<input type="button", value="button11"><br>
	<input type="reset", value="reset"><br>
	<input type="submit", value="submit"><br>
	<input type="image", src="../Chapter3/images.jpeg"><br>
</body>
```
## label 태그
라벨 태그는 `input`태그를 설명할 때 사용된다.<br>
`label` 태그의 `for` 속성에 `input` 태그의 `id`를 입력하면 둘이 연결됨

```HTML
<form>
    <label for="name">이름</label>
    <input id="name" type="text">
</form>
```

## radio 사용
`input` 태그의 `radio` 속성을 사용할 때 `name` 속성을 같이 사용한다면 여러개의 radio 버튼 중 하나만 선택할 수 있도록 구성이 가능해진다.

```HTML
<form>
    <input type="radio" name="gender" value="m">
    <input type="radio" name="gender" value="w">
</form>
```

## select 태그
목록으로 보여주는 항목 중 하나 혹은 여러 항목을 선택할 때 사용하는 입력 요소<br>
기본적으로 `select` 태그 안에 `option` 태그를 넣으면 옵션을 선택할 수 있는 요소가 생성된다.

```HTML
<body>
    <select>
        <option>김밥</option>
        <option>떡볶이</option>
        <option>순대</option>
        <option>어묵</option>
    </select>
</body>
```

만약 여러 항목을 선택하고 싶다면 `select`태그의 `multiple`속성을 사용할 수 있다.

```HTML
<body>
    <select multiple="multiple">
        <option>김밥</option>
        <option>떡볶이</option>
        <option>순대</option>
        <option>어묵</option>
    </select>
</body>
```

또한 `option`을 그룹으로 묶는 `optgroup`옵션도 사용할 수 있다.

```HTML
<body>
    <select>
        <optgroup label="HTML5">
            <option>Multimedia tag</option>
            <option>Connectivity</option>
            <option>Device Access</option>
        </optgroup>
        <optgroup label="CSS3">
            <option>Animation</option>
            <option>3D Transform</option>
        </optgroup>
    </select>
</body>
```

## fieldset 태그와 legend 태그
`fieldset`태그와 `legend`태그를 사용하면 입력 양식을 그룹으로 묶고 이름을 지정할 수 있다.<br>
`legend`태그는 `fieldset`태그 내부에 사용한다.

```HTML
<body>
    <form>
        <fieldset>
            <legend>입력 양식</legend>
            <table>
                <tr>
                    <td><label for="name">이름</label></td>
                    <td><input id="name" type="text"></td>
                </tr>
                <tr>
                    <td><label for="mail">이메일</label></td>
                    <td><input id="mail" type="email"></td>
                </tr>
            </table>
            <input type="submit">
        </fieldset>
    </form>
</body>
```

## textarea 태그
글자를 여러 줄 입력받을 때 사용하는 태그<br>
주의해야 할 점은, 코드를 예쁘게 작성하려고 들여쓰기를 한다면 들여쓴 만큼 텍스트에 공백이 생기게 된다. 아래 두 예제 중 두 번째 예제처럼 작성해야 한다.

```HTML
<body> 
    <!--잘못된 입력-->
    <textarea>
        Textarea 태그
        Textarea 태그
    </textarea>
</body>
```
``` HTML
<body>
    <!--올바른 입력-->
    <textarea>Textarea 태그
Textarea 태그</textarea>
</body>
```

# HTML5 문서 구조화
## 공간 분할 태그
CSS로 원하는 레이아웃을 구성할 수 있도록 공간을 분할해야 함.<br>
아래에는 대표적인 공간 분할 태그 `div`와 `span`을 소개하겠다.

### div
div 태그는 블록 형식으로 공간을 분할한다.<br>
이러한 방식은 각 태그가 한 행을 차지하며 이 공간을 `블록`이라 칭한다.
```HTML
<div>div 태그 - block 형식</div>
<div>div 태그 - block 형식</div>
<div>div 태그 - block 형식</div>
<div>div 태그 - block 형식</div>
```

### span
span 태그는 공간을 인라인 형식으로 분할한다.<br>
코드를 실행하면 각 태그는 **자신의 글자 크기만큼** 영역을 차지하며, **왼쪽에서 오른쪽**으로 쌓이게 된다. 이를 인라인<sub>inline</sub> 형식이라 부른다.
```HTML
<span>span 태그 - inline 형식</span>
<span>span 태그 - inline 형식</span>
<span>span 태그 - inline 형식</span>
<span>span 태그 - inline 형식</span>
```

또한 일반 태그들도 블록/인라인 형식으로 나뉘게 되는데 예제는 다음과 같다.
<table>
    <tr>
        <th>블록 형식 태그</th>
        <th>인라인 형식 태그</th>
    </tr>
    <tr>
        <td>div 태그</td>
        <td>span 태그</td>
    </tr>
    <tr>
        <td>h1 ~ h6 태그</td>
        <td>a 태그</td>
    </tr>
    <tr>
        <td>p 태그</td>
        <td>input 태그</td>
    </tr>
    <tr>
        <td>목록 태그</td>
        <td>글자 형식 태그</td>
    </tr>
    <tr>
        <td>테이블 태그</td>
        <td>s입력 양식 태그</td>
    </tr>
</table>

## 시맨틱 태그
시맨틱이란?<br>
'의미론적인'이라는 뜻을 담고 있으며, 시맨틱 웹은 컴퓨터 프로그램이 코드를 읽고 의미를 인식할 수 있는 지능형 웹을 의미함.