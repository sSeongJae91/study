jsp, asp, php, .. -> 서버 스크립트
<br>
html 등 스크립트 코드 -> 클라이언트 스크립트

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

# JQuery
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
## Selector 표현식
* $("img") : img 태그를 셀렉트함
* $("li:nth-child(odd)")
* $(".selclass:eq(0)")
* $('img[title *= "02"]') : img태그의 title 속성 중 02를 포함한 속성의 태그들을 호출
* $("input:radio") : input의 radio버튼 호출
* $("input[name=chk]:checked") : input의 name속성이 chk인 체크박스 중 체크된 것들
