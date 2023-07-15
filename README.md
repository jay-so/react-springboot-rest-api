# [프로젝트] React - Spring Boot 상품 관리 API 구현
## 프로젝트 소개 😎
React로 만들어진 Front End가 정해져있는 상황에서,
백엔드 개발자가 Spring Boot로 상품관리 API를 구현하여 A-Z 최종 서비스를 완성시켜봅니다.

## 🚀 프로젝트 트러블 슈팅

---

### 1. gradle 5.x 버전 이후 lombok 설정 오류
1. gradle 5.x 버전 미만

```
implementation('org.projectlombok:lombok')
```

2. gradle 5.x 버전 이후
```
compileOnly 'org.projectlombok:lombok'
annotationProcessor 'org.projectlombok:lombok'
```
<br/>

#### Reference(참고자료)

---
[참고자료 - gradle 버전별 lombok 설정](https://deeplify.dev/back-end/spring/lombok-required-args-constructor-initialize-error)

<br/>

### 2. M1 MacOS wix-embedded-SQL 연동 오류

---
- wix-embedded-SQL은 M1 Mac OS를 지원하지 않음(지원 x,윈도우 or Linux 환경에 최적화되어 있음(x86아키텍처))
- wix-embedded-SQL 버전을 변경해도 동일한 이유의 에러가 발생함
- h2 DB으로 테스트용 DB 변경 시 UUID 자료형을 지원하지 않음

<br/>

#### 대안 방안
- JDBC 테스용 코드 내 EmbeddedemMySQL 관련 변수 및 코드 삭제
1. Docker를 이용해 별도의 테스트용 MySQL환경을 구축
2. 로컬 MySQL DB환경에서 테스트용 DB를 구축

-> 테스트용 DB 환경 설정

<br/>

#### 테스트용 DB환경 설정
- src/test/schema_test.sql을 별도로 생성한 후, 테스트 DB환경을 구축

<br/>

#### Reference(참고자료)

---
[참고자료 - M1 macOS EmbeddedMySQL 미지원 사례 ]
(https://github.com/flapdoodle-oss/de.flapdoodle.embed.process/issues/118)
[참고자료 - EmbeddedMySQL공식 레포]
(https://github.com/wix-incubator/wix-embedded-mysql)