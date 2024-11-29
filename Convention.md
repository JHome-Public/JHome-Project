# Convention(작성/보완 진행중)

## Infra.
- 마이크로 서비스의 port 번호는 9000번대를 사용한다.

## Config
- 전체 서비스에서 공통으로 사용 될 설정 값은 **Config-server의 application.yml**에서 관리한다.
    - 예) 날짜 포맷 = yyyy-MM-dd HH:mm:ss
- server.port와 spring.application.name은 **서비스의 application.yml**에 작성한다.

## Log
- 로그 파일 저장 경로 : /logs/application-name/날짜.log

## Micro Service
- 서비스는 도메인 기준으로 구분한다.

## Package
- 패키지명은 모두 소문자로 한다.
- com.jhome.user 하위에 패키지를 위치한다.
- 기본 구조는 다음과 같은 구조를 따른다.
    ```bash
    com.jhome.user
    - common
    - controller
    - domain
    - dto
    - repository
    - security
    - service
    ```

## Class
- 클래스명은 파스칼케이스로 한다.
- 클래스명은 명사로만 작성한다.
- 객체 생성 시 빌더 패턴을 사용한다.
- 객체 주입 시 생성자 주입 방식을 사용한다.

### Controller
- 컨트롤러의 역할
    - 요청 파라미터 검증
    - 서비스 호출
    - 서비스 예외 처리
    - 응답 반환

### Service
- 서비스의 역할
    - 비즈니스 로직 수행
    - 레포지토리 연동
    - 레포지토리 예외 처리
    - 응답 반환

### Repository
- JPA ORM을 활용한다.

## Method
- 메서드명은 카멜케이스로 한다.
- 메서드명은 동사로 시작한다.
- @Transactional은 서비스 메서드에서 사용한다.
