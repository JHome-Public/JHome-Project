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

### Spring Cloud
_Spring Cloud Gateway, Spring Cloud Netflix Eureka, Spring Cloud Config Server_
- MSA 도입을 위해 Spring Cloud 라이브러리를 활용하였습니다. 
- Gateway, Eureka를 적용하여 Gateway패턴을 구현하였고 설정 파일을 공통으로 관리하도록 Config Server를 활용하였습니다.

### Spring Security & JWT & Redis 활용 인증/인가
- Security Filter를 통한 Login 로직을 구현하였고 JWT 토큰을 Redis Storage에 저장하여 Gateway 패턴에서 토큰 검증이 가능하도록 구현 하였습니다.

### Spring AOP & Logback 활용 로그 출력 및 수집
- Spring AOP를 통해 메서드 실행 전후로 로그를 출력하도록 하였고 Logback으로 콘솔 출력 로그 규격화 및 파일 저장을 구현하였습니다.

### AWS RDS
- 개발 DB를 클라우드 환경에 구축하여 매번 로컬 환경에 DB를 설치하지 않고 추후 협업 시에도 일관된 DB를 활용할 수 있도록 하였습니다.

# Architecture
![image](https://github.com/user-attachments/assets/4b440a74-6bd3-421b-ae34-a45d9c21f5a7)

# Services
### User Service
사용자 등록(회원가입), 정보 조회, 정보 수정, 사용자 삭제(탈퇴), 로그인 기능을 담당합니다.
