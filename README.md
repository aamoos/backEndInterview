# 백엔드 개발자 CS
> Was란?
- 종류 : Web Logic, Web Spere, Jeus, Jboss, tomcat

- 특징
1. 웹 브라우저와 같은 클라이언트로부터 웹 서버가 요청을 받으면 애플리케이션에 대한 로직을 실행하여 웹 서버로 다시 반환해주는 소프트웨어
2. 웹 서버와 DBMS 사이에 동작하는 미들웨어로써, 컨테이너 기반으로 동작
3. 동적인 컨텐츠를 요청받아 처리 (jsp, asp, php 등)

> WebServer란?

- 종류 : Apache, NginX, IIS, WebTob

- 특징
1. 클라이언트가 서버에 페이지 요청을 하면 요청을 받아 정적 페이지(html, png, css)를 제공함
2. 클라이언트에서 요청이 올때 가장 앞에서 요청에 대한 처리를 함
3. 정적인 컨텐츠(html, css, image 등)을 요청받아 처리

![image](https://user-images.githubusercontent.com/37327676/177281162-a244f024-29bb-4e04-8a73-de5199d93fbe.png)

> DI, DL, AOP, IOC 란?
>
> DI란?
- Dependency Injection의 줄임말로, 의존성주입 이라고 한다.

> Dependency Injection 방법
- @Autowird를 사용한 DI(타입 주입)

![image](https://user-images.githubusercontent.com/37327676/177284698-66e419eb-3fc7-470c-8e1a-d4320516a1c0.png)

- @AllArgsConstructor를 통한 주입

![image](https://user-images.githubusercontent.com/37327676/177284776-705616ea-4520-46b1-84da-2db4498f40a9.png)

- @RequiredArgsConstructor를 통한 주입

![image](https://user-images.githubusercontent.com/37327676/177283017-087062ec-ad75-44fc-aefd-2ad76968a384.png)

- @Setter를 통한 주입

> DL란?
- 한 객체에서 필요로 하는 다른 객체를 찾아서 사용하는 기술

> AOP란?
- Aspect-oriented Programming의 약어로 흩어진 Aspect를 모듈화 할 수 있는 프로그래밍 기법이다. 즉, 여러 곳에서 쓰이는 모듈화하고, 쓰이는 곳에 필요할 때 연결함으로써, 유지 보수 혹은 재사용에 용이하도록 프로그래밍 하는 것

> AOP 주요 개념
- Aspect : 여러 곳에서 쓰이는 코드 (공통 부분)을 모듈화한 것
- Target : Aspect를 적용하는 곳 (클래스, 메소드)
- Advice : 실질적으로 어떤 일을 해야할지에 대한 것, 실질적인 부가기능을 담은 구현체
- JointPoint : Advice가 적용될 위치, 끼어들 수 있는 지점, 메서드 진입 시점, 생성자 호출 시점, 필드에서 값을 꺼내올 때 등 다양한 시점에 적용가능
- PointCut : JointPoint의 상세한 스펙을 정의한 것

> AOP 구현체
- AspectJ
- 스프링 AOP

> IOC란?
1. 제어의 역전이라고 불림
2. 예전에는 의존관계의 제어를 개발자가 직접 해주었다. 그러나 제어권이 컨테이너로 넘어갔고 객체의 생성부터 생명주기의 관리까지 객체에 대한 제어를 프레임워크에서 하는것을 IOC라고 한다.

> XSS란?
1. 크로스 사이트 스크립팅, 즉 사이트 간 스크립팅이라는 이름의 웹 취약점 입니다.
2. 웹 사이트의 관리자가 아닌 악의적인 목적을 가진 제 3자가 악성 스크립트를 삽입하여 의도하지 않은 명령을 실행시키거나 세션 등을 탈취할 수 있는 해킹기법입니다. 

> XSS로 인한 위험성
1. 쿠키 및 세션정보 탈취
2. 악성 프로그램 다운 유도
3. 의도하지 않은 페이지 노출

> XSS 대응방법
1. 입력 값의 길이 제한 (이메일, 아이디, 패스워드 등 목적에 맞게)
2. replace 등의 함수를 이용한 치환
3. 입력 값에 대한 꼼꼼한 유효성 검사 (반드시 서버에서 수행)
4. 불가피하게 html 태그 사용을 허용해야 할 경우 화이트리스트를 만들어 특정 태그 입력만 허용
5. lucy-xss-servlet-filter 같은 웹 어플리케이션으로 들어오는 모든 요청 파라미터에 대해 기본적인 xss 방어 필터링을 수행하는 라이브러리 

> SQL Injection (SQL 삽입 공격)
- SQL Injection이란 악의적인 사용자가 보안상의 취약점을 이용하여, 임의의 SQL문을 주입하고 실행되게 하여 데이터베이스가 비정상적인 동작을 하도록 조작하는 행위입니다.

![image](https://user-images.githubusercontent.com/37327676/177290118-7ea13a47-7454-49a1-af6e-e6a797aaa27d.png)

> SQL Injection 대응방안
- Prepared Statement 구문 사용 : Prepared Statement 구문을 사용하게 되면, 사용자의 입력 값이 데이터베이스의 파라미터로 들어가기 전에 DBMS가 미리 컴파일 하여 실행하지 않고 대기합니다. Spring Mybatis에서 #{}으로 선언하는것과 동일함

- Error Message 노출 금지 : 공격자가 SQL Injection을 수행하기 위해서는 데이터베이스의 정보 (테이블명, 컬럼명 등)이 필요합니다. 데이터베이스 에러 발생시 에러메시지를 되면 테이블명, 컬럼명등이 노출되기 때문에 사용자에게 보여줄수 있는 페이지 또는 메시지 박스를 띄우도록 해야합니다.

- 웹 방화벽 사용 : 웹 공격 방어에 특화되어있는 웹 방화벽을 사용하는 방법입니다. 웹 방화벽은 소프트웨어 형, 하드웨어 형, 프록시 형 이렇게 3가지 종류로 나눌수 있습니다. 
- 소프트웨어형 : 서버내에 직접 설치하는 방법
- 하드웨어 형 : 네트워크 상에서 서버 앞 단에 직접 하드웨어 장비로 구성하는 것
- 프록시 형 : DNS 서버 주소를 웹 방화벽으로 바꾸고 서버로 가는 트래픽이 웹 방화벽을 먼저 거치도록 설정

> 쿠키란?
1. 쿠키는 클라이언트에 저장되는 키와 값이 들어있는 작은 데이터 파일입니다.
2. 쿠키는 이름, 값 만료 날짜(쿠키 저장기간), 경로 정보등이 들어있습니다.
3. 쿠키는 클라이언트의 상태 정보를 본인 하드디스크에 저장하였다가 필요할 때 참조, 재사용합니다.

> 세션이란?
1. 세션은 클라이언트와 웹서버 간 네트워크 연결이 지속 유지되고 있는 상태를 말합니다.
2. 즉, 사용자가 브라우저를 열어 서버를 접속한 뒤 접속을 종료할 때까지의 시점을 말합니다.
3. HTTP 프로토콜은 비접속형 프로토콜이므로, 매 접속시마다 새로운 네트워크 연결이 이루어지는데, 세션이 연결 유지를 가능하게 해줍니다.

> VO, DTO, BO, DAO란?
- DAO(Data Acess Object) : DB에 접근하여 실제 데이터를 조회 또는 조작하는 클래스, Repository 또는 Mapper에 해당함
- BO(Business Object) : 여러 DAO를 활용해 비즈니스 로직을 처리하는 클래스, Service에 해당함
- DTO(Data Transfer Object) : 데이터를 주고 받기 위해 사용하는 클래스
- VO(Value Object) : 실제 데이터만을 저장하는 클래스

> MVC 패턴이란?
1. MVC(Model-View-Controller) 패턴은 아키텍처를 설계하기 위한 디자인 패턴입니다.
2. MVC 패턴은 애플리케이션을 개발할 때 그 구성요소를 3가지로 나눕니다.
- Model : 데이터를 저장하는 컴포넌트
- View : 사용자 인터페이스(UI) 컴포넌트
- Controller : 사용자의 요청을 처리하고 Model과 View를 중개하는 컴포넌트

> Spring MVC란?
> 
Spring MVC란 웹 애플리케이션 개발을 위한 MVC 패턴 기반의 웹 프레임워크입니다. Spring MVC는 애플리케이션의 구성요소를 Model, View, Controller로 분리합니다. 또한 Spring MVC는 아래와 같은 컴포넌트들로 구성됩니다.
- Dispatcher Servlet : 클라이언트의 요청을 먼저 받아들이는 서블릿으로, 요청에 맞는 컨트롤러에게 요청을 전달함
- Handler Mapping : 해당 요청이 어떤 컨트롤러에게 온 요청인지 검사함
- Controller : 클라이언트의 요청을 받아 처리하여 결과를 디스패처 서블릿에게 전달함
- ViewResolver : View의 이름을 통해 알맞은 View를 찾음
- View : 사용자에게 보여질 UI 

> 많은 트래픽이 발생한 경우 대처하는 방법
- 스케일 업(Scale Up) : 서버에 CPU나 RAM등을 추가하여 서버의 하드웨어 스펙을 향상시키는 방법
- 스케일 아웃(Scale Out) : 서버를 여러 대 추가하여 시스템을 증가시키는 방법

> CORS란?
- CORS (Cross-Origin-Resource-Sharing)란 도메인이 다른 2개의 사이트가 데이터를 주고 받을 때 발생하는 문제입니다. 예를 들어 A.com에서 B.com으로 데이터를 요청한다고 하면, 따로 설정을 해주지 않는 한 CORS 에러를 만나게 됩니다.  CORS가 생기게 된 이유는 서버내에서 요청이 허락된 도메인에만 데이터를 주기 위해서인데, 요청을 허락하기 위해서는 Acess-Control-Allow-Origin : {도메인} 과 같은 내용을 Response의 헤더에 추가해주어야 합니다. 만약 도메인을 * 으로 설정하면 모든 도메인에 대해 요청을 허락할 수 있습니다. 그 외에도 Acess-Control-Allow-Methods, Acess-Control-Max-Age등을 설정할 수 있습니다.
- Acess-Control-Allow-Origin : 요청을 보내는 페이지의 출처 [*, 도메인]
- Acess-Control-Allow-Methods ; 요청을 허용하는 메소드, Default : GET, POST
- Acess-Control-Max-Age : 클라이언트에서 preflight 요청 (서버의 응답 가능여부에 대한 확인) 결과를 저장할 시간
- Acess-Control-Allow-Headers : 요청을 허용하는 헤더

> 아파치와 톰캣은 각각 멀티 프로세스인가 멀티 쓰레드인가?
1. 아파치는 기본적으로 멀티 프로세스로 구현되어 있다. 하지만 설정에 따라 멀티 쓰레드를 같이 운용할 수 있다.
2. 톰캣은 요청을 처리하기 위한 쓰레드 풀을 관리하고 있다. 그리고 요청이 오면 해당 쓰레드 풀에서 쓰레드를 꺼내 요청을 처리하도록 한다.
