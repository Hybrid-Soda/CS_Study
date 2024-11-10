### [HTTP 프로토콜](https://youtu.be/TwsQX1AnWJU?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

#### 1. 7계층 프로토콜 개요

- **7계층 (응용 계층)** 에는 다양한 프로토콜이 존재

  - 예시: HTTP, FTP, SMTP 등
  - 개발자가 소켓 통신 등을 활용해 직접 프로토콜을 정의할 수도 있음

- HTTP는 웹 서비스를 제공하기 위해 가장 널리 사용되는 프로토콜

#### 2. HTTP (HyperText Transfer Protocol)

- 정의: 웹 브라우저와 서버 간의 데이터를 주고받기 위한 프로토콜
- 역할: 웹 페이지(HTML), 이미지, 동영상 등의 데이터를 전송
- 특징:

  - 요청-응답(Request-Response) 방식으로 동작
  - 클라이언트가 서버에 요청을 보내면, 서버는 이에 대한 응답을 반환

- HTTP vs HTTPS:

  - HTTP: 기본적인 데이터 전송 프로토콜
  - HTTPS: HTTP에 **SSL(Secure Socket Layer)**을 추가하여 보안을 강화한 프로토콜

#### 3. HTTP 프로토콜 버전 변화

- HTTP 1.0:

  - 요청-응답 후 연결을 끊는 방식
  - 하나의 웹 페이지를 로드할 때마다 여러 번의 연결이 필요 → 비효율적

- HTTP 1.1:

  - Persistent Connection 지원 (연결 유지)
  - 한번 연결 후 여러 요청을 연속적으로 처리 가능 → 성능 개선

#### 4. 웹 기술 개요

- 웹을 구성하는 기술들을 클라이언트 측과 서버 측으로 구분
- 클라이언트 사이드 기술:

  - HTML: 웹 페이지의 구조와 내용 정의
  - CSS: 웹 페이지의 스타일 및 디자인 설정
  - JavaScript: 웹 페이지의 동적 기능 및 인터랙션 구현
  - 특징: 클라이언트 컴퓨터에서 실행되며, 사용자가 소스를 볼 수 있음

- 서버 사이드 기술:

  - ASP.NET, JSP, PHP:
  - 서버에서 코드를 실행하고 결과만 클라이언트에 전달
  - 클라이언트는 소스를 볼 수 없음 (보안 강화)

- 활용 예:

  - JSP: 주로 공공기관 및 대규모 프로젝트에 사용
  - PHP: 상대적으로 가벼운 웹 사이트 제작에 사용

#### 5. 웹 개발 관련 개념

- 프론트엔드(Frontend): 사용자와 직접 상호작용하는 화면 개발

  - 사용 기술: HTML, CSS, JavaScript

- 백엔드(Backend): 서버에서 동작하는 프로그램 개발

  - 사용 기술: Python, Java, PHP, ASP.NET 등

### [HTTP 요청 프로토콜](https://youtu.be/rxaBwwI_JnI?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

#### 1. HTTP 요청 프로토콜 구조

- 텍스트 기반으로 작성되며, 영문자와 특수문자 사용
- 구조:
  1. Request Line (요청 라인): 요청의 종류, URI, HTTP 버전이 포함된 첫 번째 줄
  1. Header (헤더): 요청에 대한 추가 정보 제공, 여러 줄로 구성됨
  1. Blank Line (공백 줄): 헤더와 본문을 구분하기 위해 빈 줄 삽입
  1. Body (본문): 요청 시 추가 데이터가 필요한 경우 사용 (주로 POST 요청에서 활용)
- 예시:

  ```
    <Request Line>
    GET /produ/content.asp?code=sch-v310 HTTP/1.1

    <Header>
    Accept: image/gif, image/jpeg, image/pjpeg, image/pjpeg, application/x-shockwave-flash,
    application/vnd.ms-excel, application/vnd.ms-powerpoint, application/msword,
    application/xaml+xml, application/x-ms-xbap, application/x-ms-application, */*
    Referer: http://www.sst.com/
    Accept-Language: ko
    User-Agent: Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 5.1; Trident/4.0;
    InfoPath.3; .NET4.0C; .NET4.0E)
    Accept-Encoding: gzip, deflate
    Host: www.sst.com
    Proxy-Connection: Keep-Alive
    Cookie: ASPSESSIONIDCCDQARAS=EMCDFFBCEC FHKPAGOADOIOIE

  ```

