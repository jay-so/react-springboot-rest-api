# [프로젝트] React - Spring Boot 상품 관리 API 구현
## 프로젝트 소개 😎
React로 만들어진 Front End가 정해져있는 상황에서,
백엔드 개발자가 Spring Boot로 상품관리 API를 구현하여 A-Z 최종 서비스를 완성시켜봅니다.

## 🚀 프로젝트 트러블 슈팅

---

### gradle 5.x 버전 이후 lombok 설정 오류
1. gradle 5.x 버전 미만

```
implementation('org.projectlombok:lombok')
```

2. gradle 5.x 버전 이후
```
compileOnly 'org.projectlombok:lombok'
annotationProcessor 'org.projectlombok:lombok'
```

#### Reference(참고자료)
[참고자료 - gradle 버전별 lombok 설정](https://deeplify.dev/back-end/spring/lombok-required-args-constructor-initialize-error)
