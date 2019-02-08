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
