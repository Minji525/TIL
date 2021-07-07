# HTML 

[기본 형태](#기본-형태)  
[HTML 문서의 범위](#html-문서의-범위)

## 기본 형태
* __요소(element)__  
  컨텐츠(content)를 감싸는 태그(tag) <br>
  
    - 여는 태그(opening tag): 요소의 시작 => ```<p>```
    - 닫는 태그(closing tag): 요소의 끝 =>  ```</p>```
```html
  <p>content</p>
```
 빈 요소: 내용을 갖지 않는 요소 (닫는 태그 x)
 ```html
  <img src=".png" alt="image">
```
 
* __속성과 값__
```html
  <TAG 속성="값">content</TAG>
```
## HTML 문서의 범위
```html
<!DOCTYPE html>
<html>
  <head>
   /*문서의 정보*/
    <meta charset="UTF-8">
    <title>page</title>
  </head>
  <body>
    /*문서의 구조*/
    <div></div>
  </body>
 </html>
```  
* ```<!DOCTYPE html>``` : 
HTML 버전 정보를 의미하며, HTML 문서의 반드시 최상 위에 위치
* ```<html></html>``` : HTML 문서의 전체 범위 지정
* ```<head></head>``` : HTML 문서의 정보 범위 지정(페이지 설명, CSS 선언 등)
* ```<body></body>``` : HTML 문서의 구조 범위 지정(내용의 형태, 레이아웃 등)
* ```<meta charset="utf-8">``` : 문자인코딩 방식
* ```<title></title>``` : 페이지의 제목 설정, 브라우저의 탭에 표시 



웹 표준 검사 사이트 [W3C validator](https://validator.w3.org/#validate_by_upload)

