# HTML 
<br>  

[기본 형태](#기본-형태)  
[HTML 문서의 범위](#html-문서의-범위)  
[메타데이터](#메타데이터)  
[블럭 요소](#블럭-요소)  
[인라인 요소](#인라인-요소)  
[블럭과 인라인의 차이](#블럭과-인라인의-차이)  
[표 콘텐츠](#표-콘텐츠)  

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

>\!는 html 태그가 아님을 명시

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
 
## 블럭 요소 
* ### \<div\> <br>
아무런 의미를 가지지 않으며, 영역을 설정하는데 주로 사용되는 태그   
* ### \<header\> <br>
 header를 만들 때 사용  
소개나 탐색을 돕는 것의 그룹 (가장 상단 바 로그, 메뉴, 로그아웃 등의 콘텐트)  
footer, 다른 header의 후손이 될 수 없다.  
즉, header안에 header를 쓸 수 없다.  
전역 속성이다.  
* ### \<footer\> <br>
 footer의 영역 지칭, 일반적으로 사이트 가장 하단에 있는 바(관련 문서 링크, 주소...)  
 특성은 header와 같다.  
* ### \<h1\~h6\>      
 6단계의 문서 제목 구현, 전역 속성  
 > 제목 폰트의 크기를 줄이기 위해 낮은 단계를 사용하지 않음  
 > 제목 단계를 건너뛰는 것은 피해야함(h1->h3)  
 > h1은 한 페이지에 하나만 사용  
* ### \<main\>  
문서의 핵심 콘텐츠를 설정  
한 문서에 하나의 태그만 존재  
internet Explorer 지원 불가  
* ### \<article\>   
독립적으로 구분되거나 재사용 가능한 영역을 설정(매거진/신문 기사 등)  
h1-h6을 포함하여 식별  
```html
<article class="forecast">
  <h1>Weather forecast for seattle</h1>
  <article class="day-forecast">
    <h2>02 March 2018</h2>
    <p>Rain</p>
  </article>
  <article class="day-forecast">
    <h2>04 March 2018</h2>
    <p>periods of rain</p>
  </article>
  <article class="day-forecast">
    <h2>05 March 2018</h2>
    <p>Heavy rain</p>
  </article>
</article> 
```  
* ### \<section\>  
문서의 일반적인 영역을 나누는 용도로 사용, h1-h6을 포함하여 식별  
> div와 차이점  
> section은 일반적으로 의미를 가짐  
>> article과의 차이점  
>> article은 독립적임  
  
* ### \<aside\>  
문서의 별도 콘텐츠를 설정(광고 배너)  

* ### \<nav\>  
Navigation, 다른 페이지 링크를 제공하는 영역 설정(메뉴, home, contact...)
```html
<nav>
  <a href="/html/">HTML</a> |
  <a href="/css/">CSS</a> |
  <a href="/js/">JavaScript</a> |
  <a href="/python/">Python</a>
</nav>
```  
* ### \<address\>  
연락처 정보 제공  
```html
<address>
  <a href="mailto:minji@naver.com">minji@naver.com</a><br>
  <a href="tel:+821012345678">010-1234-5678</a>
</address>
```  
* ### \<ol\>, \<ul\>, \<li\>  
\<ol\>: ordered-List  
\<ul\>: unordered-List  
\<li\>: 목록을 만드는 태그  
\<li\>는 단독으로 사용 불가(ol+li, ul+li)  

```html
<ul>
    <li>Neil Armstrong</li>
    <li>Alan Bean</li>
    <li>Peter Conrad</li>
</ul>
```  
```html
<ol>
  <li>Mix flour, baking powder, sugar, and salt.</li>
  <li>In another bowl, mix eggs, milk, and oil.</li>
  <li>Stir both mixtures together.</li>
  <li>Fill muffin tray 3/4 full.</li>
  <li>Bake for 20 minutes.</li>
</ol>
```  

* ### \<dl\>, \<dt\>, \<dd\>  
\<dt\>: 용어  
\<dd\>: 정의  
\<dl\>: 용어 정의 쌍들의 영역 설정  
```html
<dl>
    <dt>Beast of Bodmin</dt>
    <dd>A large feline inhabiting Bodmin Moor.</dd>
</dl> 
```  
* ### \<p\>  
하나의 문단, 문장을 설정  
<br>

## 인라인 요소  

* ### \<a\>
다른 페이지, 같은 페이지 위치, 파일 등 다른 URL로 연결할 수 있는 하이퍼링크 설정  
버튼 형태로 많이 쓰임  

속성|의미|값
:---:|:---:|:---:
rel|현재 문서와 링크 URL의 관계|```license```, ```prev```, `next`...
href|링크 URL|URL 
target|링크 URL의 표시 위치|```_self```(현재창에서 새로운 페이지), ```_blank```(새로운 탭 생성)  
```html
<a href="mailto:minji@naver.com">minji@naver.com</a><br>
  <a href="tel:+821012345678">010-1234-5678</a>
```
* ### \<dfn\>  
용어 정의할 때 사용  
> dl,dd,dt와의 차이점  
>> dfn은 하나의 용어 정의할 때 사용하며, dl은 용어와 정의를 나열할 때 사용  

* ### \<q\>  
짧은 인용문 설정  
긴 인용문은 \<blocquote\>사용  

* ### \<span\>  
의미가 없는 콘텐츠 영역 설정  
div와 같은 용도, div는 블록 요소, span은 인라인 요소  

* ### \<img\/\>  
빈태그, 이미지 삽입  
src: 이미지 url (필수), alt: 이미지의 대체 텍스트(필수)  
```html
  <img class="fit-picture"
     src="/media/cc0-images/grapefruit-slice-332-332.jpg"
     alt="Grapefruit slice atop a pile of other slices">
  ```  
* ### \<iframe\>  
다른 html 페이지를 현재 페이지에 삽입  
 <br>

## 블럭과 인라인의 차이 
* __블록 요소__  
  * 수직으로 쌓인다.
  * 사용 가능한 최대 가로 너비를 사용
  * width: 100%; height: 0;로 시작) 
  * 크기 지정 가능 
  * margin, padding 위, 아래, 좌, 우 사용 가능
  * 레이아웃으로 주로 사용
  * ex) div, h1, p...<br>
* __인라인 요소__  
  * 수평으로 쌓인다.
  * 필요한 만큼의 너비를 사용
  * width: 0; height: 0;로 시작
  * 크기 지정 불가
  * margin, padding 위, 아래는 사용 불가
  * 텍스트로 주로 사용
  * ex) span, img, a...<br>
  <br>

## 표 콘텐츠  
  * ### 표 기본 틀 생성 태그  
    * __\<table\>__: 표 영역 설정, 블럭 요소와 비슷한 특성을 가짐  
    * __\<tr\>__: 행  
    * __\<th\>, \<td\>__: 열(cell)   
      * __th(table header)__: 머리글 칸을 지정  
      * __td(table data)__: 일반 칸을 지정   
***
웹 표준 검사 사이트 [W3C validator](https://validator.w3.org/#validate_by_upload)  
html 요소 참고서 [MDN](https://developer.mozilla.org/ko/) \/ [W3Schools](https://www.w3schools.com/)