#### 2. Request Line (요청 라인) 구성 요소

- 요청 메서드 (Request Method): 서버에 어떤 작업을 요청할지 정의
- URI (Uniform Resource Identifier): 요청 대상 리소스의 경로
- HTTP 버전: 예시 - `HTTP/1.1`
- 예시: `GET /index.html HTTP/1.1`

#### 3. HTTP 요청 메서드 종류

- GET: 클라이언트가 서버로부터 데이터를 요청할 때 사용
  - 데이터를 URL에 포함하여 전송
  - 주로 웹 페이지, 이미지 등 리소스 요청 시 사용
- POST: 클라이언트가 서버에 데이터를 전송할 때 사용
  - 데이터를 본문(Body)에 포함하여 전송
  - 주로 폼 데이터, 로그인 정보 등 민감한 데이터 전송에 사용
- HEAD: GET과 유사하지만, 헤더 정보만 요청
- PUT: 서버에 데이터 업로드, 주로 파일 업데이트
- DELETE: 서버에서 지정된 리소스 삭제
- OPTIONS: 서버에서 사용 가능한 메서드 종류 확인
- PATCH: 리소스의 일부 수정에 사용

#### 4. GET vs. POST 방식의 차이

- GET 요청:

  - 데이터를 URL의 쿼리 스트링에 포함하여 전송
  - 예시: `GET /search?q=example HTTP/1.1`
  - 주소창에 데이터 노출됨, 중요한 정보 전송에 부적합
  - 브라우저의 캐시 가능 (보안 이슈)
  - 데이터 전송량에 제한 있음

- POST 요청:

  - 데이터를 본문(Body)에 포함하여 전송
  - 예시:

    ```
      POST /login HTTP/1.1
      Content-Type: application/x-www-form-urlencoded

      username=user&password=pass
    ```

  - 주소창에 데이터 노출되지 않음
  - 민감한 정보 전송 시 적합 (아이디, 비밀번호 등)
  - 대용량 데이터 전송 가능
  - HTTPS와 함께 사용 시 보안 강화

### [URL, URI란?](https://youtu.be/2ikhZ_fNP5Y?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

#### 1. URI (Uniform Resource Identifier)

- 정의: 인터넷 상의 특정 자원을 식별하는 유일한 주소
- 구성 요소:
  - 스키마(schema): 요청 형식 지정 (http, https, ftp 등)
  - 호스트(host): 도메인 이름 또는 IP 주소
  - 포트 번호(port): 서비스 접속 포트 (기본적으로 80 또는 443 사용, 생략 가능)
  - 경로(path): 서버 내 자원의 위치 (폴더 및 파일 경로)
  - 쿼리(query): 추가적으로 전달되는 데이터 (? 뒤에 key=value 형태)

#### 2. URL (Uniform Resource Locator)

- 정의: URI의 하위 개념으로, 리소스의 위치를 나타내는 주소
- URI와 URL의 차이점:
  - URI는 자원을 식별하는 모든 주소를 포함 (위치뿐 아니라, 이름도 식별 가능)
  - URL은 자원의 위치를 정확히 지칭하는 주소에 해당

#### 3. URI 구조 예제

- `https://www.example.com:443/path/to/resource?query=value`
- 스키마: https
- 호스트: www.example.com
- 포트 번호: 443 (생략 가능)
- 경로: /path/to/resource
- 쿼리: query=value

#### 4. 예제 설명

- 스키마에 따라 통신 방식이 달라짐 (http, https, ftp 등)
- 도메인 주소는 컴퓨터가 자동으로 IP 주소로 변환 (DNS 서버 활용)
- 포트 번호를 생략해도 브라우저가 기본 포트(80 또는 443) 사용
- 경로와 쿼리를 통해 서버에 저장된 특정 파일과 데이터를 요청

### [HTTP 요청 프로토콜 작성 실습](https://youtu.be/XbGJYsxed2w?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

#### 1. nc (netcat) 프로그램

