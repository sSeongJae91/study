jsp, asp, php, .. -> 서버 스크립트
<br>
html 등 스크립트 코드 -> 클라이언트 스크립트
# **강의 제목**
- 강의 주제 및 코스 코드
-
## **강의 개요**
- 강의의 전체적인 소개와 목표
- ## **강의 목표**
- 학습자가 강의를 통해 달성할 주요 목표

* [javascript DOM & BOM](#javascript-DOM-&-BOM)

* [연관배열](#연관배열)

* [익명함수](#익명함수)

* [javascript DOM](#javascript-DOM)

* [EVENT](#EVENT)

* [JSON](#JSON(Javascript-Object-Notation))

* [JQuery](#JQuery)

* [Hoisting](#Hoisting)

* [ECMAScript란?](#ECMAScript란?)

* [GUID(UUID)](#GUID)



## javascript DOM & BOM
https://jayzzz.tistory.com/64

## 연관배열
```javascript
<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8"%>
<!DOCTYPE html>
<html>
<head>
<title>Insert title here</title>
<script type="text/javascript">
    var objArr = {
        name1 : ['석혜민', '박현웅', '조진무', '양경석'],
        phoneNum : ['010-1111-2222', '010-3333-4444', '010-5555-6666', '010-7777-7777']
    };
    
    var nameList = '';
    
    for (var i = 0; i < objArr.name1.length; i++) {
        nameList = objArr.name1[i] + " " + objArr.phoneNum[i] + "\n";
        alert(nameList);
    }
    
    
    
    var objArr = {
            석혜민 : '010-1111-2222',
            박현웅 : '010-3333-4444',
            조진무 : '010-5555-6666',
            양경석 : '010-7777-7777',
        };
        
        alert(objArr.박현웅);
</script>
</head>
<body>

</body>
</html>
```
## 익명함수

```javascript
<script type="text/javascript">
    var addFunc = function(p1, p2){
        var sum = p1 + p2;
        return sum;
    }
    
    var sumFunc = addFunc(1, 2);
    alert(sumFunc);
</script>
```

## javascript DOM
```javascript
<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8"%>
<!DOCTYPE html>
<html>
<head>
<title>Insert title here</title>
<script type="text/javascript">
    window.onload = function(){
        var newPtag = document.createElement('div');
        var newSpanTag = document.createElement('span');
        var newButton1 = document.createElement('button');
        var newButton2 = document.createElement('button');
        var text1 = document.createTextNode('버튼1');
        var text2 = document.createTextNode('버튼2');
        
        newButton1.setAttribute('id', 'btn1');
        newButton2.setAttribute('id', 'btn2');
        
        newButton1.appendChild(text1);
        newButton2.appendChild(text2);
        newSpanTag.appendChild(newButton1);
        newSpanTag.appendChild(newButton2);
        newPtag.appendChild(newSpanTag);

        var theObj=document.getElementById('theBox');
        theObj.setAttribute('style', 'background-color:#d8d8d8');
        theObj.appendChild(newPtag);

        var newFormTag = document.createElement('form');
        var newDivTag = document.createElement('div');
        var newTableTag = document.createElement('table');
        var newTrTag = document.createElement('tr');
        var newTdTag = document.createElement('td');
        var buttonTag = document.createElement('button');
        var newTxtTag = document.createTextNode('고생했어요');
        var buttonTxt = document.createTextNode('td추가');
        var bodyTag = document.getElementsByTagName('body');
        var cnt = 0;
        newFormTag.setAttribute('action', 'my');
        newFormTag.setAttribute('method', 'get');
        newDivTag.setAttribute('id', 'container');
        buttonTag.setAttribute('id', 'addTd');
        newTableTag.setAttribute('style', 'border:1px solid black; border-collapse:collapse;');
        
        newTdTag.appendChild(newTxtTag);
        newTrTag.appendChild(newTdTag);
        newTableTag.appendChild(newTrTag);
        newDivTag.appendChild(newTableTag);
        newFormTag.appendChild(newDivTag);
        bodyTag[0].appendChild(newFormTag);
        buttonTag.appendChild(buttonTxt);
        bodyTag[0].appendChild(buttonTag);
        
        var tdButton = document.getElementById('addTd');
        tdButton.addEventListener('click', function(){
            var tdTag = document.createElement('td');
            var newTxtTag1 = document.createTextNode(cnt++);
            
            tdTag.setAttribute('style', 'border-right:1px solid black; border-collapse:collapse;');
            
            tdTag.appendChild(newTxtTag1);
            newTrTag.appendChild(tdTag);
        });
    }
</script>
</head>
<body>
    <div id='theBox'>
        <h1>요소 생성 연습</h1>
    </div>
</body>
</html>
```

## EVENT

* event.stopPropagation(); -> 이벤트 증식 해제
* event.target.nodeName -> 이벤트가 일어난 곳의 노드 네임을 찍는다
* event.preventDefault(); -> a링크 등 이벤트를 막는다.

## JSON(Javascript Object Notation)

http://blog.naver.com/pajamasi/220554189537

### xml 문법 vs json 문법
* xml 문법 -> 내용을 알아보기 편하게(직관적) 만들어야 하는 경우
* json 문법 -> 작성이 쉬운가? (글자를 적는게 빠른가)

## JQuery
* jQuery -> css(selector) + javascript DOM
* JQuery의 장점
    1. 코드의 양이 줄어든다. -> 가독성이 좋아진다.
    1. 브라우저와 상관없이 같은 표준을 제공한다.
    1. 도큐먼트 내용 자체도 바꿀 수 있다. HTML 전체 구조를 완전히 새로 만들거나 확장하기 쉽다. 이 모든 변경이 간단한 API(Application Programming Inerface)로 할 수 있다.
    1. 페이지와 사용자 간 상호작용 처리, 세련된 방식 웹 개발자를 괴롭히는 브라우저 사이의 불일치 문제를 깔끔하게 해결해준다.
    1. 시각적인 효과를 제공해준다.
    1. 페이지를 새로고침하지 않고 서버에서 정보 가져오기(예 : Ajax(비동기 통신)), 클라이언트와 서버 사이에서 통신할 수 있는 훨씬 더 많은 기술을 사용할 수 있다.
    1. 일반적인 자바스크립트 작업을 단순화
* 왜 좋을까
    1. CSS 지식을 최대한 활용
    1. 확장 지원
    1. 브라우저의 차이로부터 해방
    1. 언제나 집합으로 작업
    1. 여러 동작을 한 줄에 작성 -> 임시변수 사용을 최소화하거나 불필요한 반복을 피함
    1. 모든 사람에게 무료로 제공한다.
### Selector 표현식
* $("img") : img 태그를 셀렉트함
* $("li:nth-child(odd)")
* $(".selclass:eq(0)")
* $('img[title *= "02"]') : img태그의 title 속성 중 02를 포함한 속성의 태그들을 호출
* $("input:radio") : input의 radio버튼 호출
* $("input[name=chk]:checked") : input의 name속성이 chk인 체크박스 중 체크된 것들

## Hoisting

_ES6 문법이 표준화가 되면서 크게 신경쓰지 않아도 되는 부분이 되었지만, JavaScript 라는 언어의 특성을 가장 잘 보여주는 특성 중 하나이기에 정리했습니다._

### 정의

`hoist` 라는 단어의 사전적 정의는 끌어올리기 라는 뜻이다. 자바스크립트에서 끌어올려지는 것은 변수이다. `var` keyword 로 선언된 모든 변수 선언은 **호이스트** 된다. 호이스트란 변수의 정의가 그 범위에 따라 `선언`과 `할당`으로 분리되는 것을 의미한다. 즉, 변수가 함수 내에서 정의되었을 경우, 선언이 함수의 최상위로, 함수 바깥에서 정의되었을 경우, 전역 컨텍스트의 최상위로 변경이 된다.

우선, 선언(Declaration)과 할당(Assignment)을 이해해야 한다. 끌어올려지는 것은 선언이다.

```js
function getX() {
  console.log(x); // undefined
  var x = 100;
  console.log(x); // 100
}
getX();
```

다른 언어의 경우엔, 변수 x 를 선언하지 않고 출력하려 한다면 오류를 발생할 것이다. 하지만 자바스크립트에서는 `undefined`라고 하고 넘어간다. `var x = 100;` 이 구문에서 `var x;`를 호이스트하기 때문이다. 즉, 작동 순서에 맞게 코드를 재구성하면 다음과 같다.

```js
function getX() {
  var x;
  console.log(x);
  x = 100;
  console.log(x);
}
getX();
```

선언문은 항시 자바스크립트 엔진 구동시 가장 최우선으로 해석하므로 호이스팅 되고, **할당 구문은 런타임 과정에서 이루어지기 때문에** 호이스팅 되지 않는다.

함수가 자신이 위치한 코드에 상관없이 함수 선언문 형태로 정의한 함수의 유효범위는 전체 코드의 맨 처음부터 시작한다. 함수 선언이 함수 실행 부분보다 뒤에 있더라도 자바스크립트 엔진이 함수 선언을 끌어올리는 것을 의미한다. 함수 호이스팅은 함수를 끌어올리지만 변수의 값은 끌어올리지 않는다.

```js
foo( );
function foo( ){
  console.log(‘hello’);
};
// console> hello
```

foo 함수에 대한 선언을 호이스팅하여 global 객체에 등록시키기 때문에 `hello`가 제대로 출력된다.

```js
foo( );
var foo = function( ) {
  console.log(‘hello’);
};
// console> Syntax Error
```

이 두번째 예제의 함수 표현은 함수 리터럴을 할당하는 구조이기 때문에 호이스팅 되지 않으며 그렇기 때문에 `Syntax Error`를 발생시킨다.

출처 : https://github.com/JaeYeopHan/Interview_Question_for_Beginner/blob/master/JavaScript/README.md#javascript-event-loop

## ECMAScript란?
그렇다면! 다시 본론으로 돌아가서 ECMAScript(이하 ES)란 무엇인가?

ES는 자바스크립트를 이루는 코어(Core)스크립트 언어로써, 다양한 환경에서 운용될 수 있게 확장성을 갖고 있기때문에 사용처가 웹환경으로 국한되어있지는 않다. 즉 위에서 말한 우리가 아는 자바스크립트는 웹브라우저에서 돌아갈 수 있도록 BOM 과 DOM을 함께 사용하는 확장성이 되겠다. 이러한 확장성들은 ES 버전에 따른 문법과 기능의 확장을 가능하게 한다.

그렇다면 ES의 버전관리는 어떻게 되는거야?
ES는 다음과 같은 버전 히스토리를 갖고있다.

ES3 -> ES5 -> ES6(ES2015) -> ES7(ES2016)

뭐야…! 헷갈리게 넘버링과 년도가 따로있네, 그렇다 ES5 != ES2015 였던 것이다. 그렇다면 각 버전에 대해 좀더 자세히 알아보자.

### ES3 (1999)
대중적으로 알고있는 그냥 자바스크립트라고 보면 된다. 함수 단위의 스코프, 호이스팅, 클로저, 프로토타입 등… 우리가 익히 알고있는 자바스크립트의 기본적인 특징들을 갖고있다. 대부분의 브라우저에서 지원하며, IE8까지 크로스브라우징을 지원하는 환경이라면 ES3을 쓰고 있다고 보면 된다.

### ES5 (2009)
ES4는 너무 시대의 흐름을 앞서갔는지 거절되고, 그 후에 점진적인 개선을 목표로 ES5가 나왔다고 한다. 아무리 그래도 10년만에 버전업이라니 너무한것 같지만 많은 편리한 기능이 추가되었다.

배열 배열과 관련하여 편리한 메소드들이 다수 생겼다. forEach, map, reduce, filter, some, every와 같은 순환 메소드들이 생겼다. 이 메소드들은 개발 시 불필요한 중복 코드를 줄여주어서 가독성은 높이고 버그율은 낮추는 효과가 있다.
객체 객체는 프로퍼티에 대한 설정을 할 수 있게 되었다. 객체를 생성, 수정, 복사하는 표준 메소드 Object.Create(), Object.defineProperty(), Object.freeze(), Object.assign() 등 과 getter, setter 등이 추가되었으며, Object.keys() 메소드를 이용하면 for in 메소드도 대체할 수 있게 되었다.
strict 모드 문법을 좀 더 깐깐하게 체크하는 모드이다. 너무 자유분방하였던 기존 ES를 안전하고, 개발자가 인지할 수 있는 범위 안에서 개발할 수 있도록 사용하기 위해 등장했다. Strict mode - JavaScript | MDN에서 자세한 특징을 확인 할 수 있다.
bind() 메소드 this를 강제로 바인딩 시켜주는 메소드이다. 좀 더 명확하게 this 스코프를 지정 할 수 있게 되었다.

### ES6 (ES2015)
ES6보다 ES2015라고 많이 불리우며, ES6 Harmony라고도 불리운다고 한다. ES2015에서 다음과 같은 문제점들이 해결되었다.

호이스팅이 사라진 것 같은 효과
함수 단위 스코프에서 블록 단위 스코프로 변경
this를 동적으로 바인딩하지 않는 화살표 함수
모듈화 지원
콜백 지옥에서 구원해줄 Promise
Default, Rest 파라미터
해체 할당, Spread 연산자
템플릿 리터럴
클래스 이 외에도 추가된점이 너무 많아서 이부분에서 사람들이 진입장벽을 느끼는 것 같다. 브라우저(특히 MS 계열)에서 지원해주지 않는 경우가 많아 바벨(Babel)이라는 트랜스파일러를 써야하는데 이 바벨은 웹브라우저가 아닌 Node.js 위에서 돌아가고… Node.js를 설치하려면 NPM을 알아야하고… 또 모듈화를 사용하려면 웹팩(WebPack)같은 모듈 번들러를 알아야하고…
이런 다양한 장벽 때문에 사람들이 ES2015를 쉽게 접근하지 못하는 경향이 있는 것 같다. 하지만 우리는 언제나처럼 도전할 것이다!

* 기본 매개 변수 (Default Parameters)
* 템플릿 리터럴 (Template Literals)
* 멀티 라인 문자열 (Multi-line Strings)
* 비구조화 할당 (Destructuring Assignment)
* 향상된 객체 리터럴 (Enhanced Object Literals)
* 화살표 함수 (Arrow Functions)
* Promises
* 블록 범위 생성자 Let 및 Const (Block-Scoped Constructs Let and Const)
* 클래스 (Classes)
* 모듈 (Modules)

참조 : https://blog.asamaru.net/2017/08/14/top-10-es6-features/
듀토리얼 : https://www.w3schools.com/js/js_es6.asp

### ES7 (ES2016)
이번에는 다행히? ES2015때처럼 큰 변화는 없었다. 비교하자면 ES2015의 1/10 정도도 안되는 분량? 휴.. 다행이다.

### 제곱 연산자(\*\*) 등장
Array.includes 배열에 해당 요소가 존재하는지 확인하는 메소드 등장
ES8 (ES2017)
ES2017에서는 Promise 급의 중대한 변화인 async, await등이 발표되었습니다!

async
await
객체 객체의 좀더 심화된 메소드가 등장했습니다. Object.keys()에 대응되는 메소드인 Object.values(), Object.keys()와 Object.values()를 합쳐 놓은 Object.entries(), Object.getOwnPropertyDescriptor의 복수 형태인 Object.getOwnPropertDescriptors()로써 상속받지 않은 속성들의 설명만 보여줍니다.
문자열 단순 편의기능이 추가되었습니다. 문자열 앞부분에 공백을 넣어 자리수를 맞춰주는 String.padStart(), 문자열 뒷부분에 공백을 넣어 자리수를 맞춰주는 String.padEnd()
매개변수 마지막에 콤마를 붙이는걸 허용

[https://luckydavekim.github.io/web/2018/02/07/what-is-the-ecmascript/]


## GUID

전역 고유 식별자(Globally Unique Identifier, GUID)는 응용 소프트웨어에서 사용되는 유사 난수이다. GUID는 생성할 때 항상 유일한 값이 만들어진다는 보장은 없지만, 사용할 수 있는 모든 값의 수가 2128 = 3.4028×1038개로 매우 크기 때문에, 적절한 알고리즘이 있다면 같은 숫자를 두 번 생성할 가능성은 매우 적다.

```js
<script>
  function guid() {
    function s4() {
      return ((1 + Math.random()) * 0x10000 | 0).toString(16).substring(1);
    }
    return s4() + s4() + '-' + s4() + '-' + s4() + '-' + s4() + '-' + s4() + s4() + s4();
  }

  function show_uuid() {
    document.getElementById('uuid').value = guid();
  }

</script>
<button onclick='show_uuid()'>생성</button>
<input type='text' size='40' id='uuid' />
```
