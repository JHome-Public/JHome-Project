# JHome-Project (진행중)
만들어보고싶은 프로젝트 아이디어가 떠올랐지만 여러 프로젝트를 해보며 거창했던 아이디어와 기획들은 경험 부족으로 무너졌던 기억이 있습니다.<br>
그래서 작지만 완성된 제품을 만든 뒤 하나씩 기능을 추가해보면 좋겠다 생각했습니다.<br>
팀원도 없이 혼자 할 수 있는데까지 최대한 해보는 것으로 계획하였고 필요한 시점에 필요한 팀원을 찾아볼 생각입니다.

당장에 아이디어를 실현 시키려하기 보단 단계적으로 필요한 기능을 쌓아올리려고 합니다. <br>
그 단계의 마지막 지점에서 어떠한 아이디어로 시작되었는지 확인해주시길 바랍니다.

# Tech Stacks
### Versions
- JDK : 17
- Gradle : 8.5
- Spring Boot : 3.2.4
- Spring Cloud : 2023.0.3
- MySQL(AWS RDS) : 8.0.39

### ~~Spring Cloud Data Flow 활용 Batch, Stream Job 관리~~

### Spring Cloud 활용 MSA 구현
- Gateway, Eureka를 활용하여 Gateway패턴을 구현
- Config Server를 활용하여 설정 파일을 공통으로 관리

### Spring Security & JWT & Redis 활용 인증/인가
- Spring Security를 활용하여 일반 회원 Login 기능을 구현
- OAuth2 활용 SNS 로그인 기능 구현
- Access(Header), Refresh(Cookie) 두개의 JWT 토큰을 발급
- Refresh 토큰은 Redis Storage에 저장하여 API-Gateway에서 토큰 검증을 진행하도록 구현

### Spring AOP & Logback 활용 로그 출력 및 수집
- Spring AOP를 활용하여 메서드 실행 전후로 로그를 출력
- Logback을 활용하여 콘솔 출력 로그 규격화 및 로그 파일 저장 구현

### AWS RDS
- AWS RDS MySQL, PostgreSQL DB 활용

# Architecture
![image](https://github.com/user-attachments/assets/ead907cd-1f5b-4a57-b43d-a008e4ce1c94)

# Services
### API-Gateway
토큰 검증, 라우팅을 담당합니다.

### Auth-Service
로그인, 로그아웃 기능을 담당합니다.

### User-Service
사용자 등록(회원가입), 정보 조회, 정보 수정, 사용자 삭제(회원탈퇴) 기능을 담당합니다.
