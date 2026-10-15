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
라벨 태그는 `input`태그를 설명할 때 사용된다.