- nc: 네트워크 연결을 테스트하거나 서버-클라이언트 통신을 실습할 수 있는 도구
- 주로 TCP/UDP 연결 테스트 및 메세지 주고받기에 사용

#### 2. HTTP 요청 프로토콜 작성 및 서버와 통신하기

- 목적: HTTP 요청을 직접 작성해보고, 서버로부터 응답을 받아보는 실습

#### 3. 실습 절차

- 서버 접속:

  - nc [서버 주소] [포트 번호]
  - 80번 포트는 HTTP 기본 포트
  - 연결 성공 시 서버와 직접 통신할 수 있는 상태가 됨

- HTTP 요청 작성:

- 기본 형식:

  ```
    GET [요청 경로] HTTP/1.1
    Host: [서버 주소]
  ```

- GET 메서드, 요청 경로, HTTP 버전, Host 헤더 작성 후 엔터 두 번 입력

- 응답 확인:

  - 요청이 올바르게 작성되면, 서버로부터 HTTP 응답이 옴
  - 요청 형식이 잘못되면 400 Bad Request 오류 발생

#### 4. HTTP 응답 분석

- HTTP 응답 구조:
  - Status Line: 응답 상태 코드 (예: 200 OK, 400 Bad Request)
  - Headers: 서버 정보, 콘텐츠 타입 등 (예: Server: Apache)
  - Body: HTML 등 실제 웹페이지 콘텐츠

### [URI 이해를 위한 실습](https://youtu.be/HBojczyd1Ac?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

#### JDK 및 Apache Tomcat 설치와 설정

##### 1. JDK 설치

- JDK (Java Development Kit): 자바 개발 및 자바 프로그램 실행에 필요
  - Oracle JDK를 다운로드 후 설치 (주로 JDK 1.8 버전)
  - 설치 시 기본 옵션으로 진행 (넥스트 클릭)

##### 2. JDK 환경변수 설정 (Windows)

- 목적: 시스템에서 java 명령어 인식 가능하도록 설정
- 환경 변수 설정:
  - 내 컴퓨터 → 우클릭 → 속성 → 고급 시스템 설정 → 환경 변수
  - 시스템 변수에서 Path 편집:
    - 기존 값 맨 끝에 ; 추가 후 JDK 경로 붙여넣기 (예: `C:\Program Files\Java\jdk1.8.0\bin`)
  - 새 변수 추가:
    - 변수 이름: JAVA_HOME
    - 변수 값: JDK 설치 경로
  - CMD에서 확인:
  - java -version 및 javac -version 입력하여 설치 확인

#### Apache Tomcat 설치 및 설정

##### 1. Tomcat 다운로드 및 압축 해제

- Tomcat 9.0 버전 다운로드 후 압축 해제
- C 드라이브에 폴더 이동 및 이름 간단히 변경 (예: tomcat9)

##### 2. Tomcat 서버 실행

- `tomcat9/bin/startup.bat` 파일 실행
- 웹 브라우저에서 `http://localhost:8080` 입력 후 Tomcat 시작 페이지 확인

#### 웹 애플리케이션 배포 및 테스트

##### 1. Tomcat 웹 애플리케이션 폴더 구성

- tomcat9/webapps에 새 폴더 생성 (예: `abc/df/hij`)
- 폴더 안에 klm.txt 파일 생성 (내용은 자유롭게 작성)

##### 2. 브라우저에서 접근 테스트

- URL로 접근: `http://localhost:8080/abc/df/hij/klm.txt`

#### JSP 파일 생성 및 쿼리 테스트

##### 1. JSP 파일 생성

- webapps 폴더에 query.jsp 파일 생성
- JSP 파일 내용은 서버에서 쿼리 파라미터를 받아 처리하는 코드 작성

##### 2. 쿼리 파라미터 전달

- 브라우저에서 테스트: `http://localhost:8080/abc/df/query.jsp?number1=10&number2=20`
- 결과: 쿼리로 전달된 값 (`number1`, `number2`)을 더한 결과 출력

### [HTTP 응답 프로토콜](https://youtu.be/kuucNF4Zvbs?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

#### HTTP 응답 프로토콜 개요

