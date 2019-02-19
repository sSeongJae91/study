# React

리액트는 Node JS와 함께 SSR(Server-Side Rendering)로 많이 사용된다. CSR은 SEO 하기가 불편하지만 SSR은 그런 문제가 없어서 토이프로젝트가 아니면 
대부분 Node JS와 SSR(Next.js)을 선호하는 추세이다.
특히 소규모 스타트업같이 인력이 부족한 회사들도 JS로 React-NodeJS-React Native-MongoDB 스택을 사용하는 사람들도 많다.
다만 개발할때 SSR을 염두에 두고 개발해야 한다.

* 서버사이드 렌더링이란?
  - http://webframeworks.kr/tutorials/react/server-side-rendering/

* 왜 서버사이트 렌더링이 필요할까?
  - https://subicura.com/2016/06/20/server-side-rendering-with-react.html

* Next.js - 서버 사이드 렌더링 프레임워크
  - https://blog.kesuskim.com/2017/06/next-js-react-server-side-rendering-framework/


## React vs React Native

* React
  - 사용자 인터페이스(UI)를 만들기 위한 자바스크립트(JavaScript)라이브러리로서 구조가 MVC, MVW(Model-View Whatever)등인 프레임워크와 달리 오직V(View)만 신경쓰는 
* React Native
  - 리액트 네이티브는 네이티브 모바일 앱을 만들 수 있게 도와주는 라이브러리로서 Objective-C, Java 또는 Swift를 사용하여 만든 앱과 구별 할 수없는 실제 모바일 앱을 만들 수 있다.  React Native는 일반 iOS 및 Android 앱과 동일한 기본 UI 빌딩 블록을 사용한다. JavaScript와 React를 사용하여 이러한 빌딩 블록을 함께 모으는 것이다. (React Native는 자바스크립트 코드와 네이티브 코드를 별도의 스레드로 분리하여 둘 사이의 통신을 비동기식으로 만들어 느려지는 현상이 없다)

## 렌더링
* 사용자 화면에 뷰를 보여 주는 것을 렌더링이라고 한다.
  ### 초기 렌더링
  * 리액트에서 다루는 render(){...} 함수는 컴포넌트가 어떻게 생겼는지 정의하는 역할을 한다. 이 함수는 html형식의 문자열을 반환하지 않고 뷰가 어떻게 생겼고 어떻게 작동하는지 정보를 지닌 객체를 반환한다. 컴포넌트 내부에는 또 다른 컴포넌트들이 들어갈 수 있다. 이때 render 함수를 실행하면 그 내부에 있는 컴포넌트들도 재귀적으로 렌더링한다. 이렇게 최상위 컴포넌트의 렌더링 작업이 끝나면 지니고 있는 정보들을 사용하여 HTML 마크업을 만들고, 이를 우리가 정하는 실제 페이지의 DOM 요소 안에 주입한다.

## Node.js와 npm
* Node.js는 크롬 V8 자바스크립트 엔진으로 빌드한 자바스크립트 런타임이다. 이것으로 웹 브라우저 환경이 아닌 곳에서도 자바스크립트를 사용하여 연산할 수 있다. Node.js를 출시한 이후 자바스크립트는 웹 브라우저 영역 외에 웹 서버는 물론, 모바일 애플리케이션, 데스크톱 애플리케이션 영역에서도 활약 중이다.
* npm은 Node.js 패키지 매니저로 수많은 개발자가 만든 모듈(재사용 가능한 코드)을 설치하고 해당 모듈 버전을 관리하는 도구이다.
