# CSS  
<br>

## CSS란?  
CSS(Cascading Style Sheets)는 웹페이지를 꾸미려고 작성하는 코드로, HTML 문서에 있는 요소들에 선택적으로 스타일을 적용하는 스타일 시트 언어이다.  
CSS는 웹 페이지의 스타일을 별도의 파일로 저장할 수 있게 해주므로 사이트의 전체 스타일을 손쉽게 제어할 수 있다.  
<br>  


## 선언 방식  
- __인라인(in-line) 방식__  
html요소의 style속성에 직접 작성하는 방식(HTML태그 안에 직접 작성)  
```html
<div style="color: red; font-size: 20px; font-weight: vold;> HELLO </div>
```  
- __내장 방식__  
head부분에 style속성을 통해 바디와 연결  
```html
<head>
    <style>
        div{
            color: red;
            font-size: 20px;
        }
    </style>
</head>
```
```html
<body>
    <div>HELLO</div>
</body>
```  
- __링크 방식__  
link를 통해 외부 문서 CSS를 가지고오는 것(html에서 CSS를 가지고 오는 것), 병렬 방식  

```html
<head>
    <link rel="stylesheet" href="css/common.css">
</head>
<body>
    <div>HELLO</div>
</body>
```  

```css
div{
    color: red;
    font-size: 20px;
}
```  
- __@import 방식__  
@import를 이용하여 외부 문서로 CSS를 불러와 적용하는 방식(CSS가 CSS를 불러오는 것)  
직렬 방식으로 시간이 더 걸림  
```html
<head>
    <link rel="stylesheet" href="css/common1.css">
</head>
<body>
    <div>HELLO</div>
</body>
```  

```css
@import url("./common2.css");

```  

```css
div{
    color: red;
    font-size: 20px;
}
```  
<br>

## 기본 문법  
```css
선택자{속성: 값;}
```  
__선택자__: 내가 원하는 요소를 선택하는 부분  
__속성과 값__: 선택한 요소에 지정될 CSS 명령, 선택자로 검색한 대상에 속성과 값을 입력하여 스타일을 지정  
<br>

## 선택자 종류  
### 기본 선택자(Basic Selector)  
__1. 전체 선택자__  
모든 요소를 선택 `*`  
__2. 태그 선택자__  
태그 이름으로 요소 선택 `E`  
__3. 클래스 선택자__  
HTML class 속성의 값이 E인 요소 선택 `.E`  
__4. 아이디 선택자__  
id 속성의 값이 E인 요소 선택 `#E`  
>class는 동일한 값으로 여러군데 사용가능하지만 id는 고유한 값이어야 함  

### 복합 선택자  
- __일치 선택자__  
E와 F를 동시에 만족하는 선택자 `EF`  
- __자식 선택자__  
E의 자식 요소 F를 선택 `E>F`  
- __후손(하위) 선택자__  
E의 후손 요소 F를 선택 `E F`  
- __인접 형제 선택자__  
E의 다음 형제 요소 F 하나만 선택 `E+F`  
- __일반 형제 선택자__  
E의 다음 형제 요소 모두 선택 `E~F`  
>후손(하위): 자식을 포함한 특정한 요소 내의 모든 하위 요소  
>조상(상위): 부모를 포함한 특정한 요소를 감싸는 모든 상위 요소  
>형제: 같은 부모를 공유하는 다른 요소  

### 가상 클래스 선택자  
- __HOVER__  
E에 마우스가 올라가 있는 동안에만 E 선택 `E:hover`  
즉, 마우스를 올렸을 때, 요소가 어떻게 변할지 정의하는 것
```html
<a href="https://google.com">Google!</a>
```  
```css
/*마우스를 올렸을 때 폰트가 커지도록*/
a:hover {
  font-weight: bold;
  font-size: 20px;
}
```  
- __ACTIVE__  
E에 마우스로 클릭하는 동안에만 E 선택 `E:actice`  

```html
<div class="box"></div> 
```  
```css
/*마우스를 클릭할 동안에 box가 커지도록*/
.box{
  width:100px;
  height: 100px;
  background: tomato;
  transition: 0.4s;
}
.box:active {
  width: 200px;
  background: yellowgreen;
}
```  
- __FOCUS__  
E가 포커스 된 동안에만 E 선택 `E:focus`  
> 대화형 콘텐츠에서 사용 가능(input, img...)  

```html
<input type="text"> 
```  
```css
/*포커스 된 동안에만 대화창이 커지도록 */
input{
  width:100px;
  outline: none;
  border: 1px solid lightgray;
  transition: 0.4s;
}
input:focus {
  border-color: red;
  width: 200px;
}
```  
- __FIRST CHILD__  
E가 형제 요소 중 첫번째 요소라면 선택 `E:first-child`  

- __LAST CHILD__  
E가 형제 요소 중 마지막 요소라면 선택 `E:last-child`  

```CSS
.fruits li:last-child{
    color: red;
}
```  
```html
<ul class="fruits">
    <li>딸기</li>
    <li>사과</li>
    <li>바나나</li> <!--선택-->
</ul>
```  
- __NTH CHILD__   
E가 형제 요소 중 n번째 요소라면 선택 `E:nth-child(n)`  
(n 키워드 사용시 0부터 해석)    

```CSS
.fruits li:nth-child(n+3){
    color: red;
}
```  
```html
<ul class="fruits">
    <li>딸기</li>
    <li>사과</li>
    <li>바나나</li> <!--선택-->
    <li>수박</li> <!--선택-->
</ul>
```     
> 2번 이후부터 선택  
>> 오른쪽에서 왼쪽으로 해석하는 것이 더 정확  

- __NTH OF TYPE__  
E의 타입(태그이름)과 동일한 타입인 형제 요소 중 E가 n번째 요소라면 선택 `E:nth-of-type`  
> 클래스를 태그이름처럼 쓰지 않도록 주의  

- __부정 선택자__  
S가 아닌 E선택 `E:not(S)`  

### 가상 요소 선택자  
- __BEFORE__  
E요소 내부의 앞에, 내용을 삽입  `E::before`  
content 속성 필수  

- __AFTER__  
E요소 내부의 뒤에, 내용을 삽입  `E::after`  

### 속성 선택자  
- __ATTR__  
속성 attr을 포함한 요소 선택 `[attr]`  
- __ATTR=VALUE__    
속성 attr을 포함하며 속성 값이 value인 요소 선택 `[attr=value]`  
- __ATTR$=VALUE__   
속성 attr을 포함하며 속성 값이 value로 끝나는 요소 선택 `[attr$=value]`  

## 상속  
## 우선순위 결정  
같은 요소가 여러 선언의 대상이 될 경우, 어떤 선언의 CSS속성을 우선 적용할지 결정하는 방법
1. 명시도 점수가 높은 선언이 우선  
2. 점수가 같은 경우, 가장 마지막에 해석되는 선언이 우선  
3. 명시도는 '상속' 규칙보다 우선  
4. `!important` 가 적용된 선언 방식이 다른 모든 방식보다 우선   
 
> 인라인 선언 방식\>  
> 아이디 선택자\>  
> 클래스 선택자\>  
> 태그 선택자\>  
> 전체 선택자\>    
> (not 선택자, 상속 계산x) 



