## 웹 서버(Web Server)
* 클라이언트의 요청을 받아 HTML이나 오브젝트를 HTTP 프로토콜을 이용해 전송하는 것.
   사용자가 클라이언트로 요청을 보내오면 그 명령에 대한 처리를 실행하고 다시 사용자에게 답변을 보내준다.
* 사용자가 요청한 것들 중에 웹 서버 자체적으로 처리할 수 없는 것들을 톰캣과 같은 컨테이너나 PHP 모듈과
   같이 처리할 수 있는 곳으로 넘겨 처리 결과를 받아와서 사용자에게 넘겨주는 역할도 수행한다.
* 웹 서버만 구축된 서버는 웹 페이지, 이미지 등 정적인 페이지를 생성하지만,
   JSP 컨테이너가 탑재되어 있는 WAS는 JSP 페이지를 컴파일 해 동적인 페이지를 생성한다.
* 웹 서버는 웹 문서를, WAS는 JSP 페이지 등을 양분하여 서버 부담을 줄이는 것이 가능하다.
* Apache, IIS(Internet Information Server), WebtoB 등


## 웹 어플리케이션 서버(Web Application Server / WAS)
* 웹 서버 + 웹 컨테이너.
* 웹상에서 사용하는 컴포넌트들을 올려놓고 사용하게 되는 서버
* EJB와 같은 빈들이 올라가게 되며, 서버에 따라 웹에 필요한 많은 기능들을 포함하고 있다.
* J2EE 스펙을 구현한 서버(JSP / Servlet Container와 EJB Container 로서의 기능)
* 가장 많이 사용하는 WAS는 BEA사의 Web Logic, IBM사의 Web Sphere, T-max사의 Jeus, Tomcat, Redhot사의 JBoss 등이 있다.)
* Tomcat은 JSP / Servlet Container의 기능을 구현했으나 EJB Container로서의 기능은 없다.
    따라서 Tomcat은 Was가 아니라는 사람들도 있다.



## 컨테이너(Containner)
* JSP와 서블릿을 이용하는 웹 응용 프로그램은 자바 언어를 이용해서 작성할 수 있는데,
   JSP와 서블릿을 실행시킬 수 있는 소프트웨어를 웹 컨테이너(Web Container) 혹은 서블릿 컨테이너(Servlet Container)라고 한다.
* Servlet 컨테이너, JSP 컨테이너, EJB 컨테이너 등의 종류가 있으며, 대표적인 웹 컨테이너로는
   자카르타 톰캣(JSP), RESIN, Web Logic, WebtoB 등이 있다.
* 웹 서버에서 JSP를 요청하면 톰캣에서는 JSP 파일을 서블릿으로 변환하여 컴파일을 수행하고,
   서블릿의 수행결과를 웹 서버에서 전달하게 된다. 


 
## 웹 서버와 WAS의 차이점
* 웹 서버와 WAS를 구별 짓는 것은 동적 서버 콘텐츠를 수행하는가? 만약 수행한다면 WAS로 보면 된다.
* 웹 서버 : 정적인 HTML이나 이미지를 제공하는 서버.
* WAS : 동적인 처리를 담당하는 서버. 



■ 웹 서버와 WAS의 일반적인 구성
* 사용자가 브라우저에서 요청을 하게 되면 다음과 같이 웹 서버와 WAS 서버를 거쳐 응답이 돌아오게 된다.
   사용자 요청(웹 브라우저) -> 웹 서버 -> WAS(동적 처리) -> 웹 서버 -> 사용자 응답 메세지(웹 브라우저)
![](/img/hsp1.png)
출처: https://gap85.tistory.com/45 [Joo studio]
