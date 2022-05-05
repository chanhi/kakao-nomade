# kakao-nomade

 this is Nomade Kakao clone class

# HTML
*HTML은 브라우저의 골격이 되는 콘텐츠를 표현하는 문법(?)이다
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```
기본적으로 head, body로 구성되고 head는 웹의 설정으로 구성되고 body는 웹의 콘텐츠, 사용자가 보는 내용으로 구성된다.

### Tag
*콘텐츠를 나타내는 구간을 표현
```
<h2>Contents</h2>
```

### Tag Attributes
*Tag 속성으로서 Tag의 옵션을 사용
<a> 의 경우 href="" 의 attributes가 있다.
 
### More Tags
1. ```<h1></h1>``` h1 ~ h6 까지 있음
2. ```<a></a>``` 이 태그의 부분을 누르면 설정된 링크로 이동 *attributes: href
3. ```<img></img>``` 이미지 삽입 *attributes: src
4. ```<form></form>``` *form 안에 있을 때 여러가지 attribute를 사용할 수 있음. 예를 들어 input의 type=colors, disable, required
5. ```<input></input>``` *attributes: placeholder, type, value
6. ```<lable></lable>``` 클릭 시 지정된 input으로 이동 *attributes: for="input's id"
7. ```<div></div>``` division 분할, 즉 이 tag를 통해 공간을 구분함 *기본적으로 block 속성을 가짐
8. ```<span></span>``` 이것도 div와 같은 역할을 하지만 inline 속성을 가짐
9. ```<header></header><main></main><footer></footer>``` 그냥 구역을 나누기 위해서 존재하는 semantic tag *block

### id
id 란 고유식별자(unique identifier)이므로 같은 id를 가지는 tag는 없어야 한다.

#CSS
*브라우저를 화장시켜주는 문법(?)이다. 폭포처럼 위에서 아래로 읽는다.

```html
<head>
    <meta charset="UTF-8">
    <link href="style.css" rel="stylesheet" />
    <title>Document</title>
</head>
```
head 부분에 link를 넣어주면 해당 css파일이 import된다.

```css
h1 {
 color: red;
}
.className {
 font-size: 20px;
}
#id {
 text-align: center;
}
* {
 background-color: red;
}
```
*위와 같은 방식으로 태그, class, id를 지정하여 style을 변경한다.

#### block: 대부분의 tag들이 가지는 속성, 해당 tag가 있는 영역에 다른 객체가 못 옴
-content -> padding -> border -> margin
-collapsing margins: 두 content가 위, 아래에서 경계가 같아지면 서로 margin이 같아짐
#### inline: span, link 등의 tag가 가지는 속성, tag의 콘텐츠가 가지는 영역만 있음
-height, width를 가질 수가 없음

```
* {
 display: block
 display: inline
 display: inline-block
}
```
-해당 tag의 속성을 변경    
-block의 경우 혼자만 공간을 차지    
-inline의 경우 padding은 상하좌우 모두 가질 수 있지만, margin의 경우 상하는 가질 수 없다.(height와 width가 없음)    
-inline-block의 경우 inline 처럼 옆에 컨텐츠가 오지만 height와 width를 가질 수 있다.    
-inline-block의 단점    
 1. 생성하지 않은 빈 공간이 생김    
 2. 빈 공간에 대한 정해진 규칙이 없음     
 3. 반응형 디자인을 지원하지 않기 때문에 잘 사용하지 않음    

```
div {
 border: 1px solid red;
}
```
div 태그의 모든 box 경계선에 1px 크기의 빨간 선이 생긴다.

#### display

```css
body {
 display: flex;
 justify-content: center;
 align-items: center;
 display-direction: column-reverse;
 display-wrap: wrap;
}
```

3가지 규칙
1. 자식 element를 움직이기 위해서는 오로지 부모 element에게 명시한다.
2. main axis(주축): justify-content를 통해 조절(수평)
3. cross axis(교차축): align-items를 통해 조절(수직)

-display를 flex로 했을 때 default는 row(수평)이다    
-display-direction: column 으로 작성하면 주축이 수직이 되고 교차축이 수평이 된다
-reverse로 설정할 경우 순서가 뒤집힘

#### position    
- fixed: 주어진 값만큼 페이지를 기준으로 하여 고정된다 *레이어가 바뀌어서 정해진 위치에 '고정'
- relative: 처음 주어진 위치(static)를 기준으로 하여 주어진 값만큼 이동
- absolute: relative인 가장 가까운 부모를 기준으로 이동 *없는 경우 body가 relative한 부모가 됨

```
div {
 position: relative;
}
```
모든 div 태그가 relative 속성을 가진다

#### pseudo selector

```css
div:first-child {
 background-color: red;
}
div:last-child {
 background-color: blue;
}
span:nth-child(2),
span:nth-child(4) {
 background-color: green;
}
```
- div 태그중 첫번째 태그가 빨강
- div 태그중 마지막 태그가 파랑
- span 태그중 두번째, 네번째 태그가 초록
- :nth-child(even), :nth-child(2n) -> 짝수번째 태그
- :nth-child(odd), :nth-child(2n+1) -> 홀수번째 태그

```css
p span {
 color: red;
}
p > span {
 color: blue;
}
p + span {
 color: orange;
}
p ~ span {
 color: green;
}
```
- p 안에서 span 찾기 *부모 자식 순서를 잘 지켜야 실행됨
- p 바로 아래 자식 span
- p 바로 다음 형제 span
- p 다음 형제 중 span

input:required -> input중에 required 속성을 가진 태그
input:[placeholder~="name"] -> input 중에 palceholder이 name이 들어간 태그
input::placeholder -> placeholder 변경
p::selection -> 선택된 parse 변경

### Variables
```css
:root {
 --main-color: #000;
}
a {
 color: var(--main-colo);
}
```
document의 root에 변수를 저장해서 var()을 이용해서 사용

#### states
button:active
button:hover
input:focus
a:visited
form:focus-within - 자식들 중에 focused 된것이 있으면 실행

#Git, Github
```
git status
git add modifiedFile
...
git status
git commit -m "commit comment"
git push
```