- 응답 프로토콜 구성

  - 요청과 비슷한 구조지만 응답에 맞게 변형된 프로토콜
  - 구성: 상태 라인(Status Line), 헤더(Headers), 공백, 바디(Body)

- 상태 라인(Status Line)

  - 구성: HTTP 프로토콜 버전 + 상태 코드(Status Code) + 상태 문구(Status Text)
  - 상태 코드와 상태 문구는 항상 정해진 쌍으로 제공됨

#### 주요 상태 코드 설명

- 2xx (성공)

  - 200 OK: 클라이언트의 요청이 성공적으로 완료됨

- 4xx (클라이언트 오류)

  - 클라이언트 측 문제로 요청 실패
  - 403 Forbidden: 권한이 없는 리소스를 요청함
  - 404 Not Found: 요청한 파일이 서버에 존재하지 않음

- 5xx (서버 오류)

  - 서버 측 문제로 요청 실패
  - 500 Internal Server Error: 서버 내부 오류, 주로 개발 코드 문제로 발생

### [HTTP 헤더 포맷](https://youtu.be/mQTGmxendk8?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

#### HTTP 헤더 개요

- 헤더(Header)의 종류

  - 공통 헤더: 요청(Request)과 응답(Response) 모두에서 사용 가능
  - 요청 헤더(Request Header): 클라이언트가 서버로 보낼 때 사용
  - 응답 헤더(Response Header): 서버가 클라이언트로 응답할 때 사용
  - 특수 헤더(Entity Header): 특정 상황에서 사용됨

- 주요 헤더 설명

  - Content-Length: 바디에 포함된 데이터의 크기 (바이트 단위)
  - Content-Type: 바디에 포함된 데이터의 유형 (예: text/html, application/json 등)

#### 요청 헤더 (Request Header)

- Host

  - HTTP/1.1 버전에서 필수
  - 요청하는 서버의 도메인 이름을 포함해 서버를 식별

- User-Agent

  - 클라이언트의 프로그램 정보 (브라우저, 운영체제 등)를 서버에 전달
  - 예시: 모바일 또는 PC 접속 여부를 서버가 판단하여 적절한 페이지를 제공

- Cookie

  - 서버로부터 받은 쿠키 정보를 클라이언트가 요청 시 다시 서버로 전달
  - 주로 사용자 인증이나 세션 관리에 사용

#### 응답 헤더 (Response Header)

- Set-Cookie

  - 서버가 클라이언트에게 새로운 쿠키를 설정할 때 사용
  - 이후 요청 시 클라이언트가 해당 쿠키를 포함해 전송

- Server

  - 서버 프로그램의 종류와 버전 정보를 포함 (예: Apache, Nginx)
  - 보안상 정보 노출을 피하기 위해 일부 서버에서는 생략 가능

### [HTTP 프로토콜 분석 실습](https://youtu.be/dhMrKTwNI8U?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi)

#### 1. Burp Suite 개요

- 웹 애플리케이션 보안 테스트를 위한 도구
- 클라이언트와 서버 간 HTTP 요청/응답을 중간에서 가로채고 수정 가능
- 실무에서도 많이 사용되는 유용한 프로그램

#### 2. Burp Suite의 동작 원리

- 웹 브라우저(예: 크롬)와 웹 서버 사이의 HTTP 통신을 가로챔
- HTTP 요청/응답을 수정한 후 서버나 클라이언트로 전달
- 주로 프록시(Proxy) 기능을 활용해 HTTP 프로토콜을 가로채고 수정

#### 중요한 사항

- 로컬에서만 변경: Burp Suite를 통해 수정된 내용은 로컬 브라우저에만 반영되며, 실제 서버 데이터에는 영향을 미치지 않음
- 보안 및 윤리: Burp Suite는 보안 테스트 목적으로 사용해야 하며, 악의적인 목적으로 남용해서는 안 됨

#### 요약

- Burp Suite를 통해 HTTP 요청/응답을 가로채고 수정할 수 있음
- HTML, CSS, 자바스크립트 코드를 수정해 웹 페이지 동작을 변경 가능
- 서버 데이터에 영향을 주지 않으며, 로컬 테스트 및 연구 목적으로 활용
