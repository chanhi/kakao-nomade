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
}
```
해당 tag의 속성을 변경

#Git, Github
```
git status
git add modifiedFile
...
git status
git commit -m "commit comment"
git push
```
