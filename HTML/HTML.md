# HTML 
<br>  

[기본 형태](#기본-형태)  
[HTML 문서의 범위](#html-문서의-범위)  
[메타데이터](#메타데이터)

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
<br>  

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

속성|의미|값
:---:|:---:|:---:
lang|문서의 언어|```ko```,```en```...

* ```<head></head>``` : HTML 문서의 정보 범위 지정(페이지 설명, CSS 선언 등)
* ```<body></body>``` : HTML 문서의 구조 범위 지정(내용의 형태, 레이아웃 등)
<br>  

## 메타데이터
* ### \<title\> 
브라우저의 탭에 보여지는 문서의 제목 설정  

* ### \<base\/\>  
HTML문서에 포함된 모든 상대 URL들의 기준 URL 설정  
한 문서에 하나의 ```<base />```요소만 포함 가능   
 
속성|의미|값
:---:|:---:|:---:
href|기준 URL|URL  


* ### \<link\/\>  
 외부 리소스의 연결 및 현재 문서와의 관계 명시  (CSS 가져오기)  
 

속성|의미|값
:---:|:---:|:---:
rel|(필수)현재 문서와 외부 리소스와의 관계|```stylesheet```, ```icon```...
href|기준 URL|URL 
type|외부 리소스의 MIME 타입|```text/css```, ```image/x-icon```...  

* ### \<meta\/\>  
기타 메타데이터 요소  

속성|의미|값
:---:|:---:|:---:
charset|문자인코딩 방식|```UTF-8```, ```EUC-KR```...
name|메타 데이터의 이름|```author```, ```description```...
http-equiv|서버/사용자 에이전트의 작동방식 변경에 대한 지시|```refresh```, ```X-UA_Compatible```...  
content|```name```, ```http-equiv```의 값


* ### \<style\/\>  
스타일 정보 설정  

속성|의미|값
:---:|:---:|:---:
type|MIME 타입|```text/css```  

<br>

***
웹 표준 검사 사이트 [W3C validator](https://validator.w3.org/#validate_by_upload)  
html 요소 참고서[MDN](https://developer.mozilla.org/ko/)\/[W3Schools](https://www.w3schools.com/)

